<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Kartik Singh — AI Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=JetBrains+Mono:wght@300;400;600&family=Space+Grotesk:wght@300;400;600&display=swap" rel="stylesheet" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css" />
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --c1: #00f7ff;
    --c2: #bf00ff;
    --c3: #00ff88;
    --dark: #060a10;
    --panel: #0a1020;
    --border: rgba(0,247,255,0.15);
  }

  body {
    font-family: 'Space Grotesk', sans-serif;
    background: #060a10;
    color: #c8d8e8;
    min-height: 100vh;
    position: relative;
    overflow-x: hidden;
  }

  .grid-bg {
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,247,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,247,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .scanline {
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.08) 2px,
      rgba(0,0,0,0.08) 4px
    );
    pointer-events: none;
    z-index: 1;
  }

  .content {
    position: relative;
    z-index: 2;
    max-width: 860px;
    margin: 0 auto;
    padding: 2rem 1.5rem 4rem;
  }

  /* HERO */
  .hero {
    text-align: center;
    padding: 3.5rem 0 2.5rem;
    position: relative;
  }

  .hero-ring {
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 50%;
    border: 1px solid rgba(0,247,255,0.08);
    pointer-events: none;
  }
  .hero-ring:nth-child(1) { width: 340px; height: 340px; animation: pulse-ring 4s ease-in-out infinite; }
  .hero-ring:nth-child(2) { width: 500px; height: 500px; animation: pulse-ring 4s ease-in-out infinite 1.3s; }
  .hero-ring:nth-child(3) { width: 660px; height: 660px; animation: pulse-ring 4s ease-in-out infinite 2.6s; }

  @keyframes pulse-ring {
    0%, 100% { opacity: 0.5; transform: translate(-50%, -50%) scale(1); }
    50% { opacity: 0.1; transform: translate(-50%, -50%) scale(1.02); }
  }

  .status-dots {
    display: flex;
    justify-content: center;
    gap: 0.5rem;
    margin-bottom: 1.5rem;
  }

  .dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    animation: dot-pulse 2s ease-in-out infinite;
  }
  .dot:nth-child(1) { background: var(--c1); animation-delay: 0s; }
  .dot:nth-child(2) { background: var(--c2); animation-delay: 0.4s; }
  .dot:nth-child(3) { background: var(--c3); animation-delay: 0.8s; }

  @keyframes dot-pulse {
    0%, 100% { transform: scale(1); opacity: 1; }
    50% { transform: scale(1.6); opacity: 0.4; }
  }

  .name-badge {
    display: inline-block;
    font-family: 'Orbitron', monospace;
    font-size: clamp(2rem, 6vw, 3.5rem);
    font-weight: 900;
    letter-spacing: 0.08em;
    background: linear-gradient(135deg, #00f7ff 0%, #bf00ff 50%, #00ff88 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 0.75rem;
    animation: name-glow 3s ease-in-out infinite alternate;
  }

  @keyframes name-glow {
    from { filter: drop-shadow(0 0 20px rgba(0,247,255,0.3)); }
    to   { filter: drop-shadow(0 0 40px rgba(191,0,255,0.5)); }
  }

  .role-line {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--c1);
    letter-spacing: 0.12em;
    opacity: 0.8;
    margin-bottom: 1.5rem;
    animation: blink-role 2s step-end infinite;
  }

  @keyframes blink-role {
    0%, 100% { opacity: 0.8; }
    50% { opacity: 0.4; }
  }

  /* LAYOUT HELPERS */
  .separator {
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,247,255,0.2), transparent);
    margin: 1.75rem 0;
  }

  .section { margin: 2rem 0; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 1rem;
  }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.2em;
    color: var(--c1);
    white-space: nowrap;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(0,247,255,0.35), transparent);
  }

  /* PANEL */
  .panel {
    background: rgba(10,16,32,0.9);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.25rem 1.5rem;
    position: relative;
    overflow: hidden;
  }

  .panel::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--c1), transparent);
    opacity: 0.4;
  }

  .corner { position: absolute; width: 12px; height: 12px; }
  .corner-tl { top: -1px; left: -1px; border-top: 2px solid var(--c1); border-left: 2px solid var(--c1); }
  .corner-tr { top: -1px; right: -1px; border-top: 2px solid var(--c1); border-right: 2px solid var(--c1); }
  .corner-bl { bottom: -1px; left: -1px; border-bottom: 2px solid var(--c1); border-left: 2px solid var(--c1); }
  .corner-br { bottom: -1px; right: -1px; border-bottom: 2px solid var(--c1); border-right: 2px solid var(--c1); }

  /* YAML */
  .yaml-block {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    line-height: 1.9;
  }
  .yaml-key  { color: var(--c1); }
  .yaml-val  { color: #a0c0d0; }
  .yaml-list { color: var(--c3); }

  .code-cursor {
    display: inline-block;
    width: 2px; height: 13px;
    background: var(--c1);
    animation: blink 1s step-end infinite;
    vertical-align: middle;
    margin-left: 3px;
  }
  @keyframes blink { 50% { opacity: 0; } }

  /* TAGS */
  .tags-grid { display: flex; flex-wrap: wrap; gap: 0.5rem; }

  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    padding: 0.3rem 0.75rem;
    border-radius: 2px;
    letter-spacing: 0.05em;
    cursor: default;
    transition: all 0.2s;
  }
  .tag:hover { transform: translateY(-2px); box-shadow: 0 4px 16px rgba(0,247,255,0.2); }
  .tag-cyan   { background: rgba(0,247,255,0.08);  border: 1px solid rgba(0,247,255,0.3);  color: var(--c1); }
  .tag-purple { background: rgba(191,0,255,0.08);  border: 1px solid rgba(191,0,255,0.3);  color: #d080ff; }
  .tag-green  { background: rgba(0,255,136,0.08);  border: 1px solid rgba(0,255,136,0.3);  color: var(--c3); }

  /* AI STACK CARDS */
  .ai-stack {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 0.75rem;
  }

  .ai-card {
    background: rgba(5,10,20,0.8);
    border: 1px solid rgba(0,247,255,0.1);
    border-radius: 3px;
    padding: 0.75rem;
    text-align: center;
    transition: all 0.25s;
    cursor: default;
  }
  .ai-card:hover {
    border-color: var(--c1);
    background: rgba(0,247,255,0.05);
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(0,247,255,0.15);
  }
  .ai-card-name { font-family: 'JetBrains Mono', monospace; font-size: 0.72rem; font-weight: 600; color: var(--c1); letter-spacing: 0.05em; }
  .ai-card-type { font-size: 0.62rem; color: rgba(200,216,232,0.4); margin-top: 2px; }
  .ai-card-bar  { height: 2px; margin-top: 8px; border-radius: 1px; background: rgba(0,247,255,0.12); overflow: hidden; }
  .ai-card-fill { height: 100%; border-radius: 1px; background: linear-gradient(90deg, var(--c1), var(--c2)); animation: fill-bar 2s ease-out forwards; }
  @keyframes fill-bar { from { width: 0%; } }

  /* CODE BLOCK */
  .code-block {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
    line-height: 2;
  }
  .code-line { display: flex; gap: 1rem; }
  .code-num  { color: rgba(0,247,255,0.2); min-width: 1.5rem; user-select: none; }
  .code-kw   { color: #d080ff; }
  .code-fn   { color: var(--c1); }
  .code-op   { color: #888; }
  .code-str  { color: var(--c3); }

  /* STATS */
  .stats-row { display: grid; grid-template-columns: 1fr 1fr; gap: 0.75rem; }
  .stat-img-wrap { border: 1px solid var(--border); border-radius: 3px; overflow: hidden; background: rgba(10,16,32,0.9); padding: 4px; }
  .stat-img-wrap img { width: 100%; display: block; border-radius: 2px; }

  /* QUOTE */
  .quote-panel { text-align: center; padding: 2rem 2.5rem; position: relative; }
  .quote-text { font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; line-height: 2; color: rgba(200,216,232,0.7); }
  .quote-text strong { color: var(--c1); font-weight: 600; }
  .quote-marks { font-family: 'Orbitron', monospace; font-size: 3rem; color: rgba(0,247,255,0.1); line-height: 0; position: absolute; }
  .qm-open  { top: 1.5rem; left: 1.5rem; }
  .qm-close { bottom: 1rem; right: 1.5rem; }

  /* PROJECT */
  .project-label {
    position: absolute;
    top: -0.65rem; left: 1rem;
    font-family: 'Orbitron', monospace;
    font-size: 0.6rem;
    letter-spacing: 0.2em;
    color: var(--c2);
    background: #060a10;
    padding: 0 0.5rem;
  }
  .project-title { font-family: 'Orbitron', monospace; font-size: 1.1rem; color: var(--c1); margin-bottom: 0.4rem; margin-top: 0.4rem; }
  .project-desc  { font-size: 0.82rem; color: rgba(200,216,232,0.6); line-height: 1.7; }

  /* CONNECT */
  .connect-row { display: flex; gap: 0.75rem; flex-wrap: wrap; justify-content: center; }

  .connect-btn {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.1em;
    padding: 0.6rem 1.2rem;
    border-radius: 2px;
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: all 0.2s;
    border: none;
  }
  .connect-btn:hover { transform: translateY(-2px); filter: brightness(1.25); box-shadow: 0 6px 20px rgba(0,247,255,0.2); }
  .btn-linkedin  { background: rgba(0,200,255,0.1);  border: 1px solid rgba(0,200,255,0.4);  color: var(--c1); }
  .btn-instagram { background: rgba(191,0,255,0.1);  border: 1px solid rgba(191,0,255,0.4);  color: #d080ff; }
  .btn-email     { background: rgba(0,255,136,0.1);  border: 1px solid rgba(0,255,136,0.4);  color: var(--c3); }

  /* FOOTER */
  .footer {
    text-align: center;
    padding: 2rem 0 1rem;
    font-family: 'Orbitron', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.25em;
    color: rgba(0,247,255,0.4);
  }

  @media (max-width: 560px) {
    .stats-row { grid-template-columns: 1fr; }
    .hero-ring:nth-child(2), .hero-ring:nth-child(3) { display: none; }
  }
</style>
</head>
<body>

<div class="grid-bg"></div>
<div class="scanline"></div>

<div class="content">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-ring"></div>
    <div class="hero-ring"></div>
    <div class="hero-ring"></div>

    <div class="status-dots">
      <div class="dot"></div>
      <div class="dot"></div>
      <div class="dot"></div>
    </div>

    <div class="name-badge">KARTIK SINGH</div>
    <div class="role-line">[ FULL STACK DEV ⚡ AI ENGINEER ⚡ AGENT BUILDER ]</div>

    <div class="tags-grid" style="justify-content:center; margin-top:1rem;">
      <span class="tag tag-cyan">LangGraph</span>
      <span class="tag tag-purple">LLMs</span>
      <span class="tag tag-green">RAG Pipelines</span>
      <span class="tag tag-cyan">Agentic AI</span>
      <span class="tag tag-purple">Multi-Agent</span>
      <span class="tag tag-green">Full Stack</span>
    </div>
  </div>

  <div class="separator"></div>

  <!-- IDENTITY -->
  <div class="section">
    <div class="section-header">
      <span class="section-title">// identity.yaml</span>
      <div class="section-line"></div>
    </div>
    <div class="panel">
      <div class="corner corner-tl"></div>
      <div class="corner corner-tr"></div>
      <div class="corner corner-bl"></div>
      <div class="corner corner-br"></div>
      <div class="yaml-block">
        <div><span class="yaml-key">name: </span><span class="yaml-val">Kartik Singh</span></div>
        <div><span class="yaml-key">role: </span><span class="yaml-val">Full Stack Developer + AI Engineer</span></div>
        <div><span class="yaml-key">focus:</span></div>
        <div style="padding-left:1.5rem"><span class="yaml-list">→ </span><span class="yaml-val">Agentic AI Systems</span></div>
        <div style="padding-left:1.5rem"><span class="yaml-list">→ </span><span class="yaml-val">LLM Applications &amp; RAG Pipelines</span></div>
        <div style="padding-left:1.5rem"><span class="yaml-list">→ </span><span class="yaml-val">Scalable Backend Systems</span></div>
        <div style="padding-left:1.5rem"><span class="yaml-list">→ </span><span class="yaml-val">AI Automation</span></div>
        <div><span class="yaml-key">currently_building:</span></div>
        <div style="padding-left:1.5rem"><span class="yaml-list">→ </span><span class="yaml-val">Inter IIT Pathway Project</span></div>
        <div style="padding-left:1.5rem"><span class="yaml-list">→ </span><span class="yaml-val">LangGraph AI Agents</span></div>
        <div><span class="yaml-key">status: </span><span class="yaml-list">ONLINE</span><span class="code-cursor"></span></div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-header">
      <span class="section-title">// tech.stack</span>
      <div class="section-line"></div>
    </div>
    <div class="tags-grid">
      <span class="tag tag-cyan">C++</span>
      <span class="tag tag-cyan">Python</span>
      <span class="tag tag-cyan">JavaScript</span>
      <span class="tag tag-cyan">React</span>
      <span class="tag tag-cyan">Node.js</span>
      <span class="tag tag-cyan">MongoDB</span>
      <span class="tag tag-cyan">HTML / CSS</span>
      <span class="tag tag-cyan">Git</span>
      <span class="tag tag-cyan">GitHub</span>
      <span class="tag tag-cyan">VS Code</span>
    </div>
  </div>

  <!-- AI STACK -->
  <div class="section">
    <div class="section-header">
      <span class="section-title">// ai_ml.modules</span>
      <div class="section-line"></div>
    </div>
    <div class="ai-stack">
      <div class="ai-card">
        <div class="ai-card-name">PyTorch</div>
        <div class="ai-card-type">Deep Learning</div>
        <div class="ai-card-bar"><div class="ai-card-fill" style="width:85%"></div></div>
      </div>
      <div class="ai-card">
        <div class="ai-card-name">LangChain</div>
        <div class="ai-card-type">LLM Framework</div>
        <div class="ai-card-bar"><div class="ai-card-fill" style="width:90%"></div></div>
      </div>
      <div class="ai-card">
        <div class="ai-card-name">LangGraph</div>
        <div class="ai-card-type">Agent Orchestration</div>
        <div class="ai-card-bar"><div class="ai-card-fill" style="width:80%"></div></div>
      </div>
      <div class="ai-card">
        <div class="ai-card-name">LlamaIndex</div>
        <div class="ai-card-type">RAG Framework</div>
        <div class="ai-card-bar"><div class="ai-card-fill" style="width:75%"></div></div>
      </div>
      <div class="ai-card">
        <div class="ai-card-name">NumPy</div>
        <div class="ai-card-type">Numerical</div>
        <div class="ai-card-bar"><div class="ai-card-fill" style="width:88%"></div></div>
      </div>
      <div class="ai-card">
        <div class="ai-card-name">Pandas</div>
        <div class="ai-card-type">Data Analysis</div>
        <div class="ai-card-bar"><div class="ai-card-fill" style="width:82%"></div></div>
      </div>
      <div class="ai-card">
        <div class="ai-card-name">Matplotlib</div>
        <div class="ai-card-type">Visualization</div>
        <div class="ai-card-bar"><div class="ai-card-fill" style="width:70%"></div></div>
      </div>
    </div>
  </div>

  <!-- FEATURED PROJECT -->
  <div class="section">
    <div class="section-header">
      <span class="section-title">// featured.project</span>
      <div class="section-line"></div>
    </div>
    <div class="panel" style="position:relative;">
      <div class="corner corner-tl"></div>
      <div class="corner corner-tr"></div>
      <div class="corner corner-bl"></div>
      <div class="corner corner-br"></div>
      <div class="project-label">INTER IIT · ACTIVE</div>
      <div class="project-title">🛣️ Pathway Project</div>
      <div class="project-desc">Building intelligent AI-powered systems using modern agentic frameworks and scalable architectures. Pushing boundaries with LangGraph &amp; multi-agent orchestration.</div>
      <div style="margin-top:1rem;">
        <div class="code-line"><span class="code-num">1</span><span><span class="code-kw">while</span><span class="code-op">(</span><span class="code-str">True</span><span class="code-op">):</span></span></div>
        <div class="code-line"><span class="code-num">2</span><span style="padding-left:1.5rem"><span class="code-fn">build</span><span class="code-op">()</span></span></div>
        <div class="code-line"><span class="code-num">3</span><span style="padding-left:1.5rem"><span class="code-fn">learn</span><span class="code-op">()</span></span></div>
        <div class="code-line"><span class="code-num">4</span><span style="padding-left:1.5rem"><span class="code-fn">innovate</span><span class="code-op">()</span></span></div>
      </div>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-header">
      <span class="section-title">// github.stats</span>
      <div class="section-line"></div>
    </div>
    <div class="stats-row">
      <div class="stat-img-wrap">
        <img
          src="https://github-readme-stats.vercel.app/api?username=kartikssingh&show_icons=true&theme=tokyonight&hide_border=true&bg_color=060a10&title_color=00f7ff&icon_color=bf00ff&text_color=c8d8e8&ring_color=00ff88"
          alt="GitHub Stats"
        />
      </div>
      <div class="stat-img-wrap">
        <img
          src="https://github-readme-stats.vercel.app/api/top-langs/?username=kartikssingh&layout=compact&theme=tokyonight&hide_border=true&bg_color=060a10&title_color=00f7ff&text_color=c8d8e8"
          alt="Top Languages"
        />
      </div>
    </div>
    <div style="margin-top:0.75rem;" class="stat-img-wrap">
      <img
        src="https://streak-stats.demolab.com?user=kartikssingh&theme=tokyonight&hide_border=true&background=060a10&ring=00f7ff&fire=bf00ff&currStreakLabel=00ff88&sideLabels=c8d8e8"
        alt="GitHub Streak"
        style="width:100%;"
      />
    </div>
  </div>

  <!-- AI QUOTE -->
  <div class="section">
    <div class="section-header">
      <span class="section-title">// ai.quote</span>
      <div class="section-line"></div>
    </div>
    <div class="panel quote-panel">
      <div class="corner corner-tl"></div>
      <div class="corner corner-tr"></div>
      <div class="corner corner-bl"></div>
      <div class="corner corner-br"></div>
      <span class="quote-marks qm-open">"</span>
      <div class="quote-text">
        AI won't replace developers.<br>
        <strong>Developers using AI</strong> will replace those who don't.
      </div>
      <span class="quote-marks qm-close">"</span>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section">
    <div class="section-header">
      <span class="section-title">// connect.init()</span>
      <div class="section-line"></div>
    </div>
    <div class="connect-row">
      <a href="https://www.linkedin.com/in/kartik-singh-25a550376" class="connect-btn btn-linkedin" target="_blank" rel="noopener">
        LinkedIn ↗
      </a>
      <a href="https://www.instagram.com/kartik_vi_ss" class="connect-btn btn-instagram" target="_blank" rel="noopener">
        Instagram ↗
      </a>
      <a href="mailto:YOUR_EMAIL@gmail.com" class="connect-btn btn-email">
        Email ↗
      </a>
    </div>
  </div>

  <div class="separator"></div>

  <!-- FOOTER -->
  <div class="footer">
    <div>⚡ BUILDING THE FUTURE WITH AI ⚡</div>
    <div style="margin-top:0.75rem;">
      <img src="https://komarev.com/ghpvc/?username=kartikssingh&color=00f7ff&style=flat-square&label=VISITORS" alt="Visitor count" />
    </div>
  </div>

</div><!-- /content -->
</body>
</html>
