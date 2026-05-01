<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>GitHub Profile — Gen AI Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #060910;
    --surface: #0d1117;
    --surface2: #161b22;
    --border: #21262d;
    --cyan: #00d9ff;
    --cyan-dim: #00d9ff33;
    --green: #3fb950;
    --amber: #f0b429;
    --red: #f85149;
    --text: #e6edf3;
    --muted: #7d8590;
    --font-mono: 'Fira Code', monospace;
    --font-display: 'Syne', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-mono);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,217,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,217,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr 340px;
    gap: 40px;
    align-items: center;
    margin-bottom: 48px;
    animation: fadeUp 0.8s ease both;
  }

  .hero-left { display: flex; flex-direction: column; gap: 16px; }

  .prompt {
    font-size: 12px;
    color: var(--cyan);
    letter-spacing: 3px;
    text-transform: uppercase;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.2s both;
  }

  .title {
    font-family: var(--font-display);
    font-size: 42px;
    font-weight: 800;
    line-height: 1.1;
    color: var(--text);
    opacity: 0;
    animation: fadeUp 0.6s ease 0.3s both;
  }

  .title span {
    color: var(--cyan);
    text-shadow: 0 0 30px var(--cyan-dim);
  }

  .tagline {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.7;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.4s both;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.5s both;
  }

  .badge {
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 500;
    border: 1px solid;
    letter-spacing: 0.5px;
    text-decoration: none;
    transition: all 0.2s;
  }
  .badge:hover { transform: translateY(-2px); box-shadow: 0 4px 12px rgba(0,217,255,0.2); }
  .badge-cyan { color: var(--cyan); border-color: var(--cyan); background: var(--cyan-dim); }
  .badge-green { color: var(--green); border-color: var(--green); background: #3fb95022; }
  .badge-amber { color: var(--amber); border-color: var(--amber); background: #f0b42922; }

  /* GIF side */
  .hero-gif {
    opacity: 0;
    animation: fadeIn 1s ease 0.6s both;
    position: relative;
  }

  .hero-gif::before {
    content: '';
    position: absolute;
    inset: -2px;
    border-radius: 16px;
    background: linear-gradient(135deg, var(--cyan), transparent, var(--green));
    z-index: -1;
    opacity: 0.5;
  }

  .hero-gif img {
    width: 100%;
    border-radius: 14px;
    display: block;
    border: 1px solid var(--border);
  }

  /* ── CODE BLOCK ── */
  .code-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    margin-bottom: 32px;
    overflow: hidden;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.7s both;
  }

  .code-header {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 12px 16px;
    background: var(--surface2);
    border-bottom: 1px solid var(--border);
  }

  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }

  .code-filename {
    margin-left: auto;
    font-size: 11px;
    color: var(--muted);
  }

  .code-body {
    padding: 20px 24px;
    font-size: 13px;
    line-height: 1.9;
  }

  .c-keyword { color: #ff7b72; }
  .c-class    { color: #ffa657; }
  .c-string   { color: #a5d6ff; }
  .c-comment  { color: var(--muted); font-style: italic; }
  .c-prop     { color: var(--cyan); }
  .c-val      { color: #79c0ff; }
  .c-list     { color: #d2a8ff; }

  /* ── SECTION ── */
  .section {
    margin-bottom: 36px;
    opacity: 0;
    animation: fadeUp 0.6s ease both;
  }

  .section-title {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 11px;
    color: var(--cyan);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 16px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }

  .section-title::before {
    content: '//';
    color: var(--muted);
  }

  /* ── IMPACT BAR ── */
  .impact-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
  }

  .impact-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    text-align: center;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .impact-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--cyan), var(--green));
  }

  .impact-card:hover {
    border-color: var(--cyan);
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(0,217,255,0.1);
  }

  .impact-num {
    font-family: var(--font-display);
    font-size: 28px;
    font-weight: 800;
    color: var(--cyan);
    text-shadow: 0 0 20px var(--cyan-dim);
    display: block;
  }

  .impact-label {
    font-size: 10px;
    color: var(--muted);
    margin-top: 4px;
    letter-spacing: 0.5px;
  }

  /* ── PROJECTS GRID ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
    text-decoration: none;
    color: inherit;
    display: block;
  }

  .project-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--cyan-dim), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .project-card:hover {
    border-color: var(--cyan);
    transform: translateY(-4px);
    box-shadow: 0 12px 32px rgba(0,217,255,0.1);
  }

  .project-card:hover::after { opacity: 1; }

  .project-tag {
    font-size: 10px;
    color: var(--cyan);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .project-name {
    font-family: var(--font-display);
    font-size: 17px;
    font-weight: 700;
    margin-bottom: 8px;
    position: relative;
    z-index: 1;
  }

  .project-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 12px;
    position: relative;
    z-index: 1;
  }

  .project-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    position: relative;
    z-index: 1;
  }

  .stack-pill {
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 4px;
    background: var(--surface2);
    color: var(--muted);
    border: 1px solid var(--border);
  }

  .project-metric {
    font-size: 11px;
    color: var(--green);
    margin-top: 8px;
    position: relative;
    z-index: 1;
  }

  /* ── TECH GRID ── */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
  }

  .tech-group {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
  }

  .tech-group-title {
    font-size: 10px;
    color: var(--cyan);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  .tech-item {
    font-size: 12px;
    color: var(--muted);
    padding: 3px 0;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .tech-item::before {
    content: '▸';
    color: var(--cyan);
    font-size: 10px;
  }

  /* ── ACHIEVEMENTS ── */
  .achieve-list {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .achieve-item {
    display: flex;
    align-items: center;
    gap: 12px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 12px 16px;
    font-size: 13px;
    transition: all 0.2s;
  }

  .achieve-item:hover {
    border-color: var(--amber);
    background: #f0b42908;
  }

  .achieve-icon { font-size: 20px; }

  .achieve-text { color: var(--text); }
  .achieve-sub  { font-size: 11px; color: var(--muted); margin-top: 2px; }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .stats-img {
    width: 100%;
    border-radius: 10px;
    border: 1px solid var(--border);
  }

  /* ── CONNECT ── */
  .connect-bar {
    display: flex;
    justify-content: center;
    gap: 12px;
    flex-wrap: wrap;
    padding: 28px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    text-align: center;
  }

  .connect-label {
    width: 100%;
    font-size: 12px;
    color: var(--muted);
    margin-bottom: 8px;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  .connect-btn {
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 12px;
    font-family: var(--font-mono);
    font-weight: 500;
    text-decoration: none;
    border: 1px solid;
    transition: all 0.2s;
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }

  .connect-btn:hover { transform: translateY(-2px); }
  .btn-linkedin { color: #0a66c2; border-color: #0a66c2; background: #0a66c211; }
  .btn-linkedin:hover { box-shadow: 0 4px 16px #0a66c233; }
  .btn-email    { color: #ea4335; border-color: #ea4335; background: #ea433511; }
  .btn-email:hover    { box-shadow: 0 4px 16px #ea433533; }
  .btn-portfolio { color: var(--green); border-color: var(--green); background: #3fb95011; }
  .btn-portfolio:hover { box-shadow: 0 4px 16px #3fb95033; }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
  }

  /* stagger delays */
  .section:nth-child(1) { animation-delay: 0.8s; }
  .section:nth-child(2) { animation-delay: 1.0s; }
  .section:nth-child(3) { animation-delay: 1.2s; }
  .section:nth-child(4) { animation-delay: 1.4s; }
  .section:nth-child(5) { animation-delay: 1.6s; }
  .section:nth-child(6) { animation-delay: 1.8s; }
  .section:nth-child(7) { animation-delay: 2.0s; }

  /* ── TYPING CURSOR ── */
  .cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--cyan);
    margin-left: 4px;
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0; }
  }

  @media (max-width: 700px) {
    .hero { grid-template-columns: 1fr; }
    .hero-gif { order: -1; max-width: 280px; margin: 0 auto; }
    .impact-grid { grid-template-columns: repeat(2, 1fr); }
    .projects-grid { grid-template-columns: 1fr; }
    .tech-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr; }
    .title { font-size: 30px; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- ── HERO ── -->
  <div class="hero">
    <div class="hero-left">
      <div class="prompt">$ whoami</div>
      <h1 class="title">Gen AI<br/><span>Engineer</span><span class="cursor"></span></h1>
      <p class="tagline">
        Building enterprise AI systems at <strong style="color:var(--text)">Tata Consultancy Services</strong>.<br/>
        LangChain · RAG · LLMs · Streamlit · Python · React
      </p>
      <div class="badges">
        <a class="badge badge-cyan" href="https://www.linkedin.com/in/anushka-joshi-4097811ba/" target="_blank">LinkedIn</a>
        <a class="badge badge-green" href="https://659d4937b0db3004afe616d9--zingy-licorice-73fe0c.netlify.app/" target="_blank">Portfolio</a>
        <a class="badge badge-amber" href="mailto:joshianushka999@gmail.com">joshianushka999@gmail.com</a>
        <a class="badge badge-cyan" href="https://www.codingninjas.com/studio/profile/Aj999" target="_blank">CodingNinjas</a>
        <a class="badge badge-green" href="https://auth.geeksforgeeks.org/user/joshianushka999" target="_blank">GeeksForGeeks</a>
      </div>
    </div>
    <div class="hero-gif">
      <img src="https://mir-s3-cdn-cf.behance.net/project_modules/disp/601014116770475.6068beff4640a.gif" alt="coding gif"/>
    </div>
  </div>

  <!-- ── WHOAMI CODE BLOCK ── -->
  <div class="code-block">
    <div class="code-header">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
      <span class="code-filename">profile.py</span>
    </div>
    <div class="code-body">
      <span class="c-keyword">class</span> <span class="c-class">Engineer</span>:<br/>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="c-prop">role</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = <span class="c-string">"Gen AI Developer @ Tata Consultancy Services"</span><br/>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="c-prop">location</span>&nbsp;&nbsp;&nbsp; = <span class="c-string">"Haldwani, Uttarakhand 🇮🇳"</span><br/>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="c-prop">education</span>&nbsp;&nbsp; = <span class="c-string">"B.Tech CSE — BIAS | CGPA 8.52"</span><br/>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="c-prop">ai_stack</span>&nbsp;&nbsp;&nbsp; = <span class="c-list">["LangChain", "RAG", "LLMs", "Prompt Engineering", "Pinecone"]</span><br/>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="c-prop">web_stack</span>&nbsp;&nbsp; = <span class="c-list">["React.js", "Node.js", "Streamlit", "MongoDB", "TypeScript"]</span><br/>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="c-prop">currently</span>&nbsp;&nbsp; = <span class="c-string">"Architecting enterprise GenAI at TCS → 40% faster triage"</span><br/>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="c-comment"># Open to: GenAI collaborations, RAG projects, AI product builds</span>
    </div>
  </div>

  <!-- ── IMPACT ── -->
  <div class="section">
    <div class="section-title">TCS Impact Metrics</div>
    <div class="impact-grid">
      <div class="impact-card">
        <span class="impact-num">40%</span>
        <div class="impact-label">Faster ticket triage via LLM dashboard</div>
      </div>
      <div class="impact-card">
        <span class="impact-num">99.9%</span>
        <div class="impact-label">ServiceNow API uptime achieved</div>
      </div>
      <div class="impact-card">
        <span class="impact-num">+25%</span>
        <div class="impact-label">Estimated automation adoption increase</div>
      </div>
      <div class="impact-card">
        <span class="impact-num">∞</span>
        <div class="impact-label">Real-time LLM predictions in prod</div>
      </div>
    </div>
  </div>

  <!-- ── PROJECTS ── -->
  <div class="section">
    <div class="section-title">Featured Projects</div>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-tag">🧠 Gen AI · RAG</div>
        <div class="project-name">Multi-Modal RAG System</div>
        <div class="project-desc">Chat with PDFs, images & CSVs simultaneously. Hybrid BM25 + semantic search with RRF fusion. Completely free stack — Gemini 2.5 Flash + local embeddings.</div>
        <div class="project-stack">
          <span class="stack-pill">Python</span>
          <span class="stack-pill">Gemini</span>
          <span class="stack-pill">Pinecone</span>
          <span class="stack-pill">BGE</span>
          <span class="stack-pill">Streamlit</span>
          <span class="stack-pill">LangChain</span>
        </div>
        <div class="project-metric">🟢 Live relevance scoring · Chat history · Feedback dashboard</div>
      </div>

      <a class="project-card" href="https://github.com/Anushka0902/INVICTA.git" target="_blank">
        <div class="project-tag">🏛️ React · Node · MongoDB</div>
        <div class="project-name">INVICTA</div>
        <div class="project-desc">Government scheme finder — helps citizens find relevant schemes in under 5 seconds. Real-time progress tracking across 12 initiatives.</div>
        <div class="project-stack">
          <span class="stack-pill">React.js</span>
          <span class="stack-pill">Node.js</span>
          <span class="stack-pill">MongoDB</span>
          <span class="stack-pill">React Router</span>
        </div>
        <div class="project-metric">📈 20% engagement boost · 40% fewer API calls</div>
      </a>

      <a class="project-card" href="https://github.com/Anushka0902/Reventa" target="_blank">
        <div class="project-tag">🛍️ Full Stack · E-Commerce</div>
        <div class="project-name">REVENTA</div>
        <div class="project-desc">3-in-1 marketplace integrating Buy, Rent & Resell. Server-side rendering with EJS + lazy loading for 30% faster loads.</div>
        <div class="project-stack">
          <span class="stack-pill">Node.js</span>
          <span class="stack-pill">EJS</span>
          <span class="stack-pill">MongoDB</span>
          <span class="stack-pill">JavaScript</span>
        </div>
        <div class="project-metric">⚡ 30% faster load · 30% more utility vs single-model</div>
      </a>

      <a class="project-card" href="https://github.com/Anushka0902/Ai-summarizer" target="_blank">
        <div class="project-tag">🤖 AI · Utility</div>
        <div class="project-name">AI Summarizer + More</div>
        <div class="project-desc">AI-powered text summarizer. Also: Docstep (healthcare), Tic-Tac-Toe, Box Office App, Anukulak (sustainability platform).</div>
        <div class="project-stack">
          <span class="stack-pill">React.js</span>
          <span class="stack-pill">AI APIs</span>
          <span class="stack-pill">JavaScript</span>
        </div>
        <div class="project-metric">🔗 View all on GitHub →</div>
      </a>

    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <div class="section">
    <div class="section-title">Tech Stack</div>
    <div class="tech-grid">
      <div class="tech-group">
        <div class="tech-group-title">AI / Gen AI</div>
        <div class="tech-item">Python</div>
        <div class="tech-item">LangChain</div>
        <div class="tech-item">LLMs / Prompt Engineering</div>
        <div class="tech-item">RAG Systems</div>
        <div class="tech-item">Gemini · HuggingFace</div>
        <div class="tech-item">Pinecone · Streamlit</div>
        <div class="tech-item">NLP · Predictive Modeling</div>
      </div>
      <div class="tech-group">
        <div class="tech-group-title">Web Development</div>
        <div class="tech-item">React.js</div>
        <div class="tech-item">TypeScript · JavaScript ES6</div>
        <div class="tech-item">Node.js</div>
        <div class="tech-item">HTML5 · CSS3</div>
        <div class="tech-item">Bootstrap</div>
        <div class="tech-item">C++ · DSA</div>
        <div class="tech-item">Next.js</div>
      </div>
      <div class="tech-group">
        <div class="tech-group-title">Data & Cloud</div>
        <div class="tech-item">MongoDB (NoSQL)</div>
        <div class="tech-item">SQL</div>
        <div class="tech-item">Azure Cloud Services</div>
        <div class="tech-item">Firebase</div>
        <div class="tech-item">Git · GitHub</div>
        <div class="tech-item">npm · Yarn</div>
        <div class="tech-item">VS Code · Canva</div>
      </div>
    </div>
  </div>

  <!-- ── ACHIEVEMENTS ── -->
  <div class="section">
    <div class="section-title">Achievements</div>
    <div class="achieve-list">
      <div class="achieve-item">
        <span class="achieve-icon">🥇</span>
        <div>
          <div class="achieve-text">1st Position — University SOCIO-HACKATHON</div>
          <div class="achieve-sub">Birla Institute of Applied Sciences</div>
        </div>
      </div>
      <div class="achieve-item">
        <span class="achieve-icon">🔬</span>
        <div>
          <div class="achieve-text">Top 50 Teams — NIT Srinagar State-Level Project Competition</div>
          <div class="achieve-sub">Selected among top 50 teams at state level</div>
        </div>
      </div>
      <div class="achieve-item">
        <span class="achieve-icon">🚀</span>
        <div>
          <div class="achieve-text">Startup Uttarakhand Grand Challenge 2022–23</div>
          <div class="achieve-sub">Organized by Government of India</div>
        </div>
      </div>
    </div>
  </div>

  <!-- ── STATS ── -->
  <div class="section">
    <div class="section-title">GitHub Stats</div>
    <div class="stats-row">
      <img class="stats-img" src="https://github-readme-stats.vercel.app/api?username=anushka0902&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="GitHub Stats"/>
      <img class="stats-img" src="https://github-readme-stats.vercel.app/api/top-langs/?username=anushka0902&layout=compact&theme=tokyonight&hide_border=true" alt="Top Languages"/>
    </div>
    <img class="stats-img" style="margin-top:16px;" src="https://github-readme-streak-stats.herokuapp.com/?user=anushka0902&theme=tokyonight&hide_border=true" alt="Streak"/>
  </div>

  <!-- ── CONNECT ── -->
  <div class="section">
    <div class="connect-bar">
      <div class="connect-label">Currently building AI systems that scale — open to GenAI collaborations</div>
      <a class="connect-btn btn-linkedin" href="https://www.linkedin.com/in/anushka-joshi-4097811ba/" target="_blank">💼 LinkedIn</a>
      <a class="connect-btn btn-email" href="mailto:joshianushka999@gmail.com">✉️ Email</a>
      <a class="connect-btn btn-portfolio" href="https://659d4937b0db3004afe616d9--zingy-licorice-73fe0c.netlify.app/" target="_blank">🌐 Portfolio</a>
    </div>
  </div>

</div>
</body>
</html>
