<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jones Studio — Strategic Brand Design</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --purple: #7c5cfc;
    --purple-dim: rgba(124,92,252,0.15);
    --white: #ffffff;
    --off-white: #e8e8e8;
    --muted: rgba(255,255,255,0.45);
    --faint: rgba(255,255,255,0.08);
    --border: rgba(255,255,255,0.07);
    --bg: #080808;
    --bg2: #0f0f0f;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--bg);
    color: var(--off-white);
    line-height: 1.6;
    overflow-x: hidden;
  }

  a { text-decoration: none; color: inherit; }

  /* ── NAV ── */
  nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.2rem 3rem;
    border-bottom: 1px solid var(--border);
    position: sticky;
    top: 0;
    background: rgba(8,8,8,0.92);
    backdrop-filter: blur(14px);
    -webkit-backdrop-filter: blur(14px);
    z-index: 100;
  }

  .logo {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--white);
  }

  .logo svg { flex-shrink: 0; }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    font-size: 12px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.4);
    list-style: none;
  }

  .nav-links a { transition: color 0.2s; }
  .nav-links a:hover { color: var(--white); }

  .btn-nav {
    font-size: 12px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 0.6rem 1.4rem;
    border: 1px solid rgba(255,255,255,0.2);
    color: var(--white);
    background: transparent;
    cursor: pointer;
    font-family: 'Inter', sans-serif;
    transition: all 0.2s;
  }
  .btn-nav:hover { background: rgba(255,255,255,0.05); }

  /* ── HERO ── */
  .hero {
    min-height: 90vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 4rem 3rem;
    position: relative;
    overflow: hidden;
  }

  .hero-bg-glow {
    position: absolute;
    right: 0;
    top: 0;
    width: 55%;
    height: 100%;
    background: radial-gradient(ellipse at 70% 40%, rgba(98,54,255,0.18) 0%, transparent 65%);
    pointer-events: none;
  }

  .hero-eyebrow {
    font-size: 11px;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--purple);
    margin-bottom: 1.5rem;
  }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.8rem, 5vw, 4.4rem);
    font-weight: 800;
    line-height: 1.08;
    color: var(--white);
    margin-bottom: 1.8rem;
  }

  .hero h1 em {
    color: var(--purple);
    font-style: normal;
  }

  .hero-body {
    font-size: 15px;
    color: var(--muted);
    max-width: 380px;
    line-height: 1.8;
    margin-bottom: 2.5rem;
  }

  .hero-btns {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .btn-primary {
    background: var(--purple);
    color: var(--white);
    padding: 0.85rem 1.8rem;
    font-size: 13px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'Inter', sans-serif;
    border: none;
    transition: background 0.2s, transform 0.15s;
  }
  .btn-primary:hover { background: #6b4de6; transform: translateY(-1px); }

  .btn-ghost {
    background: transparent;
    color: var(--white);
    padding: 0.85rem 1.8rem;
    font-size: 13px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    gap: 8px;
    border: 1px solid rgba(255,255,255,0.2);
    font-family: 'Inter', sans-serif;
    transition: all 0.2s;
  }
  .btn-ghost:hover { border-color: rgba(255,255,255,0.5); background: rgba(255,255,255,0.04); }

  .hero-right {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  .hero-visual {
    width: 460px;
    height: 540px;
    position: relative;
    background: linear-gradient(145deg, #1a0f3a 0%, #0d0621 100%);
    overflow: hidden;
  }

  .hero-visual-glow {
    position: absolute;
    top: 15%;
    left: 15%;
    width: 70%;
    height: 55%;
    background: radial-gradient(ellipse, rgba(124,92,252,0.5) 0%, transparent 70%);
    filter: blur(35px);
  }

  .hero-monogram {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;
  }

  .hero-monogram-letters {
    font-family: 'Syne', sans-serif;
    font-size: 6rem;
    font-weight: 800;
    color: rgba(124,92,252,0.12);
    line-height: 1;
    letter-spacing: -0.02em;
  }

  .hero-monogram-label {
    font-size: 10px;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.18);
    margin-top: 0.5rem;
  }

  .hero-avail {
    position: absolute;
    bottom: 3rem;
    right: 3rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .avail-dot {
    width: 7px;
    height: 7px;
    background: #22c55e;
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  .avail-text {
    font-size: 11px;
    letter-spacing: 0.1em;
    color: rgba(255,255,255,0.35);
    text-transform: uppercase;
  }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: var(--border);
    margin: 0 3rem;
  }

  /* ── WORK SECTION ── */
  .section { padding: 5rem 3rem; }

  .sec-eyebrow {
    font-size: 11px;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--purple);
    margin-bottom: 0.8rem;
  }

  .sec-h2 {
    font-family: 'Syne', sans-serif;
    font-size: 2.4rem;
    font-weight: 700;
    color: var(--white);
  }

  .sec-row {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 2.5rem;
  }

  .view-all {
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.35);
    display: flex;
    align-items: center;
    gap: 6px;
    cursor: pointer;
    transition: color 0.2s;
  }
  .view-all:hover { color: var(--white); }

  .work-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: rgba(255,255,255,0.05);
  }

  .work-card {
    background: var(--bg);
    overflow: hidden;
    cursor: pointer;
  }

  .work-thumb {
    height: 230px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
    transition: transform 0.4s ease;
  }

  .work-card:hover .work-thumb { transform: scale(1.03); }

  .work-thumb-marino { background: linear-gradient(145deg, #111 0%, #1c1c1c 100%); }
  .work-thumb-vault  { background: linear-gradient(145deg, #0e0e12 0%, #18141f 100%); }
  .work-thumb-more   { background: linear-gradient(145deg, #101010 0%, #161616 100%); }
  .work-thumb-primo  { background: linear-gradient(145deg, #0a0a1a 0%, #1a0f35 100%); }

  .work-thumb-label {
    font-family: 'Syne', sans-serif;
    font-size: 1.1rem;
    font-weight: 700;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.65);
  }

  .work-thumb-accent {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, var(--purple), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .work-card:hover .work-thumb-accent { opacity: 1; }

  .work-meta {
    padding: 1.2rem 1.4rem;
    border-top: 1px solid var(--border);
  }

  .work-num {
    font-size: 10px;
    color: var(--purple);
    letter-spacing: 0.15em;
    margin-bottom: 0.35rem;
  }

  .work-title {
    font-family: 'Syne', sans-serif;
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--white);
    margin-bottom: 0.2rem;
  }

  .work-sub {
    font-size: 11px;
    color: rgba(255,255,255,0.3);
    letter-spacing: 0.04em;
  }

  /* ── SERVICES ── */
  .services-wrap {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
    align-items: start;
    padding: 5rem 3rem;
  }

  .serv-left { padding-right: 4rem; }

  .serv-left .sec-h2 { margin-bottom: 1.2rem; }

  .serv-desc {
    font-size: 14px;
    color: rgba(255,255,255,0.38);
    line-height: 1.8;
    max-width: 300px;
  }

  .serv-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }

  .serv-card {
    padding: 1.6rem;
    border: 1px solid var(--border);
    transition: border-color 0.25s;
  }
  .serv-card:hover { border-color: rgba(124,92,252,0.4); }

  .serv-icon {
    width: 36px;
    height: 36px;
    border: 1px solid rgba(124,92,252,0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1.2rem;
  }

  .serv-title {
    font-family: 'Syne', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--white);
    margin-bottom: 0.6rem;
  }

  .serv-body {
    font-size: 12px;
    color: rgba(255,255,255,0.38);
    line-height: 1.7;
  }

  /* ── ABOUT ── */
  .about-wrap {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    padding: 5rem 3rem;
    align-items: center;
  }

  .about-img-box {
    position: relative;
    height: 500px;
    background: #0f0f0f;
    border: 1px solid var(--border);
    display: flex;
    align-items: flex-end;
    justify-content: center;
    overflow: hidden;
  }

  .about-img-label {
    position: absolute;
    top: 1.5rem;
    left: 1.5rem;
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.18);
  }

  .about-portrait-placeholder {
    width: 280px;
    height: 380px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 4rem;
    font-weight: 800;
    color: rgba(124,92,252,0.1);
    background: linear-gradient(to top, rgba(124,92,252,0.06) 0%, transparent 100%);
    margin-bottom: 0;
  }

  .about-img-line {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--purple), transparent);
  }

  .about-eyebrow { margin-bottom: 0.8rem; }

  .about-h2 {
    font-family: 'Syne', sans-serif;
    font-size: 2.8rem;
    font-weight: 800;
    color: var(--white);
    line-height: 1.1;
    margin-bottom: 0.8rem;
  }

  .about-role {
    font-size: 12px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--purple);
    margin-bottom: 1.5rem;
  }

  .about-body {
    font-size: 14px;
    color: rgba(255,255,255,0.42);
    line-height: 1.85;
    margin-bottom: 1rem;
  }

  .about-stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    border: 1px solid var(--border);
    margin-top: 2.5rem;
  }

  .stat-box {
    padding: 1.4rem;
    text-align: center;
    border-right: 1px solid var(--border);
  }
  .stat-box:last-child { border-right: none; }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    color: var(--purple);
    margin-bottom: 0.3rem;
  }

  .stat-lbl {
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.28);
  }

  /* ── CTA STRIP ── */
  .cta-strip {
    padding: 5rem 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-top: 1px solid var(--border);
    gap: 2rem;
  }

  .cta-h2 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2rem, 4vw, 2.8rem);
    font-weight: 800;
    color: var(--white);
    line-height: 1.15;
  }

  .cta-h2 em {
    color: var(--purple);
    font-style: normal;
  }

  .cta-right {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 1.5rem;
    flex-shrink: 0;
  }

  .cta-body {
    font-size: 14px;
    color: rgba(255,255,255,0.4);
    max-width: 260px;
    text-align: right;
    line-height: 1.75;
  }

  /* ── FOOTER ── */
  footer {
    padding: 1.6rem 3rem;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .footer-copy {
    font-size: 11px;
    color: rgba(255,255,255,0.22);
    letter-spacing: 0.05em;
  }

  .footer-links {
    display: flex;
    gap: 2rem;
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.28);
    list-style: none;
  }

  .footer-links a { transition: color 0.2s; }
  .footer-links a:hover { color: var(--white); }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; padding: 3rem 1.5rem; min-height: auto; }
    .hero-right { display: none; }
    .hero-avail { position: static; margin-top: 2rem; }
    .divider { margin: 0 1.5rem; }
    .section { padding: 3.5rem 1.5rem; }
    .work-grid { grid-template-columns: 1fr 1fr; }
    .services-wrap { grid-template-columns: 1fr; padding: 3.5rem 1.5rem; }
    .serv-left { padding-right: 0; margin-bottom: 2.5rem; }
    .about-wrap { grid-template-columns: 1fr; padding: 3.5rem 1.5rem; }
    .about-img-box { height: 300px; }
    .cta-strip { flex-direction: column; align-items: flex-start; padding: 3.5rem 1.5rem; }
    .cta-right { align-items: flex-start; }
    .cta-body { text-align: left; }
    footer { padding: 1.5rem; flex-direction: column; gap: 1rem; text-align: center; }
  }

  @media (max-width: 560px) {
    .work-grid { grid-template-columns: 1fr; }
    .serv-grid { grid-template-columns: 1fr; }
    .about-stats { grid-template-columns: 1fr; }
    .stat-box { border-right: none; border-bottom: 1px solid var(--border); }
    .stat-box:last-child { border-bottom: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">
    <svg width="28" height="28" viewBox="0 0 30 30" fill="none" aria-hidden="true">
      <path d="M4 26L15 4L26 26" stroke="#7c5cfc" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M8 19H22" stroke="#7c5cfc" stroke-width="2.5" stroke-linecap="round"/>
      <circle cx="15" cy="4" r="2" fill="#7c5cfc"/>
    </svg>
    Jones Studio
  </div>
  <ul class="nav-links">
    <li><a href="#work">Work</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About Me</a></li>
    <li><a href="#">Process</a></li>
    <li><a href="#">Clients</a></li>
  </ul>
  <button class="btn-nav">Work With Me</button>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg-glow"></div>
  <div>
    <p class="hero-eyebrow">Strategic Brand Design</p>
    <h1>Designing Brands<br>With <em>Purpose<br>&amp; Precision.</em></h1>
    <p class="hero-body">I help businesses build stronger brand identities, visual systems, and marketing assets that create credibility, consistency, and long-term recognition.</p>
    <div class="hero-btns">
      <a href="#work" class="btn-primary">View Projects →</a>
      <a href="#contact" class="btn-ghost">Start a Project ↗</a>
    </div>
    <div class="hero-avail">
      <div class="avail-dot"></div>
      <span class="avail-text">Available for projects</span>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-visual">
      <div class="hero-visual-glow"></div>
      <div class="hero-monogram">
        <div class="hero-monogram-letters">RJ</div>
        <div class="hero-monogram-label">Creative Lead</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- WORK -->
<section class="section" id="work">
  <div class="sec-row">
    <div>
      <p class="sec-eyebrow">Selected Work</p>
      <h2 class="sec-h2">Featured Projects</h2>
    </div>
    <a href="#" class="view-all">View All Work →</a>
  </div>
  <div class="work-grid">

    <div class="work-card">
      <div class="work-thumb work-thumb-marino">
        <span class="work-thumb-label" style="letter-spacing:0.35em">MARINO</span>
        <div class="work-thumb-accent"></div>
      </div>
      <div class="work-meta">
        <p class="work-num">01</p>
        <p class="work-title">Marino Clothing</p>
        <p class="work-sub">Brand Identity &amp; Art Direction</p>
      </div>
    </div>

    <div class="work-card">
      <div class="work-thumb work-thumb-vault" style="flex-direction:column;gap:0.6rem">
        <svg width="44" height="44" viewBox="0 0 48 48" fill="none" aria-hidden="true" style="opacity:.55">
          <path d="M8 40L24 8L40 40" stroke="rgba(255,255,255,0.8)" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M14 30H34" stroke="rgba(255,255,255,0.8)" stroke-width="2.5" stroke-linecap="round"/>
        </svg>
        <span style="font-size:9px;letter-spacing:0.28em;color:rgba(255,255,255,0.25);text-transform:uppercase;font-family:'Syne',sans-serif">VAULTMASTER</span>
        <div class="work-thumb-accent"></div>
      </div>
      <div class="work-meta">
        <p class="work-num">02</p>
        <p class="work-title">VaultMaster</p>
        <p class="work-sub">Luxury Product Branding</p>
      </div>
    </div>

    <div class="work-card">
      <div class="work-thumb work-thumb-more">
        <span class="work-thumb-label" style="font-size:1.3rem;letter-spacing:0.4em;color:rgba(255,255,255,0.45)">M.O.R.E</span>
        <div class="work-thumb-accent"></div>
      </div>
      <div class="work-meta">
        <p class="work-num">03</p>
        <p class="work-title">M.O.R.E</p>
        <p class="work-sub">Lifestyle Brand Identity</p>
      </div>
    </div>

    <div class="work-card">
      <div class="work-thumb work-thumb-primo" style="flex-direction:column;gap:0.3rem">
        <span style="font-family:'Syne',sans-serif;font-size:2.2rem;font-weight:800;color:#7c5cfc;letter-spacing:0.05em">PRIMO</span>
        <span style="font-family:'Syne',sans-serif;font-size:1rem;font-weight:700;color:rgba(255,255,255,0.45);letter-spacing:0.4em;text-transform:uppercase">PLAY</span>
        <div style="width:50%;height:1px;background:rgba(124,92,252,0.45);margin-top:0.6rem"></div>
        <div class="work-thumb-accent"></div>
      </div>
      <div class="work-meta">
        <p class="work-num">04</p>
        <p class="work-title">Primo Play</p>
        <p class="work-sub">Campaign &amp; Launch Design</p>
      </div>
    </div>

  </div>
</section>

<div class="divider"></div>

<!-- SERVICES -->
<div class="services-wrap" id="services">
  <div class="serv-left">
    <p class="sec-eyebrow">What I Do</p>
    <h2 class="sec-h2">Design Solutions That<br>Build Stronger Brands.</h2>
    <p class="serv-desc">Every brand problem is unique. I combine strategy, craft, and intention to create visual identities that endure.</p>
  </div>
  <div class="serv-grid">

    <div class="serv-card">
      <div class="serv-icon">
        <svg width="18" height="18" viewBox="0 0 18 18" fill="none" aria-hidden="true">
          <circle cx="9" cy="9" r="6" stroke="#7c5cfc" stroke-width="1.5"/>
          <circle cx="9" cy="9" r="2" fill="#7c5cfc"/>
        </svg>
      </div>
      <p class="serv-title">Brand Identity Design</p>
      <p class="serv-body">Creating strategic brand identities that communicate your value and set you apart.</p>
    </div>

    <div class="serv-card">
      <div class="serv-icon">
        <svg width="18" height="18" viewBox="0 0 18 18" fill="none" aria-hidden="true">
          <rect x="2" y="2" width="6" height="6" stroke="#7c5cfc" stroke-width="1.5"/>
          <rect x="10" y="2" width="6" height="6" stroke="#7c5cfc" stroke-width="1.5"/>
          <rect x="2" y="10" width="6" height="6" stroke="#7c5cfc" stroke-width="1.5"/>
          <rect x="10" y="10" width="6" height="6" stroke="#7c5cfc" stroke-width="1.5"/>
        </svg>
      </div>
      <p class="serv-title">Visual Systems</p>
      <p class="serv-body">Building scalable visual systems that ensure consistency across all touchpoints.</p>
    </div>

    <div class="serv-card">
      <div class="serv-icon">
        <svg width="18" height="18" viewBox="0 0 18 18" fill="none" aria-hidden="true">
          <rect x="2" y="4" width="14" height="10" rx="1" stroke="#7c5cfc" stroke-width="1.5"/>
          <path d="M5 8h8M5 11h5" stroke="#7c5cfc" stroke-width="1.5" stroke-linecap="round"/>
        </svg>
      </div>
      <p class="serv-title">Marketing Design</p>
      <p class="serv-body">Designing marketing assets that capture attention and drive measurable results.</p>
    </div>

    <div class="serv-card">
      <div class="serv-icon">
        <svg width="18" height="18" viewBox="0 0 18 18" fill="none" aria-hidden="true">
          <path d="M4 14l4-4 3 3 5-7" stroke="#7c5cfc" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>
      <p class="serv-title">Creative Direction</p>
      <p class="serv-body">Providing strategic visual leadership for campaigns, products, and brand growth.</p>
    </div>

  </div>
</div>

<div class="divider"></div>

<!-- ABOUT -->
<div class="about-wrap" id="about">
  <div class="about-img-box">
    <span class="about-img-label">About Me</span>
    <div class="about-portrait-placeholder">RJ</div>
    <div class="about-img-line"></div>
  </div>
  <div>
    <p class="sec-eyebrow about-eyebrow">About Me</p>
    <h2 class="about-h2">Hi, I'm<br>Rique Jones.</h2>
    <p class="about-role">Creative Lead &amp; Strategic Brand Designer</p>
    <p class="about-body">With over 9 years of experience, I help startups, businesses, and growing brands turn ideas into meaningful visual identities. My approach combines strategy, creativity, and purpose to deliver designs that look good and work even better.</p>
    <p class="about-body">I believe great design isn't decoration. It's communication with intention.</p>
    <a href="#" class="btn-ghost" style="display:inline-flex;margin-top:0.5rem">More About Me →</a>
    <div class="about-stats">
      <div class="stat-box">
        <div class="stat-num">9+</div>
        <div class="stat-lbl">Years Experience</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">100+</div>
        <div class="stat-lbl">Projects Delivered</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">20+</div>
        <div class="stat-lbl">Brands Developed</div>
      </div>
    </div>
  </div>
</div>

<!-- CTA STRIP -->
<div class="cta-strip" id="contact">
  <h2 class="cta-h2">Ready To Build<br>Something <em>Meaningful?</em></h2>
  <div class="cta-right">
    <p class="cta-body">Let's create a brand that not only looks great but also drives growth and leaves a lasting impact.</p>
    <a href="mailto:hello@jonesstudio.com" class="btn-primary">Work With Me ↗</a>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="logo">
    <svg width="22" height="22" viewBox="0 0 30 30" fill="none" aria-hidden="true">
      <path d="M4 26L15 4L26 26" stroke="#7c5cfc" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M8 19H22" stroke="#7c5cfc" stroke-width="2.5" stroke-linecap="round"/>
      <circle cx="15" cy="4" r="2" fill="#7c5cfc"/>
    </svg>
    Jones Studio
  </div>
  <p class="footer-copy">© 2024 Jones Studio. All rights reserved.</p>
  <ul class="footer-links">
    <li><a href="#">Instagram</a></li>
    <li><a href="#">LinkedIn</a></li>
    <li><a href="#">Behance</a></li>
    <li><a href="#">Email</a></li>
  </ul>
</footer>

</body>
</html>
