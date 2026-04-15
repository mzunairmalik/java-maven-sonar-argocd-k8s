


> **End-to-end automated pipeline:** A Git push triggers a full build, static analysis, Docker image publish, and GitOps deployment to a Kubernetes cluster — all running on AWS EC2.

---

<img width="1392" height="1700" alt="Screenshot 2026-04-15 133222" src="https://github.com/user-attachments/assets/a5f976d1-b8a9-415d-8164-89852c227020" />

## Table of Contents

1. [Project Overview](#project-overview)
2. [Architecture & Workflow](#architecture--workflow)
3. [Tech Stack](#tech-stack)
4. [Prerequisites](#prerequisites)
5. [Infrastructure Setup (AWS EC2)](#infrastructure-setup-aws-ec2)
6. [Jenkins Setup](#jenkins-setup)
7. [SonarQube Setup](#sonarqube-setup)
8. [Docker & DockerHub Setup](#docker--dockerhub-setup)
9. [Kubernetes Cluster Setup](#kubernetes-cluster-setup)
10. [ArgoCD Setup](#argocd-setup)
11. [GitHub Webhook Configuration](#github-webhook-configuration)
12. [Jenkinsfile Walkthrough](#jenkinsfile-walkthrough)
13. [How the Full Pipeline Runs](#how-the-full-pipeline-runs)
14. [Verify the Deployment](#verify-the-deployment)
15. [Troubleshooting](#troubleshooting)
16. [Key Concepts Explained](#key-concepts-explained)

---

## Project Overview

This project implements a **production-grade CI/CD pipeline** for a Java web application. The pipeline is fully automated — from the moment a developer pushes code to GitHub, through compilation, testing, static analysis, containerisation, and finally deployment to a live Kubernetes cluster.

**What makes this pipeline production-grade:**

- **Zero manual deployments** — every merge to `main` deploys automatically.
- **Quality gate enforcement** — SonarQube blocks the pipeline if code quality standards are not met.
- **GitOps model** — ArgoCD continuously reconciles the live cluster state with what is declared in Git. The cluster always matches the repository.
- **Immutable artefacts** — every deployment uses a uniquely tagged Docker image. There is no "latest" ambiguity in production.
- **Infrastructure-as-code mindset** — the pipeline definition lives in the repo as a `Jenkinsfile`. No GUI-only configuration.

---

## Architecture & Workflow

```
Developer → GitHub Push
              │
              ▼
         GitHub Webhook
              │
              ▼
     Jenkins (EC2 Instance)
       ├── Checkout source code
       ├── Spin up Maven Docker agent
       │     ├── mvn compile
       │     ├── mvn test
       │     └── mvn package  →  .jar artefact
       ├── SonarQube static analysis
       │     └── Quality Gate check  ──(FAIL)──▶  Pipeline ABORTS
       │                              │
       │                           (PASS)
       │                              │
       ├── Docker image build (new tag = BUILD_NUMBER)
       ├── Docker image push → DockerHub
       ├── Update deployment.yaml (image tag) in Git repo
              │
              ▼
         GitHub repo updated
              │
              ▼
     ArgoCD (running on K8s cluster)
       ├── Detects change in deployment.yaml
       ├── Applies updated manifest to cluster
       └── Continuously reconciles cluster ↔ Git state
```

The pipeline follows the **GitOps** pattern: Git is the single source of truth for the desired cluster state. ArgoCD's job is to make the cluster match Git — always.

---

## Tech Stack

| Tool | Role | Where it runs |
|---|---|---|
| **GitHub** | Source of truth for code + manifests | Cloud (github.com) |
| **Jenkins** | CI orchestrator | AWS EC2 |
| **Maven** | Build + dependency management | Docker agent (container) |
| **SonarQube** | Static analysis + quality gate | AWS EC2 (Docker container) |
| **Docker** | Containerise the Java app | AWS EC2 |
| **DockerHub** | Container registry | Cloud (hub.docker.com) |
| **ArgoCD** | GitOps continuous delivery | Kubernetes cluster |
| **Kubernetes** | Container orchestration | AWS EC2 / Minikube / EKS |
| **GitHub Webhook** | Triggers Jenkins on push | github.com → EC2 |

---

## Prerequisites

Before starting, make sure you have the following accounts and tools ready:

- An **AWS account** with EC2 access
- A **GitHub account** and this repository forked/cloned
- A **DockerHub account** (free tier is sufficient)
- Basic familiarity with Linux terminal commands
- `kubectl` installed on your local machine (for monitoring the cluster)

---

## Infrastructure Setup (AWS EC2)

### Launch the EC2 Instance

1. Log in to the **AWS Management Console** → EC2 → **Launch Instance**.
2. Choose **Ubuntu 22.04 LTS** as the AMI.
3. Select instance type: **t2.large** (minimum — Jenkins + SonarQube + Docker are memory-intensive).
4. Under **Key pair**, create or select an existing `.pem` key.
5. Under **Security Group**, open the following inbound ports:

   | Port | Protocol | Purpose |
   |---|---|---|
   | 22 | TCP | SSH access |
   | 8080 | TCP | Jenkins web UI |
   | 9000 | TCP | SonarQube web UI |
   | 30000–32767 | TCP | Kubernetes NodePort services |

6. Set storage to at least **20 GB**.
7. Launch the instance and note the **Public IP address**.

### Connect and Install Java

```bash
# SSH into the instance
ssh -i your-key.pem ubuntu@<EC2_PUBLIC_IP>

# Update packages
sudo apt update && sudo apt upgrade -y

# Install Java 17 (required by both Jenkins and Maven)
sudo apt install openjdk-17-jdk -y
java -version
```

---

## Jenkins Setup

Jenkins is the brain of the CI side. It listens for GitHub webhooks and orchestrates every stage of the pipeline.

### Install Jenkins

```bash
# Add Jenkins repository and key
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | \
  sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | \
  sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update
sudo apt install jenkins -y
sudo systemctl enable jenkins
sudo systemctl start jenkins
```

### First-Time Access

1. Open `http://<EC2_PUBLIC_IP>:8080` in your browser.
2. Retrieve the initial admin password:
   ```bash
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword
   ```
3. Complete the setup wizard and install **suggested plugins**.
4. Create your admin user.

### Install Docker on the EC2 Instance

Jenkins uses Docker to spin up the Maven build agent, so Docker must be installed on the host:

```bash
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker

# Allow Jenkins to use Docker without sudo
sudo usermod -aG docker jenkins
sudo usermod -aG docker ubuntu
sudo systemctl restart jenkins
```

### Install Required Jenkins Plugins

Navigate to **Manage Jenkins → Plugins → Available plugins** and install:

- **Docker Pipeline** — lets Jenkins use Docker containers as build agents
- **SonarQube Scanner** — integrates SonarQube analysis into the pipeline
- **GitHub Integration** — receives webhook events from GitHub
- **Pipeline** — enables `Jenkinsfile`-based declarative pipelines
- **Credentials Binding** — safely injects secrets into pipeline stages

Restart Jenkins after installation.

### Add Credentials to Jenkins

Go to **Manage Jenkins → Credentials → Global → Add Credential** and add the following:

| ID (use exactly) | Kind | Value |
|---|---|---|
| `dockerhub-credentials` | Username/Password | Your DockerHub username + password |
| `sonarqube-token` | Secret text | Your SonarQube project token (generated in SonarQube) |
| `github-token` | Username/Password | Your GitHub username + Personal Access Token |

### Configure SonarQube Server in Jenkins

1. Go to **Manage Jenkins → Configure System → SonarQube servers**.
2. Click **Add SonarQube**.
3. Set Name: `SonarQube`
4. Set Server URL: `http://localhost:9000` (or `http://<EC2_IP>:9000`)
5. Set Server authentication token: select `sonarqube-token` from credentials.
6. Save.

### Create the Pipeline Job

1. **New Item** → Enter name (e.g., `java-maven-pipeline`) → Select **Pipeline** → OK.
2. Under **Build Triggers**, check **GitHub hook trigger for GITScm polling**.
3. Under **Pipeline**, select **Pipeline script from SCM**.
4. Set SCM to **Git**, enter your repository URL, and select your GitHub credential.
5. Set **Script Path** to `Jenkinsfile`.
6. Save.

---

## SonarQube Setup

SonarQube performs static code analysis and enforces quality gates — if the code does not meet the configured standards, it fails the pipeline and prevents deployment.

### Run SonarQube via Docker

```bash
docker run -d \
  --name sonarqube \
  -p 9000:9000 \
  -e SONAR_ES_BOOTSTRAP_CHECKS_DISABLE=true \
  sonarqube:lts-community
```

> **Note:** SonarQube requires Elasticsearch. If it fails to start, run:
> ```bash
> sudo sysctl -w vm.max_map_count=262144
> echo "vm.max_map_count=262144" | sudo tee -a /etc/sysctl.conf
> ```

### Configure SonarQube

1. Open `http://<EC2_PUBLIC_IP>:9000`.
2. Log in with default credentials: `admin` / `admin`. Change the password when prompted.
3. Go to **Administration → Security → Users → Tokens**.
4. Generate a token for your project. Copy and save it — you will add it to Jenkins credentials.
5. Create a new project manually. Note the **Project Key** — you will reference it in the `Jenkinsfile`.

### Quality Gate

SonarQube ships with a default **Sonar Way** quality gate. For this pipeline, the default gate is sufficient. You can view and customise it under **Quality Gates** in the SonarQube UI.

When the `waitForQualityGate()` step runs in Jenkins, it polls SonarQube until analysis is complete and returns either `OK` (pipeline continues) or `ERROR` (pipeline aborts).

---

## Docker & DockerHub Setup

The pipeline builds a Docker image of the Java application and pushes it to DockerHub. The image tag is set to the Jenkins `BUILD_NUMBER` — this makes every build uniquely identifiable and traceable.

### Dockerfile Overview

The project `Dockerfile` follows a multi-stage approach:

```dockerfile
# Stage 1: Build
FROM maven:3.9-openjdk-17 AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

# Stage 2: Runtime image
FROM openjdk:17-jdk-slim
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
```

This produces a lean runtime image — the build tools (Maven, JDK source dependencies) are not included in the final image.

### DockerHub Repository

Create a **public** repository on [hub.docker.com](https://hub.docker.com) named `java-maven-app` (or matching the name used in your `Jenkinsfile`).

---

## Kubernetes Cluster Setup

The Kubernetes cluster is where the Java application actually runs. For development and portfolio purposes, you can use **Minikube** on the EC2 instance or a dedicated cluster.

### Option A — Minikube (Single EC2 Instance)

```bash
# Install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -Ls https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install kubectl /usr/local/bin/kubectl

# Install Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Start Minikube (use Docker driver on EC2)
minikube start --driver=docker
kubectl get nodes
```

### Kubernetes Manifests

The repository contains two manifest files in the `k8s/` directory:

**`deployment.yaml`** — defines the desired state for the application pods:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: java-maven-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: java-maven-app
  template:
    metadata:
      labels:
        app: java-maven-app
    spec:
      containers:
      - name: java-maven-app
        image: your-dockerhub-username/java-maven-app:BUILD_NUMBER_PLACEHOLDER
        ports:
        - containerPort: 8080
```

> The `image:` tag is what Jenkins updates automatically after each successful build. ArgoCD detects this change and triggers a rollout.

**`service.yaml`** — exposes the application:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: java-maven-app-service
spec:
  type: NodePort
  selector:
    app: java-maven-app
  ports:
  - port: 80
    targetPort: 8080
    nodePort: 30007
```

---

## ArgoCD Setup

ArgoCD is the CD engine. It watches the GitHub repository and automatically applies any changes in the Kubernetes manifests to the cluster. This is the **GitOps** pattern — Git is the desired state, and ArgoCD makes the cluster match it.

### Install ArgoCD

```bash
# Create a dedicated namespace
kubectl create namespace argocd

# Install ArgoCD
kubectl apply -n argocd -f \
  https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Wait for all pods to be running
kubectl get pods -n argocd -w
```

### Access the ArgoCD UI

```bash
# Patch the service type to NodePort so you can access it via EC2 IP
kubectl patch svc argocd-server -n argocd \
  -p '{"spec": {"type": "NodePort"}}'

# Get the NodePort assigned
kubectl get svc argocd-server -n argocd

# Get the initial admin password
kubectl -n argocd get secret argocd-initial-admin-secret \
  -o jsonpath="{.data.password}" | base64 -d
```

Open `http://<EC2_PUBLIC_IP>:<NodePort>` and log in with `admin` and the password above.

### Create the ArgoCD Application

In the ArgoCD UI:

1. Click **+ New App**.
2. Fill in the form:

   | Field | Value |
   |---|---|
   | Application Name | `java-maven-app` |
   | Project | `default` |
   | Sync Policy | **Automatic** + enable **Prune** and **Self Heal** |
   | Repository URL | `https://github.com/your-username/java-maven-sonar-argocd-k8s` |
   | Revision | `HEAD` |
   | Path | `k8s/` (directory containing your manifests) |
   | Cluster URL | `https://kubernetes.default.svc` |
   | Namespace | `default` |

3. Click **Create**.

ArgoCD will immediately sync and deploy the current manifests. From this point on, whenever Jenkins updates `deployment.yaml` and pushes to GitHub, ArgoCD detects the change within seconds and rolls out the new image.

> **Self Heal**: If someone manually modifies the cluster state (e.g., `kubectl edit deployment`), ArgoCD reverts it back to what Git says. Git always wins.

---

## GitHub Webhook Configuration

The webhook is what connects a GitHub push event to a Jenkins pipeline run.

### Setup Steps

1. In your GitHub repository, go to **Settings → Webhooks → Add webhook**.
2. Set **Payload URL** to: `http://<EC2_PUBLIC_IP>:8080/github-webhook/`
3. Set **Content type** to `application/json`.
4. Select **Just the push event**.
5. Check **Active**.
6. Click **Add webhook**.

GitHub will send a test ping. In Jenkins, you should see a green checkmark on the webhook. From this point, every `git push` to this repository automatically triggers the Jenkins pipeline.

> **EC2 Security Group reminder:** Port 8080 must be open to `0.0.0.0/0` (or at minimum to GitHub's IP ranges) for the webhook to reach Jenkins.

---

## Jenkinsfile Walkthrough

The `Jenkinsfile` at the root of the repository defines every stage of the pipeline as declarative code. Here is an annotated breakdown:

```groovy
pipeline {
    agent none  // No global agent — each stage declares its own

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-credentials')
        IMAGE_NAME = "your-dockerhub-username/java-maven-app"
        IMAGE_TAG  = "${BUILD_NUMBER}"
    }

    stages {

        stage('Checkout') {
            agent { label 'built-in' }
            steps {
                git branch: 'main', url: 'https://github.com/your-username/java-maven-sonar-argocd-k8s'
            }
        }

        // Maven build runs inside a Docker container — no Java/Maven installed on the Jenkins host
        stage('Build & Test') {
            agent {
                docker {
                    image 'maven:3.9-openjdk-17'
                    args  '-v /root/.m2:/root/.m2'  // Cache .m2 between runs for speed
                }
            }
            steps {
                sh 'mvn clean package'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'  // Publish test results
                }
            }
        }

        stage('SonarQube Analysis') {
            agent {
                docker { image 'maven:3.9-openjdk-17' }
            }
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar -Dsonar.projectKey=java-maven-app'
                }
            }
        }

        stage('Quality Gate') {
            agent { label 'built-in' }
            steps {
                timeout(time: 5, unit: 'MINUTES') {
                    // Waits for SonarQube to finish analysis and return gate status
                    // If gate FAILS, this step throws an exception → pipeline aborts
                    waitForQualityGate abortPipeline: true
                }
            }
        }

        stage('Build Docker Image') {
            agent { label 'built-in' }
            steps {
                sh "docker build -t ${IMAGE_NAME}:${IMAGE_TAG} ."
            }
        }

        stage('Push to DockerHub') {
            agent { label 'built-in' }
            steps {
                sh '''
                    echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin
                    docker push ${IMAGE_NAME}:${IMAGE_TAG}
                    docker logout
                '''
            }
        }

        // Update the manifest in Git so ArgoCD picks up the new image tag
        stage('Update Kubernetes Manifest') {
            agent { label 'built-in' }
            steps {
                withCredentials([usernamePassword(credentialsId: 'github-token',
                                                  usernameVariable: 'GIT_USER',
                                                  passwordVariable: 'GIT_TOKEN')]) {
                    sh '''
                        git config user.email "jenkins@pipeline.com"
                        git config user.name  "Jenkins"
                        sed -i "s|image: ${IMAGE_NAME}:.*|image: ${IMAGE_NAME}:${IMAGE_TAG}|g" k8s/deployment.yaml
                        git add k8s/deployment.yaml
                        git commit -m "ci: update image tag to ${IMAGE_TAG} [skip ci]"
                        git push https://${GIT_USER}:${GIT_TOKEN}@github.com/your-username/java-maven-sonar-argocd-k8s.git HEAD:main
                    '''
                }
            }
        }
    }

    post {
        success { echo "Pipeline completed successfully. ArgoCD will deploy image tag ${IMAGE_TAG}." }
        failure { echo "Pipeline FAILED. Check the stage logs above." }
    }
}
```

**Why `agent none` at the top?** Because different stages need different environments. The Maven build runs inside a Maven Docker container. Git operations run on the Jenkins host directly. Declaring `agent none` globally forces each stage to be explicit about where it runs — which is cleaner and more intentional.

**The `[skip ci]` commit message flag** prevents the Git push in the last stage from triggering another pipeline run (which would cause an infinite loop). GitHub webhooks ignore pushes whose commit message contains `[skip ci]`.

---

## How the Full Pipeline Runs

Here is a complete trace of what happens from a `git push` to a live deployment:

1. **Developer pushes code** to the `main` branch on GitHub.
2. **GitHub fires the webhook** — sends an HTTP POST to `http://<EC2_IP>:8080/github-webhook/`.
3. **Jenkins receives the event** and starts the pipeline defined in `Jenkinsfile`.
4. **Checkout stage** — Jenkins pulls the latest source code.
5. **Build & Test stage** — Jenkins starts a `maven:3.9-openjdk-17` Docker container. Maven compiles the code, runs unit tests, and packages the app into a `.jar` file. The container exits after this stage.
6. **SonarQube Analysis stage** — A new Maven container runs `mvn sonar:sonar`. It sends code metrics and coverage data to the SonarQube server.
7. **Quality Gate stage** — Jenkins polls SonarQube for the gate result. If the code has issues that violate the quality gate (e.g. code coverage below threshold, critical bugs found), the pipeline **aborts here**. No image is built, nothing is deployed. The developer is notified to fix the code.
8. **Build Docker Image stage** — Jenkins runs `docker build` on the EC2 host. The image is tagged with the current `BUILD_NUMBER` (e.g. `:42`).
9. **Push to DockerHub stage** — Jenkins logs in to DockerHub using the stored credentials and pushes the new image.
10. **Update Kubernetes Manifest stage** — Jenkins uses `sed` to replace the image tag in `k8s/deployment.yaml` from the old build number to the new one, then commits and pushes to GitHub.
11. **ArgoCD detects the change** — ArgoCD polls the GitHub repo every 3 minutes by default (or can be configured with a webhook for near-instant sync). It sees the updated `deployment.yaml`.
12. **ArgoCD applies the manifest** — It runs the equivalent of `kubectl apply -f k8s/deployment.yaml` on the cluster, triggering a **rolling update** of the Deployment.
13. **Kubernetes rolls out the new pods** — The cluster starts new pods with the updated image, waits for them to become healthy, then terminates the old pods.
14. **Application is live** — The new version of the Java app is running in the cluster.

Total time from push to live: typically **4–8 minutes** depending on build and test duration.

---

## Verify the Deployment

After a pipeline run, verify everything worked:

```bash
# Check that ArgoCD synced successfully
kubectl get application -n argocd

# Check pods are running with the new image
kubectl get pods -o wide

# Check the image tag on the running deployment
kubectl describe deployment java-maven-app | grep Image

# Access the app via the NodePort service
kubectl get svc java-maven-app-service
# Note the NodePort (e.g. 30007), then open:
# http://<EC2_PUBLIC_IP>:30007
```

In the ArgoCD UI, the application card should show **Synced** and **Healthy** with a green status badge.

---

## Troubleshooting

### Jenkins does not start after EC2 reboot

```bash
sudo systemctl start jenkins
sudo systemctl status jenkins
# If Jenkins prompts for password after reboot:
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

### SonarQube container exits immediately

```bash
# Check logs
docker logs sonarqube

# Most common cause: Elasticsearch vm.max_map_count too low
sudo sysctl -w vm.max_map_count=262144
docker start sonarqube
```

### Webhook not triggering Jenkins

- Confirm port 8080 is open in the EC2 Security Group.
- Check Jenkins → **Manage Jenkins → System Log** for incoming webhook requests.
- In GitHub, go to the webhook and click **Recent Deliveries** to see if the POST succeeded.

### Docker permission denied in Jenkins pipeline

```bash
sudo usermod -aG docker jenkins
sudo systemctl restart jenkins
```

### ArgoCD stuck in OutOfSync

```bash
# Force a manual sync
argocd app sync java-maven-app

# Or in the UI: click the Sync button → Force
```

### Pipeline commits trigger another pipeline run (infinite loop)

Ensure your commit message in the manifest update stage contains `[skip ci]`. GitHub will not trigger webhooks for such commits.

---

## Key Concepts Explained

**CI (Continuous Integration):** The practice of automatically building and testing code on every push. In this pipeline, Jenkins handles CI — it compiles, tests, and analyses the code before anything is deployed.

**CD (Continuous Delivery/Deployment):** Automatically delivering the tested, packaged artefact to a target environment. Here, ArgoCD handles CD — it continuously delivers the state declared in Git to the Kubernetes cluster.

**GitOps:** A CD methodology where Git is the single source of truth for infrastructure and application state. Changes are made via Git commits, not direct `kubectl` commands. ArgoCD is a GitOps engine — it reads Git and syncs the cluster to it.

**Docker Agent in Jenkins:** Instead of installing Maven on the Jenkins host, Jenkins spins up a short-lived Docker container (`maven:3.9-openjdk-17`) to run the build. When the build stage finishes, the container is destroyed. This keeps the Jenkins host clean and makes builds reproducible — the build environment is defined by the Docker image, not by what happens to be installed on the host.

**SonarQube Quality Gate:** A pass/fail threshold configured in SonarQube. The gate can enforce rules like "code coverage must be above 80%", "zero critical bugs", "technical debt ratio below 5%". If the gate fails, `waitForQualityGate abortPipeline: true` throws an exception and halts the pipeline — preventing a broken build from reaching production.

**Immutable Image Tags:** Using `BUILD_NUMBER` as the image tag (`:42`, `:43`, `:44`) means every image is unique and traceable. If a deployment causes issues, you can roll back by pointing `deployment.yaml` back to a previous tag.

**Rolling Update (Kubernetes):** When the Deployment's image tag changes, Kubernetes replaces pods gradually — it starts new pods, waits for them to pass health checks, then terminates old pods. At no point is the application fully offline during a deployment.

**Self-Heal (ArgoCD):** If someone manually modifies the cluster state (e.g., changes the replica count with `kubectl`), ArgoCD detects the drift between the cluster and Git, and reverts the cluster back to the Git-declared state. This prevents configuration drift over time.

---

## Repository Structure

```
java-maven-sonar-argocd-k8s/
├── src/                        # Java application source code
│   ├── main/java/
│   └── test/java/
├── k8s/                        # Kubernetes manifests (ArgoCD watches this)
│   ├── deployment.yaml         # Updated by Jenkins after each build
│   └── service.yaml
├── Dockerfile                  # Multi-stage image build
├── Jenkinsfile                 # Pipeline definition (CI stages)
├── pom.xml                     # Maven project configuration
└── README.md                   # This file
```

---

*Built as part of a DevOps portfolio — demonstrating end-to-end CI/CD with Jenkins, SonarQube, Docker, ArgoCD, and Kubernetes on AWS EC2.*
