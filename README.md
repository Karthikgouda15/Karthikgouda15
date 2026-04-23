<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Karthik Gouda — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;700&family=Unbounded:wght@400;700;900&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg: #020408;
  --bg2: #060d18;
  --accent: #00d4ff;
  --accent2: #7c3aed;
  --accent3: #f59e0b;
  --green: #10b981;
  --text: #e2e8f0;
  --muted: #64748b;
  --card: rgba(6, 20, 40, 0.8);
  --border: rgba(0, 212, 255, 0.15);
  --glow: 0 0 20px rgba(0,212,255,0.3);
}

* { margin:0; padding:0; box-sizing:border-box; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Space Grotesk', sans-serif;
  overflow-x: hidden;
  min-height: 100vh;
}

/* STARS BACKGROUND */
#stars-canvas {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  z-index: 0;
  pointer-events: none;
}

.content {
  position: relative;
  z-index: 1;
  max-width: 900px;
  margin: 0 auto;
  padding: 40px 24px 80px;
}

/* ── HERO ── */
.hero {
  text-align: center;
  padding: 60px 0 40px;
  position: relative;
}

.hero-orbit {
  position: relative;
  width: 180px;
  height: 180px;
  margin: 0 auto 32px;
}

.avatar-ring {
  width: 180px;
  height: 180px;
  border-radius: 50%;
  border: 2px solid rgba(0,212,255,0.4);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  animation: ring-pulse 3s ease-in-out infinite;
}

@keyframes ring-pulse {
  0%,100% { box-shadow: 0 0 20px rgba(0,212,255,0.3), 0 0 60px rgba(0,212,255,0.1); }
  50% { box-shadow: 0 0 40px rgba(0,212,255,0.6), 0 0 100px rgba(0,212,255,0.2); }
}

.avatar-inner {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  background: linear-gradient(135deg, #1e3a5f, #0f2744);
  border: 3px solid var(--accent);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Unbounded', sans-serif;
  font-size: 2.4rem;
  font-weight: 900;
  color: var(--accent);
  letter-spacing: -2px;
  position: relative;
  overflow: hidden;
}

.avatar-inner::after {
  content: '';
  position: absolute;
  top: -50%; left: -50%;
  width: 200%; height: 200%;
  background: conic-gradient(transparent, rgba(0,212,255,0.08), transparent 60%);
  animation: avatar-spin 4s linear infinite;
}

@keyframes avatar-spin { to { transform: rotate(360deg); } }

.orbit-dot {
  position: absolute;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  top: 50%;
  left: 50%;
  transform-origin: 0 0;
}

.orbit-dot.d1 {
  background: var(--accent);
  animation: orbit1 4s linear infinite;
  margin: -5px 0 0 -5px;
  box-shadow: 0 0 10px var(--accent);
}

.orbit-dot.d2 {
  background: var(--accent2);
  animation: orbit1 6s linear infinite reverse;
  margin: -5px 0 0 -5px;
  box-shadow: 0 0 10px var(--accent2);
}

@keyframes orbit1 {
  0% { transform: rotate(0deg) translateX(95px) rotate(0deg); }
  100% { transform: rotate(360deg) translateX(95px) rotate(-360deg); }
}

.hero-name {
  font-family: 'Unbounded', sans-serif;
  font-size: clamp(2rem, 5vw, 3.2rem);
  font-weight: 900;
  line-height: 1.1;
  letter-spacing: -2px;
  margin-bottom: 8px;
  background: linear-gradient(90deg, #fff 0%, var(--accent) 50%, #fff 100%);
  background-size: 200% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: shimmer 4s linear infinite;
}

@keyframes shimmer {
  0% { background-position: 0% center; }
  100% { background-position: 200% center; }
}

.hero-role {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.9rem;
  color: var(--accent);
  letter-spacing: 0.1em;
  margin-bottom: 20px;
}

.hero-role span { color: var(--muted); }

.hero-bio {
  font-size: 1rem;
  color: var(--muted);
  max-width: 520px;
  margin: 0 auto 28px;
  line-height: 1.7;
}

.connect-row {
  display: flex;
  justify-content: center;
  gap: 12px;
  flex-wrap: wrap;
}

.connect-btn {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 10px 20px;
  border: 1px solid var(--border);
  border-radius: 8px;
  background: var(--card);
  color: var(--text);
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.8rem;
  text-decoration: none;
  transition: all 0.3s;
  backdrop-filter: blur(8px);
}

.connect-btn:hover {
  border-color: var(--accent);
  color: var(--accent);
  transform: translateY(-2px);
  box-shadow: var(--glow);
}

.connect-btn svg { width: 16px; height: 16px; flex-shrink: 0; }

/* ── SECTION LABEL ── */
.section-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.7rem;
  color: var(--accent);
  letter-spacing: 0.2em;
  text-transform: uppercase;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 12px;
}
.section-label::before { content: '//'; color: var(--muted); }
.section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

/* ── SECTION ── */
.section { margin-bottom: 48px; }

/* ── ABOUT GRID ── */
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

.about-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 16px 18px;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}

.about-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(0,212,255,0.04), transparent);
  opacity: 0;
  transition: opacity 0.3s;
}

.about-card:hover { border-color: rgba(0,212,255,0.4); transform: translateY(-2px); }
.about-card:hover::before { opacity: 1; }

.about-card-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.65rem;
  color: var(--accent);
  letter-spacing: 0.15em;
  text-transform: uppercase;
  margin-bottom: 6px;
}

.about-card-val {
  font-size: 0.9rem;
  color: var(--text);
  line-height: 1.4;
}

/* ── TECH STACK ── */
.tech-groups {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
}

.tech-group {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 16px;
  transition: border-color 0.3s;
}

.tech-group:hover { border-color: rgba(0,212,255,0.4); }

.tech-group-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.65rem;
  color: var(--muted);
  letter-spacing: 0.15em;
  text-transform: uppercase;
  margin-bottom: 10px;
}

.tech-pills {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.pill {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem;
  padding: 4px 10px;
  border-radius: 4px;
  background: rgba(0,212,255,0.08);
  border: 1px solid rgba(0,212,255,0.2);
  color: var(--accent);
  transition: all 0.2s;
  cursor: default;
}

.pill:hover {
  background: rgba(0,212,255,0.18);
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(0,212,255,0.2);
}

/* ── STATS ── */
.stats-hero {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
  margin-bottom: 16px;
}

.stat-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 20px 16px;
  text-align: center;
  position: relative;
  overflow: hidden;
  transition: all 0.3s;
}

.stat-card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  opacity: 0;
  transition: opacity 0.3s;
}

.stat-card.blue::after { background: var(--accent); }
.stat-card.green::after { background: var(--green); }
.stat-card.amber::after { background: var(--accent3); }
.stat-card.purple::after { background: var(--accent2); }

.stat-card:hover { transform: translateY(-3px); }
.stat-card:hover::after { opacity: 1; }

.stat-num {
  font-family: 'Unbounded', sans-serif;
  font-size: 1.6rem;
  font-weight: 700;
  display: block;
  line-height: 1;
  margin-bottom: 6px;
}

.stat-card.blue .stat-num { color: var(--accent); }
.stat-card.green .stat-num { color: var(--green); }
.stat-card.amber .stat-num { color: var(--accent3); }
.stat-card.purple .stat-num { color: var(--accent2); }

.stat-lbl {
  font-size: 0.72rem;
  color: var(--muted);
  font-family: 'JetBrains Mono', monospace;
  letter-spacing: 0.05em;
}

/* ── LANG BARS ── */
.lang-rows { display: flex; flex-direction: column; gap: 10px; }

.lang-row {
  display: grid;
  grid-template-columns: 110px 1fr 44px;
  align-items: center;
  gap: 12px;
}

.lang-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem;
  color: var(--text);
  text-align: right;
}

.lang-track {
  height: 5px;
  background: rgba(255,255,255,0.06);
  border-radius: 3px;
  overflow: hidden;
}

.lang-fill {
  height: 100%;
  border-radius: 3px;
  transform: scaleX(0);
  transform-origin: left;
  animation: bar-grow 1.2s cubic-bezier(0.16,1,0.3,1) forwards;
}

@keyframes bar-grow { to { transform: scaleX(1); } }

.lang-fill.js { background: var(--accent3); animation-delay: 0.1s; }
.lang-fill.html { background: #e34c26; animation-delay: 0.2s; }
.lang-fill.py { background: #3572A5; animation-delay: 0.3s; }
.lang-fill.css { background: #563d7c; animation-delay: 0.4s; }
.lang-fill.other { background: var(--muted); animation-delay: 0.5s; }

.lang-pct {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.7rem;
  color: var(--muted);
}

/* ── FOCUS LIST ── */
.focus-list { display: flex; flex-direction: column; gap: 8px; }

.focus-item {
  display: flex;
  align-items: center;
  gap: 14px;
  background: var(--card);
  border: 1px solid var(--border);
  border-left: 3px solid var(--accent);
  border-radius: 0 10px 10px 0;
  padding: 12px 16px;
  transition: all 0.3s;
}

.focus-item:hover {
  border-left-color: var(--accent);
  background: rgba(0,212,255,0.05);
  transform: translateX(4px);
}

.focus-icon {
  width: 28px; height: 28px;
  border-radius: 6px;
  background: rgba(0,212,255,0.1);
  border: 1px solid rgba(0,212,255,0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  font-size: 13px;
}

.focus-text { font-size: 0.88rem; line-height: 1.4; }
.focus-text strong { color: var(--accent); font-weight: 500; }

/* ── GSSOC BADGES ── */
.badge-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

.badge-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 20px 12px 16px;
  text-align: center;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}

.badge-card:hover {
  border-color: var(--accent);
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(0,212,255,0.15);
}

.badge-icon-wrap {
  width: 52px; height: 52px;
  border-radius: 50%;
  margin: 0 auto 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.badge-icon-wrap svg { width: 26px; height: 26px; }

.badge-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.7rem;
  color: var(--muted);
  line-height: 1.4;
}

/* ── ACTIVITY STREAK ── */
.streak-strip {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 20px 24px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  flex-wrap: wrap;
  gap: 16px;
}

.streak-item { text-align: center; }

.streak-val {
  font-family: 'Unbounded', sans-serif;
  font-size: 1.8rem;
  font-weight: 700;
  display: block;
  line-height: 1;
  margin-bottom: 4px;
}

.streak-sub {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.65rem;
  color: var(--muted);
  letter-spacing: 0.1em;
  text-transform: uppercase;
}

.streak-sep {
  width: 1px;
  height: 44px;
  background: var(--border);
}

/* ── TERMINAL FOOTER ── */
.terminal {
  background: #080f1a;
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
  margin-top: 48px;
}

.terminal-bar {
  background: #0d1929;
  padding: 10px 16px;
  display: flex;
  align-items: center;
  gap: 6px;
  border-bottom: 1px solid var(--border);
}

.term-dot { width: 10px; height: 10px; border-radius: 50%; }
.term-dot.r { background: #ff5f57; }
.term-dot.y { background: #febc2e; }
.term-dot.g { background: #28c840; }

.term-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.7rem;
  color: var(--muted);
  margin-left: 8px;
}

.terminal-body {
  padding: 20px 24px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.82rem;
  line-height: 2;
}

.t-line { display: flex; align-items: center; gap: 10px; }
.t-prompt { color: var(--green); }
.t-cmd { color: var(--text); }
.t-out { color: var(--muted); padding-left: 24px; }
.t-acc { color: var(--accent); }
.t-amber { color: var(--accent3); }

.cursor {
  display: inline-block;
  width: 8px;
  height: 14px;
  background: var(--accent);
  animation: blink 1s step-end infinite;
  vertical-align: middle;
}

@keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: 0; } }

/* ── SCROLL REVEAL ── */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}
.reveal.visible { opacity: 1; transform: translateY(0); }

/* ── GRID STATS IMG ── */
.stats-imgs {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 12px;
}

.stats-imgs img {
  width: 100%;
  border-radius: 10px;
  border: 1px solid var(--border);
}

.stats-imgs-full img {
  width: 100%;
  border-radius: 10px;
  border: 1px solid var(--border);
}
</style>
</head>
<body>

<canvas id="stars-canvas"></canvas>

<div class="content">

  <!-- HERO -->
  <section class="hero reveal">
    <div class="hero-orbit">
      <div class="avatar-ring">
        <div class="avatar-inner">KG</div>
      </div>
      <div class="orbit-dot d1"></div>
      <div class="orbit-dot d2"></div>
    </div>

    <h1 class="hero-name">Karthik Gouda</h1>
    <div class="hero-role"><span>const</span> role = <span>"</span>Full-Stack Developer<span>"</span></div>
    <p class="hero-bio">Building scalable MERN applications. Exploring cloud infrastructure, CI/CD pipelines, and microservices. Computer Science @ DR SMCE.</p>

    <div class="connect-row">
      <a class="connect-btn" href="https://linkedin.com/in/kartikagouda15" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        linkedin
      </a>
      <a class="connect-btn" href="https://instagram.com/karthik_gouda01" target="_blank">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><rect x="2" y="2" width="20" height="20" rx="5"/><path d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
        instagram
      </a>
      <a class="connect-btn" href="https://github.com/karthikgouda15" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>
        github
      </a>
    </div>
  </section>

  <!-- ABOUT -->
  <section class="section reveal">
    <div class="section-label">about</div>
    <div class="about-grid">
      <div class="about-card">
        <div class="about-card-label">currently building</div>
        <div class="about-card-val">Full-stack MERN apps with cloud deployments and REST APIs</div>
      </div>
      <div class="about-card">
        <div class="about-card-label">education</div>
        <div class="about-card-val">Computer Science — DR SMCE</div>
      </div>
      <div class="about-card">
        <div class="about-card-label">exploring</div>
        <div class="about-card-val">Microsoft Azure · CI/CD · Docker · Microservices</div>
      </div>
      <div class="about-card">
        <div class="about-card-label">focus area</div>
        <div class="about-card-val">Scalable architecture & real-world problem solving</div>
      </div>
    </div>
  </section>

  <!-- FOCUS -->
  <section class="section reveal">
    <div class="section-label">current focus</div>
    <div class="focus-list">
      <div class="focus-item">
        <div class="focus-icon">↗</div>
        <div class="focus-text"><strong>MERN stack</strong> — REST APIs, JWT auth, cloud-deployed applications</div>
      </div>
      <div class="focus-item">
        <div class="focus-icon">☁</div>
        <div class="focus-text"><strong>Microsoft Azure</strong> — App Service, storage, networking fundamentals</div>
      </div>
      <div class="focus-item">
        <div class="focus-icon">⚙</div>
        <div class="focus-text"><strong>DevOps</strong> — GitHub Actions CI/CD, Docker containerisation</div>
      </div>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="section reveal">
    <div class="section-label">tech stack</div>
    <div class="tech-groups">
      <div class="tech-group">
        <div class="tech-group-name">frontend</div>
        <div class="tech-pills">
          <span class="pill">React</span>
          <span class="pill">JavaScript</span>
          <span class="pill">HTML5</span>
          <span class="pill">CSS3</span>
          <span class="pill">Bootstrap</span>
          <span class="pill">jQuery</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-group-name">backend</div>
        <div class="tech-pills">
          <span class="pill">Node.js</span>
          <span class="pill">Express.js</span>
          <span class="pill">Python</span>
          <span class="pill">REST APIs</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-group-name">databases</div>
        <div class="tech-pills">
          <span class="pill">MongoDB</span>
          <span class="pill">PostgreSQL</span>
          <span class="pill">MySQL</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-group-name">cloud & tools</div>
        <div class="tech-pills">
          <span class="pill">AWS</span>
          <span class="pill">Azure</span>
          <span class="pill">Git</span>
          <span class="pill">Docker</span>
          <span class="pill">Postman</span>
          <span class="pill">Figma</span>
        </div>
      </div>
    </div>
  </section>

  <!-- STATS NUMBERS -->
  <section class="section reveal">
    <div class="section-label">github activity</div>
    <div class="stats-hero">
      <div class="stat-card blue">
        <span class="stat-num">200+</span>
        <span class="stat-lbl">commits</span>
      </div>
      <div class="stat-card green">
        <span class="stat-num">50+</span>
        <span class="stat-lbl">pull requests</span>
      </div>
      <div class="stat-card amber">
        <span class="stat-num">15+</span>
        <span class="stat-lbl">stars earned</span>
      </div>
      <div class="stat-card purple">
        <span class="stat-num">20+</span>
        <span class="stat-lbl">repositories</span>
      </div>
    </div>

    <div class="stats-imgs">
      <img src="https://github-readme-stats.vercel.app/api?username=karthikgouda15&theme=tokyonight&hide_border=true&show_icons=true&bg_color=060d18&title_color=00d4ff&icon_color=00d4ff&text_color=94a3b8&border_radius=8" alt="GitHub Stats"/>
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=karthikgouda15&theme=tokyonight&hide_border=true&background=060d18&ring=00d4ff&fire=f59e0b&currStreakLabel=00d4ff&border_radius=8" alt="GitHub Streak"/>
    </div>
    <div class="stats-imgs-full">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=karthikgouda15&theme=tokyonight&hide_border=true&layout=compact&bg_color=060d18&title_color=00d4ff&text_color=94a3b8&border_radius=8" alt="Top Languages"/>
    </div>
  </section>

  <!-- LANGUAGE BARS -->
  <section class="section reveal">
    <div class="section-label">language breakdown</div>
    <div class="lang-rows">
      <div class="lang-row"><div class="lang-name">JavaScript</div><div class="lang-track"><div class="lang-fill js" style="width:62%"></div></div><div class="lang-pct">62%</div></div>
      <div class="lang-row"><div class="lang-name">HTML/CSS</div><div class="lang-track"><div class="lang-fill html" style="width:18%"></div></div><div class="lang-pct">18%</div></div>
      <div class="lang-row"><div class="lang-name">Python</div><div class="lang-track"><div class="lang-fill py" style="width:12%"></div></div><div class="lang-pct">12%</div></div>
      <div class="lang-row"><div class="lang-name">Other</div><div class="lang-track"><div class="lang-fill other" style="width:8%"></div></div><div class="lang-pct">8%</div></div>
    </div>
  </section>

  <!-- GSSOC -->
  <section class="section reveal">
    <div class="section-label">gssoc '24 badges</div>
    <div class="badge-grid">
      <div class="badge-card">
        <div class="badge-icon-wrap" style="background:rgba(0,212,255,0.1);border:1px solid rgba(0,212,255,0.3)">
          <svg viewBox="0 0 24 24" fill="none" stroke="#00d4ff" stroke-width="1.8" stroke-linecap="round"><path d="M21 16V8a2 2 0 00-1-1.73l-7-4a2 2 0 00-2 0l-7 4A2 2 0 003 8v8a2 2 0 001 1.73l7 4a2 2 0 002 0l7-4A2 2 0 0021 16z"/></svg>
        </div>
        <div class="badge-name">Postman challenge</div>
      </div>
      <div class="badge-card">
        <div class="badge-icon-wrap" style="background:rgba(245,158,11,0.1);border:1px solid rgba(245,158,11,0.3)">
          <svg viewBox="0 0 24 24" fill="none" stroke="#f59e0b" stroke-width="1.8" stroke-linecap="round"><circle cx="12" cy="8" r="6"/><path d="M15.477 12.89L17 22l-5-3-5 3 1.523-9.11"/></svg>
        </div>
        <div class="badge-name">Code luminary</div>
      </div>
      <div class="badge-card">
        <div class="badge-icon-wrap" style="background:rgba(16,185,129,0.1);border:1px solid rgba(16,185,129,0.3)">
          <svg viewBox="0 0 24 24" fill="none" stroke="#10b981" stroke-width="1.8" stroke-linecap="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>
        </div>
        <div class="badge-name">Pull expert</div>
      </div>
      <div class="badge-card">
        <div class="badge-icon-wrap" style="background:rgba(124,58,237,0.1);border:1px solid rgba(124,58,237,0.3)">
          <svg viewBox="0 0 24 24" fill="none" stroke="#7c3aed" stroke-width="1.8" stroke-linecap="round"><circle cx="18" cy="18" r="3"/><circle cx="6" cy="6" r="3"/><path d="M13 6h3a2 2 0 012 2v7"/><line x1="6" y1="9" x2="6" y2="21"/></svg>
        </div>
        <div class="badge-name">Git explorer</div>
      </div>
    </div>
  </section>

  <!-- TERMINAL FOOTER -->
  <div class="terminal reveal">
    <div class="terminal-bar">
      <div class="term-dot r"></div>
      <div class="term-dot y"></div>
      <div class="term-dot g"></div>
      <span class="term-title">karthik@dev ~ bash</span>
    </div>
    <div class="terminal-body">
      <div class="t-line"><span class="t-prompt">karthik@dev</span><span class="t-cmd"> $ whoami</span></div>
      <div class="t-out t-acc">// Full-Stack Developer · MERN · Cloud · Open Source</div>
      <div class="t-line"><span class="t-prompt">karthik@dev</span><span class="t-cmd"> $ cat philosophy.txt</span></div>
      <div class="t-out t-amber">code → learn → build → repeat</div>
      <div class="t-line"><span class="t-prompt">karthik@dev</span><span class="t-cmd"> $ git log --oneline | head -1</span></div>
      <div class="t-out">200+ commits across 20+ repos</div>
      <div class="t-line"><span class="t-prompt">karthik@dev</span><span class="t-cmd"> $ <span class="cursor"></span></span></div>
    </div>
  </div>

</div>

<script>
// STARS
const canvas = document.getElementById('stars-canvas');
const ctx = canvas.getContext('2d');
let stars = [];

function resize() {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
}

function initStars() {
  stars = [];
  for (let i = 0; i < 120; i++) {
    stars.push({
      x: Math.random() * canvas.width,
      y: Math.random() * canvas.height,
      r: Math.random() * 1.2 + 0.2,
      a: Math.random(),
      speed: Math.random() * 0.3 + 0.05
    });
  }
}

function drawStars() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  const t = Date.now() / 1000;
  stars.forEach(s => {
    const pulse = 0.3 + 0.7 * Math.abs(Math.sin(t * s.speed + s.a * 10));
    ctx.beginPath();
    ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(148,163,184,${pulse * 0.6})`;
    ctx.fill();
  });
  requestAnimationFrame(drawStars);
}

resize();
initStars();
drawStars();
window.addEventListener('resize', () => { resize(); initStars(); });

// SCROLL REVEAL
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.1 });

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>. remove the commands to work properly
