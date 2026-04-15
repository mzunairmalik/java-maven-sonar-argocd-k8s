<img width="111" height="150" alt="java_cicd_pipeline_workflow" src="https://github.com/user-attachments/assets/a91e5e67-fd6c-4cc3-bbb5-e6f44d13fa37" /># Java CI/CD Pipeline — Jenkins · Maven · SonarQube · Docker · ArgoCD · Kubernetes

> **End-to-end automated pipeline:** A Git push triggers a full build, static analysis, Docker image publish, and GitOps deployment to a Kubernetes cluster — all running on AWS EC2.

---


![Uploadi<svg width="100%" viewBox="0 0 680 920" role="img" xmlns="http://www.w3.org/2000/svg">
  <title style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">Java CI/CD Pipeline — Jenkins, Maven, SonarQube, Docker, ArgoCD, Kubernetes</title>
  <desc style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">End-to-end CI/CD workflow: Git push triggers Jenkins, which runs Maven build and SonarQube analysis, then builds and pushes a Docker image, updates the deployment manifest, and ArgoCD deploys to Kubernetes.</desc>

  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
  <mask id="imagine-text-gaps-9sb13c" maskUnits="userSpaceOnUse"><rect x="0" y="0" width="680" height="920" fill="white"/><rect x="32" y="127.25" width="115.65934753417969" height="19.583341598510742" fill="black" rx="2"/><rect x="32" y="647.25" width="158.80130004882812" height="19.583341598510742" fill="black" rx="2"/><rect x="68.5162582397461" y="38.791664123535156" width="73.4532241821289" height="22.416677474975586" fill="black" rx="2"/><rect x="79.4732894897461" y="57.20832824707031" width="51.053409576416016" height="19.583341598510742" fill="black" rx="2"/><rect x="256.1640319824219" y="38.791664123535156" width="126.10735321044922" height="22.416677474975586" fill="black" rx="2"/><rect x="254.540771484375" y="57.20832824707031" width="128.91846466064453" height="19.583341598510742" fill="black" rx="2"/><rect x="412.5883483886719" y="33.24999237060547" width="56.99140930175781" height="19.583341598510742" fill="black" rx="2"/><rect x="526.820556640625" y="38.791664123535156" width="54.461341857910156" height="22.416677474975586" fill="black" rx="2"/><rect x="502.74090576171875" y="57.20832824707031" width="102.51828002929688" height="19.583341598510742" fill="black" rx="2"/><rect x="259.8929748535156" y="155.7916717529297" width="110.35102081298828" height="22.416677474975586" fill="black" rx="2"/><rect x="261.7339172363281" y="174.2083282470703" width="106.53217315673828" height="19.583341598510742" fill="black" rx="2"/><rect x="77.5058364868164" y="230.24998474121094" width="79.17115020751953" height="19.583341598510742" fill="black" rx="2"/><rect x="53.49258041381836" y="246.25001525878906" width="127.01482391357422" height="19.583341598510742" fill="black" rx="2"/><rect x="58.42140579223633" y="262.25" width="117.23100280761719" height="19.583341598510742" fill="black" rx="2"/><rect x="252.17880249023438" y="237.79165649414062" width="125.77604675292969" height="22.416677474975586" fill="black" rx="2"/><rect x="260.40948486328125" y="257.2083435058594" width="109.18104553222656" height="19.583341598510742" fill="black" rx="2"/><rect x="270.429443359375" y="271.2083435058594" width="89.21926879882812" height="19.583341598510742" fill="black" rx="2"/><rect x="254.03817749023438" y="329.7916564941406" width="122.04097747802734" height="22.416677474975586" fill="black" rx="2"/><rect x="275.06683349609375" y="349.2083435058594" width="79.8663558959961" height="19.583341598510742" fill="black" rx="2"/><rect x="252.8465576171875" y="363.2083435058594" width="124.37892150878906" height="19.583341598510742" fill="black" rx="2"/><rect x="487.0288391113281" y="326.25" width="104.01905059814453" height="19.583341598510742" fill="black" rx="2"/><rect x="505.51190185546875" y="343.25" width="66.97616195678711" height="19.583341598510742" fill="black" rx="2"/><rect x="485.5014953613281" y="359.25" width="107.16758728027344" height="19.583341598510742" fill="black" rx="2"/><rect x="-43.43057632446289" y="-17.208337783813477" width="86.98094177246094" height="22.416677474975586" fill="black" rx="2"/><rect x="-39.641727447509766" y="1.208329439163208" width="79.28345489501953" height="19.583341598510742" fill="black" rx="2"/><rect x="405.13153076171875" y="409.25" width="29.755407333374023" height="19.583341598510742" fill="black" rx="2"/><rect x="489.6831359863281" y="416.79168701171875" width="114.63373565673828" height="22.416677474975586" fill="black" rx="2"/><rect x="504.59503173828125" y="436.2083435058594" width="84.98909759521484" height="19.583341598510742" fill="black" rx="2"/><rect x="326" y="462.25" width="34.39280891418457" height="19.583341598510742" fill="black" rx="2"/><rect x="193.7920684814453" y="499.7916564941406" width="132.5316162109375" height="22.416677474975586" fill="black" rx="2"/><rect x="197.24888610839844" y="519.2083740234375" width="125.87406921386719" height="19.583341598510742" fill="black" rx="2"/><rect x="434.4229431152344" y="499.7916564941406" width="131.21392059326172" height="22.416677474975586" fill="black" rx="2"/><rect x="449.8660888671875" y="519.2083740234375" width="100.2678451538086" height="19.583341598510742" fill="black" rx="2"/><rect x="175.6926727294922" y="583.7916870117188" width="168.6146697998047" height="22.416677474975586" fill="black" rx="2"/><rect x="151.3105010986328" y="603.2083129882812" width="217.37901306152344" height="19.583341598510742" fill="black" rx="2"/><rect x="274" y="634.2500610351562" width="88.97139739990234" height="19.583341598510742" fill="black" rx="2"/><rect x="135.10479736328125" y="669.7916870117188" width="89.7904052734375" height="22.416677474975586" fill="black" rx="2"/><rect x="106.46524047851562" y="688.2083740234375" width="147.06951904296875" height="19.583341598510742" fill="black" rx="2"/><rect x="281.80859375" y="665.25" width="46.38283157348633" height="19.583341598510742" fill="black" rx="2"/><rect x="385.5368957519531" y="669.7916870117188" width="58.45402145385742" height="22.416677474975586" fill="black" rx="2"/><rect x="346.64495849609375" y="688.2083740234375" width="136.78236389160156" height="19.583341598510742" fill="black" rx="2"/><rect x="559.0889892578125" y="669.7916870117188" width="79.91915893554688" height="22.416677474975586" fill="black" rx="2"/><rect x="557.7866821289062" y="688.2083740234375" width="82.42668914794922" height="19.583341598510742" fill="black" rx="2"/><rect x="156.51707458496094" y="765.2500610351562" width="386.4936828613281" height="19.583341598510742" fill="black" rx="2"/><rect x="158.93722534179688" y="782.25" width="382.1256408691406" height="19.583341598510742" fill="black" rx="2"/><rect x="67.11717224121094" y="497.25" width="67.76565551757812" height="19.583341598510742" fill="black" rx="2"/><rect x="50.73695373535156" y="514.25" width="100.85162353515625" height="19.583341598510742" fill="black" rx="2"/><rect x="96.00000762939453" y="842.2500610351562" width="49.725276947021484" height="19.583341598510742" fill="black" rx="2"/><rect x="173.5277862548828" y="843.2500610351562" width="83.55559539794922" height="19.583341598510742" fill="black" rx="2"/><rect x="304.0000305175781" y="843.2500610351562" width="71.52867889404297" height="19.583341598510742" fill="black" rx="2"/><rect x="424" y="843.2500610351562" width="74.17020416259766" height="19.583341598510742" fill="black" rx="2"/><rect x="174" y="863.2500610351562" width="94.28389739990234" height="19.583341598510742" fill="black" rx="2"/><rect x="304.0000305175781" y="863.2500610351562" width="82.4638671875" height="19.583341598510742" fill="black" rx="2"/></mask></defs>

  <!-- ─── LANE BACKGROUNDS ─── -->
  <!-- CI Lane -->
  <rect x="20" y="120" width="640" height="490" rx="14" fill="none" stroke="var(--color-border-tertiary)" stroke-width="1" stroke-dasharray="6 4" style="fill:none;stroke:rgba(222, 220, 209, 0.15);color:rgb(255, 255, 255);stroke-width:1px;stroke-dasharray:6px, 4px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="36" y="142" fill="var(--color-text-tertiary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">CI — Jenkins on EC2</text>

  <!-- CD Lane -->
  <rect x="20" y="640" width="640" height="240" rx="14" fill="none" stroke="var(--color-border-tertiary)" stroke-width="1" stroke-dasharray="6 4" style="fill:none;stroke:rgba(222, 220, 209, 0.15);color:rgb(255, 255, 255);stroke-width:1px;stroke-dasharray:6px, 4px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="36" y="662" fill="var(--color-text-tertiary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">CD — ArgoCD + Kubernetes</text>

  <!-- ─── ROW 1: Developer + GitHub ─── -->
  <!-- Developer -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="40" y="28" width="130" height="56" rx="8" stroke-width="0.5" style="fill:rgb(68, 68, 65);stroke:rgb(180, 178, 169);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="105" y="50" text-anchor="middle" dominant-baseline="central" style="fill:rgb(211, 209, 199);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Developer</text>
    <text x="105" y="67" text-anchor="middle" dominant-baseline="central" style="fill:rgb(180, 178, 169);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">git push</text>
  </g>

  <!-- Arrow: dev → github -->
  <line x1="170" y1="56" x2="224" y2="56" marker-end="url(#arrow)" stroke="#888780" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- GitHub -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="224" y="28" width="190" height="56" rx="8" stroke-width="0.5" style="fill:rgb(68, 68, 65);stroke:rgb(180, 178, 169);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="319" y="50" text-anchor="middle" dominant-baseline="central" style="fill:rgb(211, 209, 199);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">GitHub Repository</text>
    <text x="319" y="67" text-anchor="middle" dominant-baseline="central" style="fill:rgb(180, 178, 169);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">source + k8s manifests</text>
  </g>

  <!-- Arrow: github → webhook label -->
  <line x1="414" y1="56" x2="468" y2="56" marker-end="url(#arrow)" stroke="#888780" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="441" y="48" text-anchor="middle" fill="var(--color-text-tertiary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">webhook</text>

  <!-- Jenkins entry box -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="468" y="28" width="172" height="56" rx="8" stroke-width="0.5" style="fill:rgb(99, 56, 6);stroke:rgb(239, 159, 39);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="554" y="50" text-anchor="middle" dominant-baseline="central" style="fill:rgb(250, 199, 117);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Jenkins</text>
    <text x="554" y="67" text-anchor="middle" dominant-baseline="central" style="fill:rgb(239, 159, 39);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">pipeline triggered</text>
  </g>

  <!-- Arrow: Jenkins header → first stage -->
  <line x1="554" y1="84" x2="554" y2="152" marker-end="url(#arrow)" stroke="#BA7517" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <line x1="554" y1="158" x2="370" y2="158" marker-end="url(#arrow)" stroke="#BA7517" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- ─── ROW 2: Checkout ─── -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="230" y="148" width="170" height="50" rx="8" stroke-width="0.5" style="fill:rgb(99, 56, 6);stroke:rgb(239, 159, 39);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="315" y="167" text-anchor="middle" dominant-baseline="central" style="fill:rgb(250, 199, 117);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Stage: Checkout</text>
    <text x="315" y="184" text-anchor="middle" dominant-baseline="central" style="fill:rgb(239, 159, 39);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">clone latest source</text>
  </g>

  <!-- Arrow down -->
  <line x1="315" y1="198" x2="315" y2="228" marker-end="url(#arrow)" stroke="#BA7517" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- ─── ROW 3: Maven Build (Docker agent) ─── -->
  <!-- Docker agent callout -->
  <rect x="46" y="225" width="142" height="64" rx="8" fill="none" stroke="var(--color-border-secondary)" stroke-width="0.5" stroke-dasharray="4 3" style="fill:none;stroke:rgba(222, 220, 209, 0.3);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-dasharray:4px, 3px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="117" y="245" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">Docker agent</text>
  <text x="117" y="261" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">maven:3.9-openjdk-17</text>
  <text x="117" y="277" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">ephemeral container</text>
  <line x1="188" y1="257" x2="230" y2="257" stroke="var(--color-border-secondary)" stroke-width="0.5" stroke-dasharray="3 3" style="fill:rgb(0, 0, 0);stroke:rgba(222, 220, 209, 0.3);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-dasharray:3px, 3px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="230" y="228" width="170" height="62" rx="8" stroke-width="0.5" style="fill:rgb(8, 80, 65);stroke:rgb(93, 202, 165);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="315" y="249" text-anchor="middle" dominant-baseline="central" style="fill:rgb(159, 225, 203);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Stage: Build &amp; Test</text>
    <text x="315" y="267" text-anchor="middle" dominant-baseline="central" style="fill:rgb(93, 202, 165);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">mvn clean package</text>
    <text x="315" y="281" text-anchor="middle" dominant-baseline="central" style="fill:rgb(93, 202, 165);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">unit tests → .jar</text>
  </g>

  <!-- Arrow down -->
  <line x1="315" y1="290" x2="315" y2="320" marker-end="url(#arrow)" stroke="#0F6E56" mask="url(#imagine-text-gaps-9sb13c)" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- ─── ROW 4: SonarQube ─── -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="230" y="320" width="170" height="62" rx="8" stroke-width="0.5" style="fill:rgb(12, 68, 124);stroke:rgb(133, 183, 235);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="315" y="341" text-anchor="middle" dominant-baseline="central" style="fill:rgb(181, 212, 244);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Stage: SonarQube</text>
    <text x="315" y="359" text-anchor="middle" dominant-baseline="central" style="fill:rgb(133, 183, 235);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">static analysis</text>
    <text x="315" y="373" text-anchor="middle" dominant-baseline="central" style="fill:rgb(133, 183, 235);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">send metrics to server</text>
  </g>

  <!-- SonarQube server callout (right) -->
  <rect x="444" y="320" width="190" height="62" rx="8" fill="none" stroke="var(--color-border-secondary)" stroke-width="0.5" stroke-dasharray="4 3" style="fill:none;stroke:rgba(222, 220, 209, 0.3);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-dasharray:4px, 3px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="539" y="341" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">SonarQube Server</text>
  <text x="539" y="358" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">:9000 (EC2)</text>
  <text x="539" y="374" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">Quality Gate check</text>
  <line x1="400" y1="351" x2="444" y2="351" stroke="var(--color-border-secondary)" stroke-width="0.5" stroke-dasharray="3 3" marker-end="url(#arrow)" style="fill:rgb(0, 0, 0);stroke:rgba(222, 220, 209, 0.3);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-dasharray:3px, 3px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- Arrow down -->
  <line x1="315" y1="382" x2="315" y2="412" marker-end="url(#arrow)" stroke="#185FA5" mask="url(#imagine-text-gaps-9sb13c)" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- ─── ROW 5: Quality Gate decision ─── -->
  <!-- Diamond shape (rotated rect) -->
  <g transform="translate(315,432)" style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="-60" y="-26" width="120" height="52" rx="6" fill="#FAEEDA" stroke="#BA7517" stroke-width="0.5" transform="rotate(0)" style="fill:rgb(250, 238, 218);stroke:rgb(186, 117, 23);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="0" y="-6" text-anchor="middle" dominant-baseline="central" style="fill:#633806;fill:rgb(99, 56, 6);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Quality Gate</text>
    <text x="0" y="11" text-anchor="middle" dominant-baseline="central" style="fill:#854F0B;fill:rgb(133, 79, 11);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">PASS or FAIL?</text>
  </g>

  <!-- FAIL branch (right) -->
  <line x1="375" y1="432" x2="468" y2="432" marker-end="url(#arrow)" stroke="#A32D2D" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="420" y="424" text-anchor="middle" style="fill:#A32D2D;fill:rgb(163, 45, 45);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">FAIL</text>
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="468" y="408" width="158" height="50" rx="8" stroke-width="0.5" style="fill:rgb(121, 31, 31);stroke:rgb(240, 149, 149);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="547" y="428" text-anchor="middle" dominant-baseline="central" style="fill:rgb(247, 193, 193);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Pipeline ABORTS</text>
    <text x="547" y="446" text-anchor="middle" dominant-baseline="central" style="fill:rgb(240, 149, 149);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">no image built</text>
  </g>

  <!-- PASS branch (down) -->
  <line x1="315" y1="458" x2="315" y2="490" marker-end="url(#arrow)" stroke="#0F6E56" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="330" y="477" style="fill:#0F6E56;fill:rgb(15, 110, 86);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">PASS</text>

  <!-- ─── ROW 6: Docker build + push ─── -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="160" y="490" width="200" height="56" rx="8" stroke-width="0.5" style="fill:rgb(8, 80, 65);stroke:rgb(93, 202, 165);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="260" y="511" text-anchor="middle" dominant-baseline="central" style="fill:rgb(159, 225, 203);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Build Docker Image</text>
    <text x="260" y="529" text-anchor="middle" dominant-baseline="central" style="fill:rgb(93, 202, 165);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">tag = BUILD_NUMBER</text>
  </g>

  <line x1="360" y1="518" x2="400" y2="518" marker-end="url(#arrow)" stroke="#0F6E56" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="400" y="490" width="200" height="56" rx="8" stroke-width="0.5" style="fill:rgb(8, 80, 65);stroke:rgb(93, 202, 165);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="500" y="511" text-anchor="middle" dominant-baseline="central" style="fill:rgb(159, 225, 203);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Push to DockerHub</text>
    <text x="500" y="529" text-anchor="middle" dominant-baseline="central" style="fill:rgb(93, 202, 165);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">username/app:42</text>
  </g>

  <!-- vertical line from docker build to update manifest -->
  <line x1="315" y1="490" x2="315" y2="546" stroke="#BA7517" stroke-width="1" stroke-dasharray="3 3" mask="url(#imagine-text-gaps-9sb13c)" style="fill:rgb(0, 0, 0);stroke:rgb(186, 117, 23);color:rgb(255, 255, 255);stroke-width:1px;stroke-dasharray:3px, 3px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <line x1="260" y1="546" x2="315" y2="546" stroke="#BA7517" stroke-width="1" stroke-dasharray="3 3" style="fill:rgb(0, 0, 0);stroke:rgb(186, 117, 23);color:rgb(255, 255, 255);stroke-width:1px;stroke-dasharray:3px, 3px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <line x1="260" y1="546" x2="260" y2="574" marker-end="url(#arrow)" stroke="#BA7517" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- ─── ROW 7: Update manifest ─── -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="100" y="574" width="320" height="56" rx="8" stroke-width="0.5" style="fill:rgb(99, 56, 6);stroke:rgb(239, 159, 39);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="260" y="595" text-anchor="middle" dominant-baseline="central" style="fill:rgb(250, 199, 117);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Update deployment.yaml</text>
    <text x="260" y="613" text-anchor="middle" dominant-baseline="central" style="fill:rgb(239, 159, 39);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">sed image tag → git commit → git push</text>
  </g>

  <!-- Arrow: manifest update → GitHub (loop back, shown as downward into CD lane) -->
  <line x1="260" y1="630" x2="260" y2="660" marker-end="url(#arrow)" stroke="#888780" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <!-- label -->
  <text x="278" y="649" fill="var(--color-text-tertiary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">push to GitHub</text>

  <!-- ─── CD LANE ─── -->

  <!-- GitHub repo (CD) -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="80" y="660" width="200" height="56" rx="8" stroke-width="0.5" style="fill:rgb(68, 68, 65);stroke:rgb(180, 178, 169);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="180" y="681" text-anchor="middle" dominant-baseline="central" style="fill:rgb(211, 209, 199);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">GitHub Repo</text>
    <text x="180" y="698" text-anchor="middle" dominant-baseline="central" style="fill:rgb(180, 178, 169);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">deployment.yaml updated</text>
  </g>

  <line x1="280" y1="688" x2="330" y2="688" marker-end="url(#arrow)" stroke="#534AB7" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="305" y="680" text-anchor="middle" fill="var(--color-text-tertiary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">detects</text>

  <!-- ArgoCD -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="330" y="660" width="170" height="56" rx="8" stroke-width="0.5" style="fill:rgb(60, 52, 137);stroke:rgb(175, 169, 236);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="415" y="681" text-anchor="middle" dominant-baseline="central" style="fill:rgb(206, 203, 246);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">ArgoCD</text>
    <text x="415" y="698" text-anchor="middle" dominant-baseline="central" style="fill:rgb(175, 169, 236);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">syncs manifest → cluster</text>
  </g>

  <line x1="500" y1="688" x2="548" y2="688" marker-end="url(#arrow)" stroke="#534AB7" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- K8s -->
  <g style="fill:rgb(0, 0, 0);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto">
    <rect x="548" y="660" width="102" height="56" rx="8" stroke-width="0.5" style="fill:rgb(60, 52, 137);stroke:rgb(175, 169, 236);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
    <text x="599" y="681" text-anchor="middle" dominant-baseline="central" style="fill:rgb(206, 203, 246);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:14px;font-weight:500;text-anchor:middle;dominant-baseline:central">Kubernetes</text>
    <text x="599" y="698" text-anchor="middle" dominant-baseline="central" style="fill:rgb(175, 169, 236);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:central">rolling update</text>
  </g>

  <!-- Arrow down to final state -->
  <line x1="415" y1="716" x2="415" y2="758" marker-end="url(#arrow)" stroke="#534AB7" style="fill:none;stroke:rgb(156, 154, 146);color:rgb(255, 255, 255);stroke-width:1.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- Self-heal note -->
  <rect x="80" y="758" width="540" height="56" rx="8" fill="none" stroke="var(--color-border-secondary)" stroke-width="0.5" style="fill:none;stroke:rgba(222, 220, 209, 0.3);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="350" y="780" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">ArgoCD continuously reconciles — if cluster drifts from Git, it self-heals.</text>
  <text x="350" y="797" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">Git is always the source of truth. Cluster state always matches the repo.</text>

  <!-- ─── DockerHub external box ─── -->
  <rect x="46" y="490" width="110" height="56" rx="8" fill="none" stroke="var(--color-border-secondary)" stroke-width="0.5" stroke-dasharray="4 3" style="fill:none;stroke:rgba(222, 220, 209, 0.3);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-dasharray:4px, 3px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="101" y="512" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">DockerHub</text>
  <text x="101" y="529" text-anchor="middle" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:middle;dominant-baseline:auto">container registry</text>
  <line x1="156" y1="518" x2="160" y2="518" stroke="var(--color-border-secondary)" stroke-width="0.5" stroke-dasharray="3 3" marker-end="url(#arrow)" style="fill:rgb(0, 0, 0);stroke:rgba(222, 220, 209, 0.3);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-dasharray:3px, 3px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>

  <!-- ─── LEGEND ─── -->
  <rect x="80" y="838" width="530" height="50" rx="8" fill="none" stroke="var(--color-border-tertiary)" stroke-width="0.5" style="fill:none;stroke:rgba(222, 220, 209, 0.15);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="100" y="857" fill="var(--color-text-tertiary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">Legend:</text>
  <rect x="148" y="848" width="24" height="14" rx="3" fill="#FAEEDA" stroke="#BA7517" stroke-width="0.5" style="fill:rgb(250, 238, 218);stroke:rgb(186, 117, 23);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="178" y="858" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">Jenkins stages</text>
  <rect x="278" y="848" width="24" height="14" rx="3" fill="#E1F5EE" stroke="#0F6E56" stroke-width="0.5" style="fill:rgb(225, 245, 238);stroke:rgb(15, 110, 86);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="308" y="858" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">Build / push</text>
  <rect x="398" y="848" width="24" height="14" rx="3" fill="#EEEDFE" stroke="#534AB7" stroke-width="0.5" style="fill:rgb(238, 237, 254);stroke:rgb(83, 74, 183);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="428" y="858" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">GitOps / K8s</text>
  <rect x="148" y="868" width="24" height="14" rx="3" fill="none" stroke="var(--color-border-secondary)" stroke-width="0.5" stroke-dasharray="3 2" style="fill:none;stroke:rgba(222, 220, 209, 0.3);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-dasharray:3px, 2px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="178" y="878" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">External services</text>
  <rect x="278" y="868" width="24" height="14" rx="3" fill="#FCEBEB" stroke="#A32D2D" stroke-width="0.5" style="fill:rgb(252, 235, 235);stroke:rgb(163, 45, 45);color:rgb(255, 255, 255);stroke-width:0.5px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:16px;font-weight:400;text-anchor:start;dominant-baseline:auto"/>
  <text x="308" y="878" fill="var(--color-text-secondary)" style="fill:rgb(194, 192, 182);stroke:none;color:rgb(255, 255, 255);stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;opacity:1;font-family:&quot;Anthropic Sans&quot;, -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, sans-serif;font-size:12px;font-weight:400;text-anchor:start;dominant-baseline:auto">Failure / abort</text>

</svg>ng java_cicd_pipeline_workflow.svg…]()


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
