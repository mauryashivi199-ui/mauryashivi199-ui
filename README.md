<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Shivangi Maurya — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #060b14;
    --surface: #0d1421;
    --surface2: #131c2e;
    --border: #1e2d45;
    --teal: #00bfa5;
    --cyan: #00e5ff;
    --blue: #2979ff;
    --orange: #ff6d00;
    --green: #00e676;
    --yellow: #ffd740;
    --pink: #f50057;
    --text: #e8f4fd;
    --muted: #607d9b;
  }

  * { margin:0; padding:0; box-sizing:border-box; }
  body { background:var(--bg); color:var(--text); font-family:'Syne',sans-serif; min-height:100vh; overflow-x:hidden; }

  #particles { position:fixed; inset:0; z-index:0; pointer-events:none; }
  .page { position:relative; z-index:1; max-width:900px; margin:0 auto; padding:0 20px 80px; }

  /* ── HERO BANNER ── */
  .hero {
    position:relative; text-align:center;
    padding:70px 20px 50px;
    overflow:hidden;
  }
  .hero-bg {
    position:absolute; inset:0;
    background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(0,191,165,0.12) 0%, transparent 70%),
                radial-gradient(ellipse 40% 40% at 20% 80%, rgba(41,121,255,0.08) 0%, transparent 60%),
                radial-gradient(ellipse 40% 40% at 80% 80%, rgba(0,229,255,0.06) 0%, transparent 60%);
  }

  .avatar-ring {
    position:relative; display:inline-block; margin-bottom:24px;
  }
  .avatar-circle {
    width:100px; height:100px; border-radius:50%;
    background: linear-gradient(135deg, var(--teal), var(--blue));
    display:flex; align-items:center; justify-content:center;
    font-size:44px;
    box-shadow: 0 0 0 3px var(--bg), 0 0 0 5px var(--teal), 0 0 30px rgba(0,191,165,0.4);
    animation: float 4s ease-in-out infinite;
    position:relative; z-index:1;
  }
  .ring1 {
    position:absolute; top:50%; left:50%;
    transform:translate(-50%,-50%);
    width:130px; height:130px; border-radius:50%;
    border:1px dashed rgba(0,191,165,0.3);
    animation:spin 10s linear infinite;
  }
  .ring1::before { content:'⚡'; position:absolute; top:-10px; left:50%; transform:translateX(-50%); font-size:16px; }
  .ring2 {
    position:absolute; top:50%; left:50%;
    transform:translate(-50%,-50%);
    width:160px; height:160px; border-radius:50%;
    border:1px dashed rgba(41,121,255,0.2);
    animation:spin 16s linear infinite reverse;
  }
  .ring2::before { content:'🐍'; position:absolute; bottom:-10px; left:50%; transform:translateX(-50%); font-size:14px; }

  .greeting {
    font-size:clamp(26px,5vw,46px); font-weight:800;
    background:linear-gradient(135deg, var(--teal) 0%, var(--cyan) 40%, var(--blue) 100%);
    -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    animation:fadeUp 0.7s ease 0.2s both;
    letter-spacing:-1px;
  }
  .username {
    font-family:'JetBrains Mono',monospace; font-size:14px;
    color:var(--teal); margin-top:6px;
    animation:fadeUp 0.7s ease 0.35s both;
  }
  .tagline {
    font-size:14px; color:var(--muted); margin-top:10px;
    animation:fadeUp 0.7s ease 0.5s both; line-height:1.6;
  }
  .tagline span { color:var(--cyan); }

  .typewriter-wrap {
    display:inline-flex; align-items:center; gap:8px;
    margin-top:18px; padding:10px 22px;
    background:var(--surface); border:1px solid var(--border);
    border-radius:50px; font-family:'JetBrains Mono',monospace; font-size:13px;
    color:var(--cyan); animation:fadeUp 0.7s ease 0.65s both;
  }
  .tw-dot { width:8px; height:8px; border-radius:50%; background:var(--teal); animation:pulse-teal 1.2s infinite; }

  .badges {
    display:flex; flex-wrap:wrap; gap:8px; justify-content:center;
    margin-top:22px; animation:fadeUp 0.7s ease 0.8s both;
  }
  .badge {
    padding:5px 14px; border-radius:50px; font-size:11px; font-weight:700;
    border:1px solid; cursor:default; transition:transform 0.2s, box-shadow 0.2s;
    letter-spacing:0.5px;
  }
  .badge:hover { transform:translateY(-3px); }
  .b-teal  { color:var(--teal);   border-color:#00bfa544; background:#00bfa510; }
  .b-teal:hover { box-shadow:0 4px 16px #00bfa540; }
  .b-blue  { color:var(--cyan);   border-color:#00e5ff44; background:#00e5ff10; }
  .b-blue:hover { box-shadow:0 4px 16px #00e5ff40; }
  .b-org   { color:var(--orange); border-color:#ff6d0044; background:#ff6d0010; }
  .b-grn   { color:var(--green);  border-color:#00e67644; background:#00e67610; }
  .b-ylw   { color:var(--yellow); border-color:#ffd74044; background:#ffd74010; }

  /* ── STATS ── */
  .stats-grid {
    display:grid; grid-template-columns:repeat(4,1fr); gap:12px;
    margin-bottom:36px;
  }
  .stat-card {
    background:var(--surface); border:1px solid var(--border); border-radius:12px;
    padding:18px 12px; text-align:center;
    transition:transform 0.2s, box-shadow 0.2s;
    animation:fadeUp 0.6s ease both;
  }
  .stat-card:hover { transform:translateY(-4px); box-shadow:0 8px 24px rgba(0,191,165,0.1); }
  .stat-num {
    font-size:28px; font-weight:800;
    background:linear-gradient(135deg,var(--teal),var(--cyan));
    -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    display:block;
  }
  .stat-lbl { font-size:10px; color:var(--muted); margin-top:4px; letter-spacing:1px; }

  /* ── SECTION ── */
  .sec-title {
    font-size:11px; color:var(--muted); letter-spacing:3px;
    text-transform:uppercase; margin-bottom:16px;
    display:flex; align-items:center; gap:10px;
  }
  .sec-title::after { content:''; flex:1; height:1px; background:var(--border); }

  /* ── ABOUT ── */
  .about-grid {
    display:grid; grid-template-columns:1fr 1fr; gap:12px;
    margin-bottom:36px;
  }
  .about-item {
    background:var(--surface); border:1px solid var(--border); border-radius:12px;
    padding:16px; display:flex; align-items:flex-start; gap:12px;
    transition:transform 0.2s, border-color 0.2s;
    animation:fadeUp 0.6s ease both;
  }
  .about-item:hover { transform:translateY(-3px); border-color:var(--teal); }
  .about-icon { font-size:24px; flex-shrink:0; }
  .about-text { font-size:12.5px; color:var(--muted); line-height:1.6; }
  .about-text strong { color:var(--text); display:block; margin-bottom:3px; font-size:13px; }

  /* ── SKILLS ── */
  .skills-wrap { margin-bottom:36px; }
  .skills-group { margin-bottom:20px; }
  .skills-group-title { font-size:11px; color:var(--teal); letter-spacing:2px; margin-bottom:10px; font-family:'JetBrains Mono',monospace; }
  .skill-pills { display:flex; flex-wrap:wrap; gap:8px; }
  .skill-pill {
    display:flex; align-items:center; gap:7px;
    padding:7px 14px; border-radius:8px; font-size:12px; font-weight:700;
    border:1px solid; cursor:default; transition:transform 0.2s, box-shadow 0.2s;
    font-family:'JetBrains Mono',monospace; letter-spacing:0.5px;
    animation:fadeUp 0.5s ease both;
  }
  .skill-pill:hover { transform:translateY(-3px) scale(1.05); }
  .sp-linux  { color:#ffd740; border-color:#ffd74044; background:#ffd74010; }
  .sp-linux:hover  { box-shadow:0 4px 16px #ffd74040; }
  .sp-py     { color:#3776ab; border-color:#3776ab55; background:#3776ab12; }
  .sp-py:hover     { box-shadow:0 4px 16px #3776ab50; }
  .sp-node   { color:#68a063; border-color:#68a06355; background:#68a06312; }
  .sp-node:hover   { box-shadow:0 4px 16px #68a06350; }
  .sp-mongo  { color:#4db33d; border-color:#4db33d55; background:#4db33d12; }
  .sp-mongo:hover  { box-shadow:0 4px 16px #4db33d50; }
  .sp-docker { color:#2496ed; border-color:#2496ed55; background:#2496ed12; }
  .sp-docker:hover { box-shadow:0 4px 16px #2496ed50; }
  .sp-k8s    { color:#326ce5; border-color:#326ce555; background:#326ce512; }
  .sp-k8s:hover    { box-shadow:0 4px 16px #326ce550; }
  .sp-jenkins{ color:#d33833; border-color:#d3383355; background:#d3383312; }
  .sp-jenkins:hover{ box-shadow:0 4px 16px #d3383350; }
  .sp-aws    { color:#ff9900; border-color:#ff990055; background:#ff990012; }
  .sp-aws:hover    { box-shadow:0 4px 16px #ff990050; }
  .sp-tf     { color:#7b42f6; border-color:#7b42f655; background:#7b42f612; }
  .sp-tf:hover     { box-shadow:0 4px 16px #7b42f650; }
  .sp-git    { color:#f05032; border-color:#f0503255; background:#f0503212; }
  .sp-git:hover    { box-shadow:0 4px 16px #f0503250; }
  .sp-html   { color:#e44d26; border-color:#e44d2655; background:#e44d2612; }
  .sp-js     { color:#f7df1e; border-color:#f7df1e55; background:#f7df1e12; }

  /* ── PROJECTS ── */
  .projects-grid { display:grid; gap:14px; margin-bottom:36px; }
  .proj-card {
    background:var(--surface); border:1px solid var(--border); border-radius:14px;
    padding:20px 22px; position:relative; overflow:hidden;
    transition:transform 0.3s, box-shadow 0.3s, border-color 0.3s;
    animation:fadeUp 0.6s ease both;
  }
  .proj-card:hover { transform:translateY(-5px); box-shadow:0 10px 36px rgba(0,191,165,0.15); border-color:var(--teal); }
  .proj-card::before {
    content:''; position:absolute; top:0; left:0; right:0; height:2px;
    background:linear-gradient(90deg,var(--teal),var(--cyan),var(--blue));
    transform:scaleX(0); transform-origin:left; transition:transform 0.3s;
  }
  .proj-card:hover::before { transform:scaleX(1); }
  .proj-header { display:flex; align-items:center; gap:12px; margin-bottom:8px; }
  .proj-icon { font-size:26px; }
  .proj-name { font-size:15px; font-weight:700; color:var(--text); }
  .proj-desc { font-size:12.5px; color:var(--muted); line-height:1.6; margin-bottom:12px; }
  .proj-tags { display:flex; flex-wrap:wrap; gap:6px; }
  .proj-tag { font-size:10px; padding:3px 10px; border-radius:20px; background:var(--surface2); border:1px solid var(--border); color:var(--muted); font-family:'JetBrains Mono',monospace; }

  /* ── ROADMAP ── */
  .roadmap-wrap { margin-bottom:36px; }
  .rm-row { display:flex; margin-bottom:4px; }
  .rm-node {
    flex:1; padding:12px 18px; border-radius:10px; border:1px solid;
    font-size:13px; font-weight:600; transition:transform 0.2s; cursor:default;
  }
  .rm-node:hover { transform:scale(1.01); }
  .rm-done    { color:var(--green);  border-color:#00e67644; background:#00e67608; }
  .rm-current { color:var(--yellow); border-color:#ffd74066; background:#ffd74010; animation:pulse-gold 2s infinite; }
  .rm-next    { color:var(--muted);  border-color:var(--border); background:var(--surface); }
  .rm-conn    { width:2px; height:12px; background:var(--border); margin-left:28px; }

  /* ── CONNECT ── */
  .connect-row { display:flex; flex-wrap:wrap; gap:12px; margin-bottom:36px; }
  .connect-btn {
    display:flex; align-items:center; gap:9px;
    padding:12px 22px; border-radius:10px; border:1px solid;
    text-decoration:none; font-size:13px; font-weight:700;
    transition:all 0.2s; font-family:'Syne',sans-serif;
  }
  .connect-btn:hover { transform:translateY(-3px); }
  .cb-li  { color:#0a66c2; border-color:#0a66c255; background:#0a66c210; }
  .cb-li:hover  { box-shadow:0 4px 20px #0a66c250; border-color:#0a66c2; }
  .cb-gh  { color:#e6edf3; border-color:#e6edf333; background:#e6edf310; }
  .cb-gh:hover  { box-shadow:0 4px 20px rgba(230,237,243,0.2); border-color:#e6edf3; }
  .cb-gm  { color:#ea4335; border-color:#ea433555; background:#ea433510; }
  .cb-gm:hover  { box-shadow:0 4px 20px #ea433550; border-color:#ea4335; }

  /* ── FOOTER ── */
  .footer {
    text-align:center; border-top:1px solid var(--border);
    padding-top:28px; color:var(--muted); font-size:12px;
    animation:fadeUp 0.6s ease 0.5s both;
  }
  .footer-wave { font-size:22px; animation:wave 2s infinite; display:inline-block; }

  /* ── ANIMATIONS ── */
  @keyframes float    { 0%,100%{transform:translateY(0)}  50%{transform:translateY(-10px)} }
  @keyframes spin     { to{transform:translate(-50%,-50%) rotate(360deg)} }
  @keyframes fadeUp   { from{opacity:0;transform:translateY(20px)} to{opacity:1;transform:translateY(0)} }
  @keyframes pulse-teal { 0%,100%{opacity:1} 50%{opacity:0.3} }
  @keyframes pulse-gold { 0%,100%{box-shadow:0 0 0 rgba(255,215,64,0)} 50%{box-shadow:0 0 14px rgba(255,215,64,0.3)} }
  @keyframes wave     { 0%,100%{transform:rotate(0deg)} 25%{transform:rotate(20deg)} 75%{transform:rotate(-10deg)} }

  .d1{animation-delay:.1s} .d2{animation-delay:.2s} .d3{animation-delay:.3s}
  .d4{animation-delay:.4s} .d5{animation-delay:.5s} .d6{animation-delay:.6s}

  @media(max-width:600px){
    .stats-grid{grid-template-columns:repeat(2,1fr)}
    .about-grid{grid-template-columns:1fr}
  }
</style>
</head>
<body>

<canvas id="particles"></canvas>

<div class="page">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-bg"></div>
    <div class="avatar-ring">
      <div class="ring2"></div>
      <div class="ring1"></div>
      <div class="avatar-circle">👩‍💻</div>
    </div>
    <h1 class="greeting">Hi 👋, I'm Shivangi Maurya</h1>
    <div class="username">@mauryashivi199-ui</div>
    <p class="tagline">
      <span>DevOps Enthusiast</span> · CSE Student · Backend Developer<br/>
      Linux • Docker • AWS · Code. Build. Deploy. Repeat 🔄
    </p>
    <div class="typewriter-wrap">
      <div class="tw-dot"></div>
      <span id="typewriter"></span><span style="color:var(--teal)">▋</span>
    </div>
    <div class="badges">
      <span class="badge b-teal">⚙️ DevOps Track</span>
      <span class="badge b-blue">🐳 Docker</span>
      <span class="badge b-org">☁️ AWS</span>
      <span class="badge b-grn">🐍 Python</span>
      <span class="badge b-ylw">📍 Lucknow, India</span>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-grid">
    <div class="stat-card d1"><span class="stat-num" id="s1">0</span><div class="stat-lbl">REPOS</div></div>
    <div class="stat-card d2"><span class="stat-num" id="s2">0</span><div class="stat-lbl">CONTRIBUTIONS</div></div>
    <div class="stat-card d3"><span class="stat-num" id="s3">0</span><div class="stat-lbl">LONGEST STREAK</div></div>
    <div class="stat-card d4"><span class="stat-num" id="s4">0</span><div class="stat-lbl">PROFILE VIEWS</div></div>
  </div>

  <!-- ABOUT -->
  <div class="sec-title">🧑‍💻 About Me</div>
  <div class="about-grid">
    <div class="about-item d1">
      <div class="about-icon">🌱</div>
      <div class="about-text"><strong>Currently Learning</strong>DevOps tools: Linux, Docker, Kubernetes, Jenkins, Terraform & AWS</div>
    </div>
    <div class="about-item d2">
      <div class="about-icon">💻</div>
      <div class="about-text"><strong>Backend Dev</strong>Building with Python, Node.js & MongoDB</div>
    </div>
    <div class="about-item d3">
      <div class="about-icon">🎯</div>
      <div class="about-text"><strong>Goal</strong>Build real-world cloud and microservices projects</div>
    </div>
    <div class="about-item d4">
      <div class="about-icon">⚡</div>
      <div class="about-text"><strong>Interests</strong>Cloud Computing, Automation & CI/CD Pipelines</div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="sec-title">🛠️ Skills & Tools</div>
  <div class="skills-wrap">
    <div class="skills-group">
      <div class="skills-group-title">// DevOps & Cloud</div>
      <div class="skill-pills">
        <div class="skill-pill sp-linux  d1">🐧 Linux</div>
        <div class="skill-pill sp-docker d2">🐳 Docker</div>
        <div class="skill-pill sp-k8s   d3">☸️ Kubernetes</div>
        <div class="skill-pill sp-jenkins d4">🔧 Jenkins</div>
        <div class="skill-pill sp-aws   d5">☁️ AWS</div>
        <div class="skill-pill sp-tf    d6">🟣 Terraform</div>
      </div>
    </div>
    <div class="skills-group" style="margin-top:14px">
      <div class="skills-group-title">// Backend & Dev</div>
      <div class="skill-pills">
        <div class="skill-pill sp-py   d1">🐍 Python</div>
        <div class="skill-pill sp-node d2">🟢 Node.js</div>
        <div class="skill-pill sp-mongo d3">🍃 MongoDB</div>
        <div class="skill-pill sp-git  d4">🔴 Git</div>
        <div class="skill-pill sp-html d5">🟠 HTML/CSS</div>
        <div class="skill-pill sp-js   d6">🟡 JavaScript</div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="sec-title">🚀 Projects</div>
  <div class="projects-grid">
    <div class="proj-card d1">
      <div class="proj-header">
        <div class="proj-icon">⚙️</div>
        <div class="proj-name">DevOps CI/CD Pipeline</div>
      </div>
      <div class="proj-desc">Jenkins, Docker aur GitHub se poora CI/CD pipeline build kiya — automated testing se deployment tak.</div>
      <div class="proj-tags">
        <span class="proj-tag">Jenkins</span><span class="proj-tag">Docker</span><span class="proj-tag">GitHub Actions</span><span class="proj-tag">CI/CD</span>
      </div>
    </div>
    <div class="proj-card d2">
      <div class="proj-header">
        <div class="proj-icon">☁️</div>
        <div class="proj-name">AWS Static Website Hosting</div>
      </div>
      <div class="proj-desc">S3 bucket aur CloudFront se static website deploy ki — global CDN ke saath fast loading.</div>
      <div class="proj-tags">
        <span class="proj-tag">AWS S3</span><span class="proj-tag">CloudFront</span><span class="proj-tag">IAM</span><span class="proj-tag">DNS</span>
      </div>
    </div>
    <div class="proj-card d3">
      <div class="proj-header">
        <div class="proj-icon">🐧</div>
        <div class="proj-name">Linux Automation Scripts</div>
      </div>
      <div class="proj-desc">Server automation ke liye shell scripts — monitoring, backup, aur system health checks automated.</div>
      <div class="proj-tags">
        <span class="proj-tag">Bash</span><span class="proj-tag">Shell Script</span><span class="proj-tag">Cron Jobs</span><span class="proj-tag">Linux</span>
      </div>
    </div>
  </div>

  <!-- ROADMAP -->
  <div class="sec-title">🗺️ DevOps Roadmap</div>
  <div class="roadmap-wrap">
    <div class="rm-row"><div class="rm-node rm-done">✅ Linux Fundamentals</div></div>
    <div class="rm-conn"></div>
    <div class="rm-row"><div class="rm-node rm-done">✅ Git & GitHub</div></div>
    <div class="rm-conn"></div>
    <div class="rm-row"><div class="rm-node rm-done">✅ Docker & Containers</div></div>
    <div class="rm-conn"></div>
    <div class="rm-row"><div class="rm-node rm-done">✅ Jenkins CI/CD</div></div>
    <div class="rm-conn"></div>
    <div class="rm-row"><div class="rm-node rm-current">⚡ Kubernetes — Currently Learning</div></div>
    <div class="rm-conn"></div>
    <div class="rm-row"><div class="rm-node rm-next">⬜ Terraform & Infrastructure as Code</div></div>
    <div class="rm-conn"></div>
    <div class="rm-row"><div class="rm-node rm-next">⬜ AWS Advanced (EKS, Lambda, RDS)</div></div>
    <div class="rm-conn"></div>
    <div class="rm-row"><div class="rm-node rm-next">⬜ Monitoring (Prometheus + Grafana)</div></div>
  </div>

  <!-- CONNECT -->
  <div class="sec-title">🤝 Connect With Me</div>
  <div class="connect-row">
    <a class="connect-btn cb-li" href="https://www.linkedin.com/in/shivangi-maurya-bba074380" target="_blank">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
      LinkedIn
    </a>
    <a class="connect-btn cb-gh" href="https://github.com/mauryashivi199-ui" target="_blank">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
      GitHub
    </a>
    <a class="connect-btn cb-gm" href="mailto:mauryashivi199@gmail.com">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
      Gmail
    </a>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div><span class="footer-wave">👋</span> Thanks for visiting!</div>
    <div style="margin-top:6px">MGIMT Lucknow · CSE 2027 · CTS Parakeet DevOps Training 🇮🇳</div>
    <div style="margin-top:8px;color:#2d4a6a;font-size:11px">Made with ❤️ by Shivangi Maurya</div>
  </div>

</div>

<script>
// Particles
const canvas = document.getElementById('particles');
const ctx = canvas.getContext('2d');
let W, H, pts = [];
function resize(){ W=canvas.width=window.innerWidth; H=canvas.height=window.innerHeight; }
resize(); window.addEventListener('resize',resize);
const COLORS=['0,191,165','0,229,255','41,121,255','255,109,0','0,230,118'];
class P {
  constructor(){ this.r(); }
  r(){
    this.x=Math.random()*W; this.y=Math.random()*H;
    this.vx=(Math.random()-.5)*.35; this.vy=(Math.random()-.5)*.35;
    this.rad=Math.random()*1.4+.3;
    this.a=Math.random()*.35+.08;
    this.c=COLORS[Math.floor(Math.random()*COLORS.length)];
  }
  u(){ this.x+=this.vx; this.y+=this.vy; if(this.x<0||this.x>W||this.y<0||this.y>H) this.r(); }
  d(){ ctx.beginPath(); ctx.arc(this.x,this.y,this.rad,0,Math.PI*2); ctx.fillStyle=`rgba(${this.c},${this.a})`; ctx.fill(); }
}
for(let i=0;i<110;i++) pts.push(new P());
function draw(){
  ctx.clearRect(0,0,W,H);
  pts.forEach(p=>{p.u();p.d();});
  for(let i=0;i<pts.length;i++) for(let j=i+1;j<pts.length;j++){
    const dx=pts[i].x-pts[j].x, dy=pts[i].y-pts[j].y, d=Math.sqrt(dx*dx+dy*dy);
    if(d<75){ ctx.beginPath(); ctx.moveTo(pts[i].x,pts[i].y); ctx.lineTo(pts[j].x,pts[j].y); ctx.strokeStyle=`rgba(0,191,165,${.1*(1-d/75)})`; ctx.lineWidth=.5; ctx.stroke(); }
  }
  requestAnimationFrame(draw);
}
draw();

// Typewriter
const lines=['⚙️ DevOps Engineer in Making...','🐳 docker run -it shivi:latest','☁️ aws s3 cp ./skills s3://career','🐧 chmod +x future.sh && ./future.sh','🚀 kubectl apply -f goals.yaml'];
let pi=0,ci=0,del=false;
const tw=document.getElementById('typewriter');
function type(){
  const p=lines[pi];
  if(!del){ tw.textContent=p.slice(0,++ci); if(ci===p.length){del=true;setTimeout(type,1800);return;} }
  else{ tw.textContent=p.slice(0,--ci); if(ci===0){del=false;pi=(pi+1)%lines.length;} }
  setTimeout(type,del?38:60);
}
type();

// Count up
function cu(id,target,suffix=''){
  let n=0; const el=document.getElementById(id);
  const t=setInterval(()=>{ n=Math.min(n+Math.ceil(target/40),target); el.textContent=n+suffix; if(n>=target)clearInterval(t); },30);
}
setTimeout(()=>{ cu('s1',16); cu('s2',65); cu('s3',5); cu('s4',157); },500);
</script>
</body>
</html>
