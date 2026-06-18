<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Mohamed Waheed – GitHub Profile Preview</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg:        #0d1117;
    --surface:   #161b22;
    --border:    #21262d;
    --red:       #FF2D20;
    --red-dim:   #7a1510;
    --text:      #c9d1d9;
    --muted:     #8b949e;
    --white:     #f0f6fc;
    --mono:      'JetBrains Mono', monospace;
    --sans:      'Inter', sans-serif;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    min-height: 100vh;
    padding: 0;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    overflow: hidden;
    padding: 56px 32px 48px;
    text-align: center;
    border-bottom: 1px solid var(--border);
    background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(255,45,32,.12) 0%, transparent 70%);
  }

  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: repeating-linear-gradient(0deg, transparent, transparent 39px, rgba(255,45,32,.04) 40px),
                repeating-linear-gradient(90deg, transparent, transparent 39px, rgba(255,45,32,.04) 40px);
    pointer-events: none;
  }

  .ascii {
    font-family: var(--mono);
    font-size: clamp(4px, 1.2vw, 11px);
    line-height: 1.15;
    color: var(--red);
    letter-spacing: .05em;
    white-space: pre;
    display: inline-block;
    margin-bottom: 28px;
    text-shadow: 0 0 18px rgba(255,45,32,.5);
    animation: flicker 6s ease-in-out infinite;
  }

  @keyframes flicker {
    0%,100%  { opacity: 1; }
    92%      { opacity: 1; }
    93%      { opacity: .6; }
    94%      { opacity: 1; }
    96%      { opacity: .8; }
    97%      { opacity: 1; }
  }

  .hero-name {
    font-family: var(--mono);
    font-size: clamp(22px, 4vw, 36px);
    font-weight: 700;
    color: var(--white);
    letter-spacing: -.01em;
  }

  .hero-name span { color: var(--red); }

  .hero-role {
    font-size: 13px;
    color: var(--muted);
    letter-spacing: .18em;
    text-transform: uppercase;
    margin-top: 8px;
    font-family: var(--mono);
  }

  .hero-badges {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 24px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 6px 14px;
    border-radius: 6px;
    font-family: var(--mono);
    font-size: 12px;
    font-weight: 600;
    letter-spacing: .05em;
    border: 1px solid var(--border);
    transition: border-color .2s, box-shadow .2s;
    text-decoration: none;
  }

  .badge:hover { border-color: var(--red); box-shadow: 0 0 12px rgba(255,45,32,.2); }

  .badge-laravel  { background: rgba(255,45,32,.1);  color: #FF2D20; }
  .badge-php      { background: rgba(119,107,180,.1); color: #a78bfa; }
  .badge-fastapi  { background: rgba(0,150,136,.1);  color: #4dd0c4; }
  .badge-python   { background: rgba(55,118,171,.1); color: #60a5fa; }
  .badge-li       { background: rgba(10,102,194,.1); color: #60a5fa; }
  .badge-java     { background: rgba(237,139,0,.1);  color: #fbbf24; }

  /* ── LAYOUT ── */
  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    display: flex;
    flex-direction: column;
    gap: 40px;
  }

  /* ── SECTION ── */
  .section { border: 1px solid var(--border); border-radius: 12px; overflow: hidden; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 14px 20px;
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    font-family: var(--mono);
    font-size: 13px;
    color: var(--muted);
  }

  .section-header .cmd { color: var(--red); }
  .section-header .filename { color: var(--text); }

  .section-body { padding: 24px 20px; }

  /* ── WHO AM I CODE BLOCK ── */
  .code-block {
    background: #010409;
    border-radius: 8px;
    padding: 20px 24px;
    font-family: var(--mono);
    font-size: 13px;
    line-height: 1.9;
    overflow-x: auto;
  }

  .c-kw   { color: #ff7b72; }
  .c-cls  { color: #79c0ff; }
  .c-str  { color: #a5d6ff; }
  .c-prop { color: #d2a8ff; }
  .c-val  { color: #a5d6ff; }
  .c-ns   { color: #ffa657; }
  .c-cmt  { color: #8b949e; font-style: italic; }
  .c-fn   { color: #d2a8ff; }

  /* ── TECH GRID ── */
  .tech-category { margin-bottom: 22px; }
  .tech-category:last-child { margin-bottom: 0; }

  .tech-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--red);
    letter-spacing: .15em;
    text-transform: uppercase;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .tech-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .chips {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .chip {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 12px;
    border-radius: 20px;
    border: 1px solid var(--border);
    background: var(--surface);
    font-size: 12px;
    font-family: var(--mono);
    color: var(--text);
    transition: all .18s;
    cursor: default;
  }

  .chip:hover {
    border-color: var(--red);
    background: rgba(255,45,32,.06);
    color: var(--white);
    transform: translateY(-1px);
  }

  .chip img { display: block; }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media (max-width: 560px) { .stats-grid { grid-template-columns: 1fr; } }

  .stat-card {
    background: #010409;
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    font-family: var(--mono);
  }

  .stat-title {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: .12em;
    text-transform: uppercase;
    margin-bottom: 14px;
  }

  .stat-bar-wrap { margin-bottom: 10px; }

  .stat-bar-label {
    display: flex;
    justify-content: space-between;
    font-size: 11px;
    color: var(--text);
    margin-bottom: 5px;
  }

  .stat-bar-track {
    height: 5px;
    background: var(--border);
    border-radius: 99px;
    overflow: hidden;
  }

  .stat-bar-fill {
    height: 100%;
    background: var(--red);
    border-radius: 99px;
    animation: grow .9s ease both;
  }

  @keyframes grow { from { width: 0 !important; } }

  .stat-numbers {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .stat-num-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 12px;
  }

  .stat-num-row .label { color: var(--muted); }
  .stat-num-row .val   { color: var(--white); font-weight: 600; }
  .stat-num-row .val.red { color: var(--red); }

  /* ── QUOTE ── */
  .quote-box {
    text-align: center;
    padding: 32px 24px;
    font-family: var(--mono);
    border: 1px solid var(--red-dim);
    border-radius: 12px;
    background: rgba(255,45,32,.04);
    position: relative;
  }

  .quote-box::before {
    content: '"';
    position: absolute;
    top: -20px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 56px;
    color: var(--red);
    line-height: 1;
    font-family: Georgia, serif;
  }

  .quote-text {
    font-size: 14px;
    color: var(--text);
    line-height: 1.7;
  }

  .quote-author {
    font-size: 11px;
    color: var(--muted);
    margin-top: 12px;
    letter-spacing: .1em;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 24px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    border-top: 1px solid var(--border);
  }

  .footer span { color: var(--red); }

  /* ── WINDOW DOTS ── */
  .dots { display: flex; gap: 6px; }
  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #ff5f56; }
  .dot-y { background: #ffbd2e; }
  .dot-g { background: #27c93f; }
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="ascii">
██╗    ██╗ █████╗ ██╗  ██╗███████╗███████╗██████╗
██║    ██║██╔══██╗██║  ██║██╔════╝██╔════╝██╔══██╗
██║ █╗ ██║███████║███████║█████╗  █████╗  ██║  ██║
██║███╗██║██╔══██║██╔══██║██╔══╝  ██╔══╝  ██║  ██║
╚███╔███╔╝██║  ██║██║  ██║███████╗███████╗██████╔╝
 ╚══╝╚══╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚══════╝╚═════╝</div>

  <div class="hero-name">Mohamed <span>Waheed</span></div>
  <div class="hero-role">Backend Engineer · Laravel · API Architect</div>

  <div class="hero-badges">
    <a class="badge badge-li" href="https://www.linkedin.com/in/mohamed-waheed-b72833209" target="_blank">
      <svg width="14" height="14" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
      LinkedIn
    </a>
    <span class="badge badge-laravel">
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/laravel/laravel-plain.svg" width="14" height="14"/> Laravel
    </span>
    <span class="badge badge-php">
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" width="14" height="14"/> PHP
    </span>
    <span class="badge badge-fastapi">
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/fastapi/fastapi-original.svg" width="14" height="14"/> FastAPI
    </span>
    <span class="badge badge-python">
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="14" height="14"/> Python
    </span>
    <span class="badge badge-java">
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" width="14" height="14"/> Java
    </span>
  </div>
</div>

<div class="container">

  <!-- WHO AM I -->
  <div class="section">
    <div class="section-header">
      <div class="dots"><div class="dot dot-r"></div><div class="dot dot-y"></div><div class="dot dot-g"></div></div>
      <span class="cmd">$</span>
      <span class="filename">whoami.php</span>
    </div>
    <div class="section-body">
      <div class="code-block">
<span class="c-cmt">// Mohamed Waheed — Backend Engineer</span>

<span class="c-kw">namespace</span> <span class="c-ns">App\Engineers</span>;

<span class="c-kw">class</span> <span class="c-cls">MohamedWaheed</span> <span class="c-kw">extends</span> <span class="c-cls">BackendEngineer</span>
{
  <span class="c-kw">public</span> <span class="c-cls">string</span> <span class="c-prop">$role</span>      = <span class="c-val">'Backend Developer'</span>;
  <span class="c-kw">public</span> <span class="c-cls">string</span> <span class="c-prop">$stack</span>     = <span class="c-val">'Laravel · FastAPI · PostgreSQL'</span>;
  <span class="c-kw">public</span> <span class="c-cls">string</span> <span class="c-prop">$focus</span>     = <span class="c-val">'Clean APIs · Scalable Systems'</span>;
  <span class="c-kw">public</span> <span class="c-cls">array</span>  <span class="c-prop">$learning</span>  = [<span class="c-val">'Microservices'</span>, <span class="c-val">'Docker'</span>];
  <span class="c-kw">public</span> <span class="c-cls">string</span> <span class="c-prop">$location</span>  = <span class="c-val">'🇪🇬 Egypt'</span>;

  <span class="c-kw">public function</span> <span class="c-fn">contact</span>(): <span class="c-cls">string</span>
  {
    <span class="c-kw">return</span> <span class="c-val">'linkedin.com/in/mohamed-waheed-b72833209'</span>;
  }
}
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-header">
      <div class="dots"><div class="dot dot-r"></div><div class="dot dot-y"></div><div class="dot dot-g"></div></div>
      <span class="cmd">$</span>
      <span class="filename">ls tech-stack/</span>
    </div>
    <div class="section-body">

      <div class="tech-category">
        <div class="tech-label">⚙ Backend & Frameworks</div>
        <div class="chips">
          <div class="chip"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Laravel.svg/64px-Laravel.svg.png" width="14" height="14"/> Laravel</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/fastapi/fastapi-original.svg" width="14" height="14"/> FastAPI</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" width="14" height="14"/> PHP</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="14" height="14"/> Python</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" width="14" height="14"/> Java</div>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-label">🗄 Databases</div>
        <div class="chips">
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" width="14" height="14"/> PostgreSQL</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" width="14" height="14"/> MySQL</div>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-label">🔬 Data & Computer Vision</div>
        <div class="chips">
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg" width="14" height="14"/> OpenCV</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg" width="14" height="14"/> NumPy</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kaggle/kaggle-original.svg" width="14" height="14"/> Kaggle</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jupyter/jupyter-original.svg" width="14" height="14"/> Jupyter</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/anaconda/anaconda-original.svg" width="14" height="14"/> Anaconda</div>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-label">🛠 DevTools</div>
        <div class="chips">
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" width="14" height="14"/> Git</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" width="14" height="14"/> GitHub</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/apache/apache-original.svg" width="14" height="14"/> Apache</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" width="14" height="14"/> VS Code</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/intellij/intellij-original.svg" width="14" height="14"/> IntelliJ</div>
          <div class="chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg" width="14" height="14"/> Figma</div>
        </div>
      </div>

    </div>
  </div>

  <!-- FAKE STATS -->
  <div class="section">
    <div class="section-header">
      <div class="dots"><div class="dot dot-r"></div><div class="dot dot-y"></div><div class="dot dot-g"></div></div>
      <span class="cmd">$</span>
      <span class="filename">cat github-stats.log</span>
    </div>
    <div class="section-body">
      <div class="stats-grid">

        <div class="stat-card">
          <div class="stat-title">Top Languages</div>
          <div class="stat-bar-wrap">
            <div class="stat-bar-label"><span>PHP / Laravel</span><span>55%</span></div>
            <div class="stat-bar-track"><div class="stat-bar-fill" style="width:55%"></div></div>
          </div>
          <div class="stat-bar-wrap">
            <div class="stat-bar-label"><span>Python</span><span>25%</span></div>
            <div class="stat-bar-track"><div class="stat-bar-fill" style="width:25%; background:#3776AB"></div></div>
          </div>
          <div class="stat-bar-wrap">
            <div class="stat-bar-label"><span>Java</span><span>12%</span></div>
            <div class="stat-bar-track"><div class="stat-bar-fill" style="width:12%; background:#fbbf24"></div></div>
          </div>
          <div class="stat-bar-wrap">
            <div class="stat-bar-label"><span>Other</span><span>8%</span></div>
            <div class="stat-bar-track"><div class="stat-bar-fill" style="width:8%; background:#8b949e"></div></div>
          </div>
        </div>

        <div class="stat-card">
          <div class="stat-title">Profile Highlights</div>
          <div class="stat-numbers">
            <div class="stat-num-row">
              <span class="label">Total Commits</span>
              <span class="val red">247+</span>
            </div>
            <div class="stat-num-row">
              <span class="label">Repositories</span>
              <span class="val">18</span>
            </div>
            <div class="stat-num-row">
              <span class="label">Current Streak</span>
              <span class="val red">🔥 Active</span>
            </div>
            <div class="stat-num-row">
              <span class="label">Focus</span>
              <span class="val">Backend APIs</span>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="quote-box">
    <div class="quote-text">First, solve the problem. Then, write the code.</div>
    <div class="quote-author">— John Johnson</div>
  </div>

</div>

<!-- FOOTER -->
<div class="footer">
  <span>■</span> Mohamed Waheed · Backend Engineer · Egypt &nbsp;|&nbsp; Built with Laravel &hearts; &nbsp;<span>■</span>
</div>

</body>
</html>
