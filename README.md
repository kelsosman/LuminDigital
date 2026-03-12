<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kelsey Osman — Product Leader for Lumin Digital</title>
  <style>
    :root {
      --bg: #0b0f14;
      --surface: #131920;
      --surface2: #1a2430;
      --accent: #00d4aa;
      --accent2: #0090ff;
      --accent3: #ff6b35;
      --text: #e8edf2;
      --muted: #8a9db5;
      --border: rgba(0, 212, 170, 0.15);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: Arial, Helvetica, sans-serif;
      font-size: 16px;
      line-height: 1.65;
      overflow-x: hidden;
    }

    /* NAV */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1rem 2.5rem;
      background: rgba(11,15,20,0.9);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }
    .nav-logo { font-weight: 700; font-size: 1.05rem; color: var(--accent); }
    .nav-links { display: flex; gap: 2rem; list-style: none; align-items: center; }
    .nav-links a {
      color: var(--muted); text-decoration: none;
      font-size: 0.78rem; font-weight: 400;
      font-family: "Arial Narrow", Arial, sans-serif;
      letter-spacing: 0.07em; text-transform: uppercase;
      transition: color 0.2s;
    }
    .hamburger { display: none; }
    .nav-links a:hover { color: var(--accent); }
    .nav-links a.active {
      color: var(--accent);
      position: relative;
    }
    .nav-links a.active::after {
      content: '';
      position: absolute;
      bottom: -6px; left: 0; right: 0;
      height: 2px;
      background: var(--accent);
      border-radius: 2px;
    }

    /* HERO */
    .hero {
      min-height: 100vh; display: flex; align-items: center;
      padding: 5.5rem 2.5rem 4rem; position: relative; overflow: hidden;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background:
        radial-gradient(ellipse 80% 60% at 70% 50%, rgba(0,212,170,0.06) 0%, transparent 60%),
        radial-gradient(ellipse 50% 40% at 20% 80%, rgba(0,144,255,0.05) 0%, transparent 50%);
    }
    .hero-grid {
      position: absolute; inset: 0;
      background-image:
        linear-gradient(rgba(0,212,170,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,212,170,0.03) 1px, transparent 1px);
      background-size: 60px 60px;
    }
    .hero-content {
      position: relative; z-index: 1;
      max-width: 1200px; margin: 0 auto; width: 100%;
      display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center;
    }
    .hero-left { display: flex; flex-direction: column; }
    .hero-eyebrow {
      display: inline-flex; align-items: center; gap: 0.5rem;
      background: rgba(0,212,170,0.08); border: 1px solid var(--border);
      border-radius: 100px; padding: 0.35rem 1rem;
      font-size: 0.72rem; font-weight: 700;
      font-family: "Arial Narrow", Arial, sans-serif;
      letter-spacing: 0.1em; text-transform: uppercase; color: var(--accent);
      margin-bottom: 1.5rem; width: fit-content;
    }
    .eyebrow-dot {
      width: 6px; height: 6px; background: var(--accent);
      border-radius: 50%; animation: pulse 2s infinite;
    }
    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.4; transform: scale(1.4); }
    }
    h1 {
      font-size: clamp(2.8rem, 5vw, 4.6rem); font-weight: 700;
      line-height: 1.0; letter-spacing: -0.02em; margin-bottom: 1.25rem;
    }
    h1 .name-line { display: block; color: var(--text); }
    h1 .title-line { display: block; color: var(--accent); }
    .hero-desc {
      font-size: 1.02rem; color: var(--muted);
      line-height: 1.8; margin-bottom: 2rem; max-width: 480px;
    }
    .hero-desc strong { color: var(--text); font-weight: 700; }

    /* Right column */
    .hero-right { display: flex; flex-direction: column; gap: 1.5rem; align-items: center; }
    .photo-area { display: flex; flex-direction: column; align-items: center; gap: 0.6rem; }
    .photo-circle {
      width: 150px; height: 150px; border-radius: 50%;
      border: 3px solid var(--accent);
      box-shadow: 0 0 30px rgba(0,212,170,0.2);
      overflow: hidden; background: var(--surface2);
      display: flex; align-items: center; justify-content: center;
    }
    .photo-circle img { width: 100%; height: 100%; object-fit: cover; }
    .photo-initials { font-size: 2.8rem; font-weight: 700; color: var(--accent); opacity: 0.45; }
    .photo-hint {
      font-size: 0.64rem; font-family: "Arial Narrow", Arial, sans-serif;
      color: var(--muted); text-align: center; opacity: 0.5; max-width: 130px;
    }
    .hero-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 0.85rem; width: 100%; }
    .stat-card {
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 12px; padding: 1.1rem 1.25rem;
      position: relative; overflow: hidden;
      transition: border-color 0.2s, transform 0.2s;
    }
    .stat-card:hover { border-color: rgba(0,212,170,0.4); transform: translateY(-3px); }
    .stat-card::before {
      content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
      background: linear-gradient(90deg, var(--accent), transparent);
    }
    .stat-card.blue::before { background: linear-gradient(90deg, var(--accent2), transparent); }
    .stat-card.orange::before { background: linear-gradient(90deg, var(--accent3), transparent); }
    .stat-card.mixed::before { background: linear-gradient(90deg, var(--accent), var(--accent2)); }
    .stat-number { font-size: 1.9rem; font-weight: 700; color: var(--accent); line-height: 1; margin-bottom: 0.3rem; }
    .stat-card.blue .stat-number { color: var(--accent2); }
    .stat-card.orange .stat-number { color: var(--accent3); }
    .stat-label { font-size: 0.78rem; color: var(--muted); line-height: 1.35; }

    .hero-cta {
      display: inline-flex; align-items: center; gap: 0.7rem;
      background: var(--accent); color: #0b0f14;
      font-weight: 700; font-size: 0.88rem;
      text-decoration: none; padding: 0.85rem 1.75rem;
      border-radius: 8px; transition: all 0.2s; width: fit-content;
    }
    .hero-cta:hover { background: #00f0c0; transform: translateY(-2px); box-shadow: 0 8px 28px rgba(0,212,170,0.3); }
    .hero-cta svg { transition: transform 0.2s; }
    .hero-cta:hover svg { transform: translateX(4px); }

    /* SECTION SHARED */
    .section-wrap { max-width: 1200px; margin: 0 auto; padding: 5rem 2.5rem 1rem; scroll-margin-top: 70px; }
    .section-label {
      display: flex; align-items: center; gap: 0.75rem;
      font-size: 0.7rem; font-weight: 700;
      font-family: "Arial Narrow", Arial, sans-serif;
      letter-spacing: 0.14em; text-transform: uppercase; color: var(--accent);
      margin-bottom: 0.85rem;
    }
    .section-label::after { content: ''; height: 1px; background: var(--border); width: 50px; }
    h2 {
      font-size: clamp(1.75rem, 3vw, 2.5rem); font-weight: 700;
      letter-spacing: -0.02em; line-height: 1.15; margin-bottom: 0.7rem;
    }
    h2 em { font-style: normal; color: var(--accent); }
    .section-intro { color: var(--muted); font-size: 0.97rem; max-width: 620px; margin-bottom: 2.25rem; line-height: 1.8; }
    .section-intro strong { color: var(--text); }

    /* CARD CONTAINER */
    .card-container {
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 20px; padding: 2.75rem; position: relative; overflow: hidden;
    }
    .card-container::before {
      content: ''; position: absolute; top: -80px; right: -80px;
      width: 320px; height: 320px;
      background: radial-gradient(circle, rgba(0,212,170,0.05), transparent 70%);
      pointer-events: none;
    }

    /* WHY LUMIN */
    .why-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.1rem; }
    .why-card {
      background: var(--surface2); border: 1px solid rgba(255,255,255,0.04);
      border-radius: 14px; padding: 1.4rem;
      transition: border-color 0.2s, transform 0.2s;
    }
    .why-card:hover { border-color: rgba(0,212,170,0.25); transform: translateY(-3px); }
    .why-icon { font-size: 1.5rem; margin-bottom: 0.65rem; display: block; }
    .why-card h3 { font-size: 0.93rem; font-weight: 700; margin-bottom: 0.45rem; color: var(--text); }
    .why-card p { font-size: 0.86rem; color: var(--muted); line-height: 1.65; }
    .why-card p strong { color: var(--accent); }
    .quote-block {
      background: var(--surface2); border-left: 3px solid var(--accent);
      border-radius: 0 10px 10px 0; padding: 1.15rem 1.4rem; margin-top: 1.75rem;
    }
    .quote-block p { font-size: 0.95rem; font-style: italic; color: var(--text); line-height: 1.65; }
    .quote-block cite {
      display: block; font-size: 0.76rem; color: var(--accent);
      font-style: normal; margin-top: 0.4rem; font-weight: 700;
      font-family: "Arial Narrow", Arial, sans-serif; letter-spacing: 0.05em;
    }

    /* TIMELINE */
    .timeline { position: relative; margin-top: 1.75rem; }
    .timeline::before {
      content: ''; position: absolute; left: 106px; top: 0; bottom: 0;
      width: 1px;
      background: linear-gradient(to bottom, var(--accent), rgba(0,212,170,0.08));
    }
    .tl-item {
      display: grid; grid-template-columns: 106px 1fr;
      gap: 1.75rem; margin-bottom: 1.75rem; position: relative;
    }
    .tl-year {
      font-family: "Arial Narrow", Arial, sans-serif;
      font-size: 0.76rem; font-weight: 700; color: var(--muted);
      text-align: right; padding-top: 0.3rem; padding-right: 1.4rem;
      letter-spacing: 0.03em; line-height: 1.4;
    }
    .tl-dot {
      position: absolute; left: 99px; top: 0.45rem;
      width: 14px; height: 14px; background: var(--accent); border-radius: 50%;
      border: 3px solid var(--bg); box-shadow: 0 0 10px rgba(0,212,170,0.5);
    }
    .tl-content {
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 12px; padding: 1.3rem;
    }
    .tl-content h3 { font-size: 0.95rem; font-weight: 700; margin-bottom: 0.15rem; color: var(--text); }
    .tl-company {
      font-size: 0.78rem; color: var(--accent); font-weight: 700;
      font-family: "Arial Narrow", Arial, sans-serif;
      letter-spacing: 0.04em; margin-bottom: 0.6rem;
    }
    .tl-content p { font-size: 0.87rem; color: var(--muted); line-height: 1.68; }
    .tl-tags { display: flex; flex-wrap: wrap; gap: 0.32rem; margin-top: 0.65rem; }
    .tl-tag {
      background: rgba(0,212,170,0.07); border: 1px solid rgba(0,212,170,0.15);
      color: var(--accent); font-size: 0.69rem; font-weight: 700;
      font-family: "Arial Narrow", Arial, sans-serif; letter-spacing: 0.04em;
      padding: 0.16rem 0.52rem; border-radius: 100px;
    }
    .tl-tag.blue { background: rgba(0,144,255,0.07); border-color: rgba(0,144,255,0.2); color: var(--accent2); }
    .tl-tag.orange { background: rgba(255,107,53,0.07); border-color: rgba(255,107,53,0.2); color: var(--accent3); }
    .tl-tag.grey { background: rgba(138,157,181,0.07); border-color: rgba(138,157,181,0.2); color: var(--muted); }

    /* SKILLS */
    .skills-grid { display: grid; grid-template-columns: repeat(2,1fr); gap: 1.1rem; margin-top: 1.75rem; }
    .skill-group {
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 14px; padding: 1.4rem;
    }
    .skill-group-title {
      font-family: "Arial Narrow", Arial, sans-serif;
      font-size: 0.7rem; font-weight: 700; letter-spacing: 0.1em;
      text-transform: uppercase; color: var(--muted); margin-bottom: 0.85rem;
    }
    .skill-pills { display: flex; flex-wrap: wrap; gap: 0.42rem; }
    .pill {
      background: var(--surface2); border: 1px solid rgba(255,255,255,0.06);
      color: var(--text); font-size: 0.79rem;
      padding: 0.28rem 0.7rem; border-radius: 6px;
      transition: border-color 0.2s, color 0.2s;
    }
    .pill:hover { border-color: rgba(0,212,170,0.35); color: var(--accent); }
    .pill.hi { background: rgba(0,212,170,0.08); border-color: rgba(0,212,170,0.2); color: var(--accent); }

    /* PERSONAL */
    .personal-grid {
      display: grid; grid-template-columns: 1.2fr 1fr;
      gap: 2rem; margin-top: 1.75rem; align-items: start;
    }
    .personal-text p { color: var(--muted); font-size: 0.92rem; line-height: 1.8; margin-bottom: 0.85rem; }
    .personal-text p strong { color: var(--text); font-weight: 700; }
    .personal-text p em { color: var(--accent); font-style: normal; }
    .personal-cards { display: flex; flex-direction: column; gap: 0.85rem; }
    .p-card {
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 12px; padding: 1rem 1.2rem;
      display: flex; align-items: flex-start; gap: 0.85rem;
      transition: border-color 0.2s;
    }
    .p-card:hover { border-color: rgba(0,212,170,0.3); }
    .p-card-icon { font-size: 1.35rem; flex-shrink: 0; margin-top: 0.05rem; }
    .p-card-text h4 { font-size: 0.87rem; font-weight: 700; color: var(--text); margin-bottom: 0.18rem; }
    .p-card-text p { font-size: 0.81rem; color: var(--muted); line-height: 1.55; }
    .badge {
      display: inline-flex; align-items: center; gap: 0.42rem;
      border-radius: 100px; font-size: 0.76rem; font-weight: 700;
      font-family: "Arial Narrow", Arial, sans-serif;
      padding: 0.25rem 0.72rem; margin-right: 0.4rem; margin-top: 0.35rem;
    }
    .badge-orange { background: rgba(255,107,53,0.1); border: 1px solid rgba(255,107,53,0.25); color: var(--accent3); }
    .badge-teal { background: rgba(0,212,170,0.08); border: 1px solid rgba(0,212,170,0.2); color: var(--accent); }

    /* CLOSING */
    .closing-inner {
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 20px; padding: 3.5rem; text-align: center;
      position: relative; overflow: hidden;
    }
    .closing-inner::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(ellipse 60% 60% at 50% 100%, rgba(0,212,170,0.05), transparent);
      pointer-events: none;
    }
    .closing-inner > * { position: relative; }
    .closing-inner p { color: var(--muted); font-size: 1rem; max-width: 540px; margin: 0 auto 2rem; line-height: 1.75; }
    .closing-inner p strong { color: var(--text); }

    /* DIVIDER */
    .divider {
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--border), transparent);
      margin: 0 2.5rem;
    }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border); padding: 1.5rem 2.5rem;
      display: flex; justify-content: space-between; align-items: center;
      max-width: 1200px; margin: 0 auto;
    }
    footer p { font-size: 0.78rem; color: var(--muted); }
    footer a { color: var(--accent); text-decoration: none; font-size: 0.78rem; font-weight: 700; }

    
      50% { transform: rotate(45deg) translateY(5px); opacity: 1; }
    }

    /* FADE IN */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .fade-in {
      opacity: 1;
      animation: fadeUp 0.65s ease both;
    }
    .fi1 { animation-delay: 0.1s; }
    .fi2 { animation-delay: 0.25s; }
    .fi3 { animation-delay: 0.4s; }
    .fi4 { animation-delay: 0.55s; }

    /* RESPONSIVE */
    @media (max-width: 950px) {
      .hero-content { grid-template-columns: 1fr; gap: 2.5rem; }
      .hero-right { align-items: flex-start; width: 100%; }
      .hero-stats { width: 100%; }
      .why-grid { grid-template-columns: 1fr 1fr; }
      .skills-grid { grid-template-columns: 1fr; }
      .personal-grid { grid-template-columns: 1fr; }
      .card-container { padding: 2rem; }
      .closing-inner { padding: 2.5rem 1.5rem; }
      .timeline::before { left: 80px; }
      .tl-item { grid-template-columns: 80px 1fr; gap: 1.25rem; }
      .tl-dot { left: 73px; }
      .section-wrap { padding: 4rem 1.5rem 1rem; }
    }
    @media (max-width: 600px) {
      .why-grid { grid-template-columns: 1fr; }
      nav { padding: 0.85rem 1.25rem; }
      .nav-links { display: none; flex-direction: column; gap: 0; }
      .nav-links.open {
        display: flex;
        position: fixed; top: 56px; left: 0; right: 0;
        background: rgba(11,15,20,0.97);
        backdrop-filter: blur(16px);
        border-bottom: 1px solid var(--border);
        padding: 0.5rem 0 1rem;
        z-index: 99;
      }
      .nav-links.open li { width: 100%; }
      .nav-links.open a {
        display: block; padding: 0.85rem 1.5rem;
        font-size: 0.9rem; border-bottom: 1px solid rgba(255,255,255,0.04);
      }
      .hamburger {
        display: flex; flex-direction: column; justify-content: space-between;
        width: 26px; height: 18px; background: none; border: none;
        cursor: pointer; padding: 0; z-index: 101;
      }
      .hamburger span {
        display: block; width: 100%; height: 2px;
        background: var(--accent); border-radius: 2px;
        transition: transform 0.25s, opacity 0.25s;
      }
      .hamburger.open span:nth-child(1) { transform: translateY(8px) rotate(45deg); }
      .hamburger.open span:nth-child(2) { opacity: 0; }
      .hamburger.open span:nth-child(3) { transform: translateY(-8px) rotate(-45deg); }
      h1 { font-size: 2.4rem; }
      h2 { font-size: 1.6rem; }
      .hero { padding: 7rem 1.25rem 3rem; }
      .hero-eyebrow { margin-top: 0.5rem; }
      .hero-stats { grid-template-columns: 1fr 1fr; }
      .stat-number { font-size: 1.6rem; }
      .photo-circle { width: 120px; height: 120px; }
      .section-wrap { padding: 3.5rem 1.25rem 1rem; }
      .card-container { padding: 1.5rem; }
      .closing-inner { padding: 2rem 1.25rem; }
      .tl-item { grid-template-columns: 70px 1fr; gap: 1rem; }
      .timeline::before { left: 70px; }
      .tl-dot { left: 63px; }
      .tl-year { font-size: 0.68rem; padding-right: 1rem; }
      .hero-cta { font-size: 0.82rem; padding: 0.75rem 1.25rem; }
      footer { flex-direction: column; gap: 0.5rem; text-align: center; padding: 1.25rem; }
    }
    @media (max-width: 400px) {
      h1 { font-size: 2rem; }
      .hero-stats { grid-template-columns: 1fr 1fr; }
      .why-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Kelsey Osman</div>
  <ul class="nav-links" id="navLinks">
    <li><a href="#why" onclick="closeMenu()">Why Lumin</a></li>
    <li><a href="#story" onclick="closeMenu()">My Story</a></li>
    <li><a href="#skills" onclick="closeMenu()">Skills</a></li>
    <li><a href="#human" onclick="closeMenu()">Beyond Work</a></li>
    <li><a href="#volunteer" onclick="closeMenu()">Giving Back</a></li>
    <li><a href="#connect" onclick="closeMenu()">Let's Talk</a></li>
  </ul>
  <button class="hamburger" id="hamburger" aria-label="Open menu" onclick="toggleMenu()">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-left">
      <div class="hero-eyebrow fade-in fi1">
        <span class="eyebrow-dot"></span>
        Here for Lumin Digital
      </div>
      <h1 class="fade-in fi2">
        <span class="name-line">Hi, I'm</span>
        <span class="title-line">Kelsey.</span>
      </h1>
      <p class="hero-desc fade-in fi3">
        I'm a product manager with <strong>7+ years in digital banking</strong> who genuinely loves this industry, cares deeply about the people using these products, and is ready to bring all of that to a team that's building something truly worth building.
      </p>
      <div class="fade-in fi4" style="display:flex; gap:0.75rem; flex-wrap:wrap;">
        <a href="https://www.linkedin.com/in/KelseyOsman" target="_blank" rel="noopener" class="hero-cta">
          Connect on LinkedIn
          <svg width="15" height="15" viewBox="0 0 16 16" fill="none">
            <path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </a>
      </div>
    </div>

    <div class="hero-right fade-in fi3">
      <div class="photo-area">
        <div class="photo-circle">
          <img src="data:image/jpeg;base64,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" alt="Kelsey Osman">
        </div>
      </div>

      <div class="hero-stats">
        <div class="stat-card">
          <div class="stat-number">7+</div>
          <div class="stat-label">Years in digital banking SaaS</div>
        </div>
        <div class="stat-card blue">
          <div class="stat-number">7</div>
          <div class="stat-label">Products owned simultaneously</div>
        </div>
        <div class="stat-card orange">
          <div class="stat-number">95%</div>
          <div class="stat-label">Roadmap say-do ratio</div>
        </div>
        <div class="stat-card mixed">
          <div class="stat-number">5+</div>
          <div class="stat-label">Fintech integrations shipped</div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- WHY LUMIN -->
<div class="section-wrap" id="why" style="scroll-margin-top:70px;">
  <div class="section-label">Why I'm Here</div>
  <h2>Lumin isn't just <em>a next job</em>.<br>It's the right one.</h2>
  <p class="section-intro">
    I've spent years across both branch banking software — where I watched on-premise systems get migrated to the cloud and felt every bit of that complexity — and digital banking products built for the cloud. That experience across both worlds gives me a clear-eyed view of what legacy infrastructure costs in speed, flexibility, and user experience. It's also exactly why Lumin's cloud-native foundation, built that way from day one, is so compelling to me.
  </p>
</div>
<div style="max-width:1200px; margin: 0 auto; padding: 0 2.5rem 3rem;">
  <div class="card-container">
    <div class="why-grid">
      <div class="why-card">
        <span class="why-icon">☁️</span>
        <h3>Built for the cloud — not retrofitted</h3>
        <p>I've felt the weight of legacy infrastructure daily. Lumin started <strong>cloud-native in 2016</strong> and never looked back. That's not just a tech advantage — it's a philosophy I want to build inside of.</p>
      </div>
      <div class="why-card">
        <span class="why-icon">🤝</span>
        <h3>People-first isn't a tagline here</h3>
        <p>98% of employees say Lumin is a great place to work. The CEO meets with every new hire personally. That's a culture I want to be part of long-term — not just pass through.</p>
      </div>
      <div class="why-card">
        <span class="why-icon">🌊</span>
        <h3>The ripple effect is real</h3>
        <p>Lumin's mission — empowering credit unions and community banks to better serve their members — is <strong>exactly the kind of impact</strong> I want to wake up and work toward every day.</p>
      </div>
      <div class="why-card">
        <span class="why-icon">🔥</span>
        <h3>Startup energy, proven momentum</h3>
        <p>$216M raised. Nearly 8M user accounts. 90+ FI clients. Still scrappy enough to challenge convention. That's my sweet spot — I thrive where teams move with <strong>purpose and speed</strong>.</p>
      </div>
      <div class="why-card">
        <span class="why-icon">📈</span>
        <h3>I want to grow here, not just work here</h3>
        <p>I'm not looking for a lateral move. I want to build toward <strong>senior product leadership</strong> at a company where bold ideas are expected, supported, and celebrated.</p>
      </div>
      <div class="why-card">
        <span class="why-icon">🧠</span>
        <h3>Curiosity is how I'm wired</h3>
        <p>"Powered by curiosity" resonates deeply with me. From hands-on AI experimentation to daily fintech podcasts, I actively invest in staying ahead — because great products require it.</p>
      </div>
    </div>
    <div class="quote-block">
      <p>"Strong leadership builds great products, which in turn create delighted clients."</p>
      <cite>— Lumin Digital's mission flywheel. I've read it a dozen times. It maps exactly to how I think about product.</cite>
    </div>
  </div>
</div>

<!-- CAREER STORY -->
<div class="section-wrap" id="story">
  <div class="section-label">My Story</div>
  <h2>Not a straight line.<br>A <em>deliberate arc</em>.</h2>
  <p class="section-intro">
    From learning how to talk to customers on a car rental lot to owning a 7-product digital banking portfolio — every chapter built something I still use every day. Business acumen. Client relationships. Storytelling. The ability to connect what a product does to <strong>why it matters to real people</strong>.
  </p>

  <div class="timeline">

    <!-- ENABLEMENT - current role -->
    <div class="tl-item">
      <div class="tl-year">Nov 2025–<br>Present</div>
      <div class="tl-dot"></div>
      <div class="tl-content">
        <h3>GTM Strategy & Sales Enablement</h3>
        <div class="tl-company">Candescent (NCR Voyix) · Atlanta, GA</div>
        <p>Moved into a dedicated GTM and sales enablement role with a mandate to <strong style="color:var(--text)">build the entire sales enablement engine from scratch</strong> — something that didn't exist before — across Candescent's full portfolio of Digital Banking and Branch solutions.
        <br><br>
        In just a few months: launched a net-new sales onboarding program, stood up a dedicated sales support channel that fields product questions and protects PM bandwidth, kicked off a Lunch &amp; Learn series, delivered product training aligned to active marketing campaigns, and built a scalable sales training framework now in active content development.
        <br><br>
        Work cross-functionally with Sales, Marketing, Product, and Customer Success to develop consistent messaging, competitive positioning, objection handling, and launch readiness — translating complex product functionality into clear, client-facing narratives that drive adoption and revenue across the entire organization.</p>
        <div class="tl-tags">
          <span class="tl-tag">GTM Strategy &amp; Execution</span>
          <span class="tl-tag">Sales Enablement</span>
          <span class="tl-tag">Onboarding Programs</span>
          <span class="tl-tag">Product Training</span>
          <span class="tl-tag">Competitive Positioning</span>
          <span class="tl-tag">Messaging &amp; Positioning</span>
          <span class="tl-tag">Cross-Functional Alignment</span>
          <span class="tl-tag">Launch Planning</span>
        </div>
      </div>
    </div>

    <!-- PM -->
    <div class="tl-item">
      <div class="tl-year">2021–<br>Nov 2025</div>
      <div class="tl-dot" style="background:var(--accent);box-shadow:0 0 10px rgba(0,212,170,0.4);"></div>
      <div class="tl-content">
        <h3>Product Manager — Digital Banking Portfolio</h3>
        <div class="tl-company">Candescent (NCR Voyix) · Atlanta, GA</div>
        <p>Owned 7 products across a digital banking platform serving 1,300+ banks and credit unions, launching 4 add-ons and 15+ features annually while maintaining a 95% roadmap say-do ratio. Led end-to-end 0→1 development of a native goal-based savings product and shipped API/SDK integrations with Greenlight, MX, SavvyMoney, and 5+ additional third-party vendors.
        <br><br>
        Project-managed the design and delivery of <strong style="color:var(--text)">3 production-level demo environments</strong> showcasing the full Candescent product portfolio — writing requirements, coordinating across multiple engineering and product teams, leading QA and testing, integrating TPVs, and planning the change management for internal rollout. These environments became a key asset for sales and executive client presentations.</p>
        <div class="tl-tags">
          <span class="tl-tag">0→1 Product</span>
          <span class="tl-tag">API / SDK Integrations</span>
          <span class="tl-tag">Strategic Roadmapping</span>
          <span class="tl-tag">SAFe Agile</span>
          <span class="tl-tag">GTM Assets</span>
          <span class="tl-tag">Pricing &amp; Packaging</span>
          <span class="tl-tag">Executive Presentations</span>
          <span class="tl-tag">Demo Environments</span>
          <span class="tl-tag">A/B Testing</span>
          <span class="tl-tag">Change Management</span>
        </div>
      </div>
    </div>

    <!-- PMM -->
    <div class="tl-item">
      <div class="tl-year">2019–<br>2021</div>
      <div class="tl-dot" style="background:var(--accent2);box-shadow:0 0 10px rgba(0,144,255,0.5);"></div>
      <div class="tl-content">
        <h3>Product Marketing Manager</h3>
        <div class="tl-company" style="color:var(--accent2);">Candescent (NCR Voyix) · Atlanta, GA</div>
        <p>Built a services-focused product architecture aligning 100+ Professional Services offers to core product strategy, increasing sales 15% YoY. Grew the services pipeline 10% annually through standardized sales enablement materials, subscription pricing, and executive-facing GTM assets — acting as a bridge between product, services, and sales.</p>
        <div class="tl-tags">
          <span class="tl-tag blue">GTM Assets</span>
          <span class="tl-tag blue">Executive Presentations</span>
          <span class="tl-tag blue">Sales Enablement</span>
          <span class="tl-tag blue">Subscription Pricing</span>
          <span class="tl-tag blue">Cross-Functional Leadership</span>
        </div>
      </div>
    </div>

    <!-- IRIS -->
    <div class="tl-item">
      <div class="tl-year">2019</div>
      <div class="tl-dot" style="background:var(--accent3);box-shadow:0 0 10px rgba(255,107,53,0.5);"></div>
      <div class="tl-content">
        <h3>Senior Marketing Manager</h3>
        <div class="tl-company" style="color:var(--accent3);">Iris Worldwide · Atlanta, GA — Agency of Record for Lamborghini North America</div>
        <p>Designed and executed a 5-day exclusive pro-driver experience for Lamborghini owners across 3 cities. Built client-facing presentations and GTM event assets. Sharpened skills in high-stakes executive storytelling and luxury brand experience that translate directly into how I communicate product value today.</p>
        <div class="tl-tags">
          <span class="tl-tag orange">Client-Facing Presentations</span>
          <span class="tl-tag orange">GTM Assets</span>
          <span class="tl-tag orange">Event Strategy</span>
        </div>
      </div>
    </div>

    <!-- JACK MORTON -->
    <div class="tl-item">
      <div class="tl-year">2014–<br>2019</div>
      <div class="tl-dot" style="background:var(--accent3);box-shadow:0 0 8px rgba(255,107,53,0.4);"></div>
      <div class="tl-content">
        <h3>Senior Market Associate</h3>
        <div class="tl-company" style="color:var(--accent3);">Jack Morton Worldwide · Alpharetta, GA — Agency of Record for General Motors</div>
        <p>Led localization of GM's national Making Strides Against Breast Cancer campaign across 500+ stores, increasing national revenue 29% through experiential and digital engagement strategy. Drove $2.75M in annual program revenue by managing $1M in client contracts, redesigning the end-to-end purchasing experience, and increasing participation 10%. Built customer-facing presentations and GTM materials for GM marketing leadership and dealership partners nationwide.</p>
        <div class="tl-tags">
          <span class="tl-tag orange">Customer-Facing Presentations</span>
          <span class="tl-tag orange">GTM Assets</span>
          <span class="tl-tag orange">Revenue Growth</span>
          <span class="tl-tag orange">User Empathy</span>
          <span class="tl-tag orange">Storytelling</span>
        </div>
      </div>
    </div>

    <!-- HEADWAY -->
    <div class="tl-item">
      <div class="tl-year">2012–<br>2014</div>
      <div class="tl-dot" style="background:var(--muted);box-shadow:0 0 7px rgba(138,157,181,0.35);"></div>
      <div class="tl-content">
        <h3>Marketing Coordinator</h3>
        <div class="tl-company" style="color:var(--muted);">Headway Marketing · Experiential Agency — GM / Jack Morton Partner</div>
        <p>Supported GM experiential marketing programs within the Jack Morton agency network. Executed and grew Chevrolet's free youth baseball and soccer programs — expanding the markets they reached and connecting the brand to families and communities in a meaningful way. Built foundational skills in client-facing execution, marketing operations, and GTM materials that drove dealership engagement and brand visibility.</p>
        <div class="tl-tags">
          <span class="tl-tag grey">Youth Community Programs</span>
          <span class="tl-tag grey">Program Growth</span>
          <span class="tl-tag grey">Event Marketing</span>
          <span class="tl-tag grey">Client Engagement</span>
          <span class="tl-tag grey">GTM Assets</span>
        </div>
      </div>
    </div>

    <!-- ENTERPRISE -->
    <div class="tl-item">
      <div class="tl-year">2010–<br>2012</div>
      <div class="tl-dot" style="background:var(--muted);box-shadow:0 0 7px rgba(138,157,181,0.25);"></div>
      <div class="tl-content">
        <h3>Management Trainee</h3>
        <div class="tl-company" style="color:var(--muted);">Enterprise Rent-A-Car</div>
        <p>Launched my career in Enterprise's management training program — widely known as one of the best first jobs for building customer-facing communication, business development, and relationship management skills. Those fundamentals still show up in how I work with clients, stakeholders, and teammates today.</p>
        <div class="tl-tags">
          <span class="tl-tag grey">Sales & Relationship Building</span>
          <span class="tl-tag grey">Customer-Facing Communication</span>
          <span class="tl-tag grey">Business Development</span>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- SKILLS -->
<div class="section-wrap" id="skills">
  <div class="section-label">What I Bring</div>
  <h2>Skills built <em>in the field</em>,<br>not just the classroom.</h2>
  <p class="section-intro">
    A combination of strategic thinking, technical fluency, and the human skills that actually get products shipped — earned across 7 years of enterprise fintech PM work and a career that started by learning how to really listen to people.
  </p>
  <div class="skills-grid">
    <div class="skill-group">
      <div class="skill-group-title">Product Strategy & Delivery</div>
      <div class="skill-pills">
        <span class="pill hi">Digital Banking Domain</span>
        <span class="pill hi">0→1 Product Development</span>
        <span class="pill hi">Strategic Roadmapping & Planning</span>
        <span class="pill">Product Lifecycle Management</span>
        <span class="pill">API & SDK Integrations</span>
        <span class="pill">Multi-Tenant SaaS</span>
        <span class="pill">SAFe Agile</span>
        <span class="pill">A/B Testing</span>
        <span class="pill">Requirements Writing</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">GTM, Growth & Communication</div>
      <div class="skill-pills">
        <span class="pill hi">GTM Strategy & Asset Development</span>
        <span class="pill hi">Executive & Client Presentations</span>
        <span class="pill hi">Pricing & Packaging</span>
        <span class="pill">Sales Enablement</span>
        <span class="pill">Revenue Expansion</span>
        <span class="pill">Engagement & Retention</span>
        <span class="pill">Advisory Board Facilitation</span>
        <span class="pill">Vendor & Partner Management</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Leadership & Cross-Functional</div>
      <div class="skill-pills">
        <span class="pill hi">Cross-Functional Team Leadership</span>
        <span class="pill">Stakeholder Alignment</span>
        <span class="pill">Change Management</span>
        <span class="pill">Project Management</span>
        <span class="pill">12+ PM Collaboration</span>
        <span class="pill">Client & Advisory Engagement</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Tools</div>
      <div class="skill-pills">
        <span class="pill">Jira / JiraAlign</span>
        <span class="pill">Confluence</span>
        <span class="pill">Figma</span>
        <span class="pill">Salesforce</span>
        <span class="pill">Google Looker</span>
        <span class="pill">Smartsheets</span>
        <span class="pill hi">AI / Claude (hands-on)</span>
        <span class="pill">Microsoft Suite</span>
        <span class="pill">Slack</span>
      </div>
    </div>
  </div>
</div>

<!-- BEYOND WORK -->
<div class="section-wrap" id="human">
  <div class="section-label">Beyond the Resume</div>
  <h2>Products are built by <em>people</em>.<br>Here's a bit of mine.</h2>
  <p class="section-intro">
    I think the best PMs bring their whole selves to the work — the curiosity, the drive, and the genuine warmth for the people on the other side of the screen. Here's what that looks like for me.
  </p>
  <div class="personal-grid">
    <div class="personal-text">
      <p>
        At my core, I believe the best products come from <em>genuinely caring about people</em> — the end users trying to manage their financial lives, the financial institutions trying to serve their communities, and the teammates building alongside you. Financial wellness isn't just a product category to me; it's something that affects real families every day, and I take that seriously. That's not a value on a slide deck. It's how I've worked every single day.
      </p>
      <p>
        I stay curious on purpose. Most mornings start with <strong>the news and markets</strong> before veering into behavioral science and fintech podcasts — it's just how I'm wired. I also invest in continuing education whenever something worth diving into comes along. I don't wait for the industry to come to me.
      </p>
      <p>
        I stay grounded through movement — <strong>yoga 4 days a week</strong>, running a few times a week, and 8 half marathons behind me with plans for a 9th this year. There's something about training that maps perfectly to product: consistency, patience, and knowing that showing up every day is how you get somewhere great.
      </p>
      <p>
        And then there's <strong>Pluto 🐾</strong> — my rescue pup, adopted at 4 years old (he's 7 now and thriving). I fostered several dogs before finding my guy, and it's been one of the best decisions I've made. He's a daily reminder that showing up for the ones who need you is always worth it.
      </p>
      <div>
        <span class="badge badge-orange">🏃‍♀️ 8 half marathons · #9 coming soon</span>
        <span class="badge badge-teal">🐶 Dog mom to Pluto (rescue)</span>
      </div>
    </div>
    <div class="personal-cards">
      <div class="p-card">
        <div class="p-card-icon">🎯</div>
        <div class="p-card-text">
          <h4>Driven, not just busy</h4>
          <p>A 95% roadmap say-do ratio isn't a happy accident — it's what happens when you care about delivering what you commit to, every single sprint.</p>
        </div>
      </div>
      <div class="p-card">
        <div class="p-card-icon">🤝</div>
        <div class="p-card-text">
          <h4>A connector — professionally and personally</h4>
          <p>I genuinely enjoy building relationships across teams, clients, and communities. People trust me because I show up as a human first, every time — inside work and out.</p>
        </div>
      </div>
      <div class="p-card">
        <div class="p-card-icon">📖</div>
        <div class="p-card-text">
          <h4>Learning every morning</h4>
          <p>Daily podcasts, continuing education, hands-on AI experimentation. I treat learning like training — consistent, intentional, always building toward something.</p>
        </div>
      </div>
      <div class="p-card">
        <div class="p-card-icon">🏆</div>
        <div class="p-card-text">
          <h4>Competitive in the best way</h4>
          <p>I like winning — for the team, for the client, for the user. That drive shows up in the metrics, in the follow-through, and in never leaving a problem half-solved.</p>
        </div>
      </div>
      <div class="p-card">
        <div class="p-card-icon">💬</div>
        <div class="p-card-text">
          <h4>I build where nothing existed</h4>
          <p>Whether it's a 0→1 product, a sales enablement engine, or a community program — I'm energized by ambiguity. I like bringing structure to chaos and leaving things better than I found them.</p>
        </div>
      </div>
      <div class="p-card">
        <div class="p-card-icon">📍</div>
        <div class="p-card-text">
          <h4>Denver, CO · Remote-first · Open to travel</h4>
          <p>Currently fully remote and loving it. Open to travel up to 10–20% for the right team moments — client visits, offsites, and the kind of in-person time that actually matters.</p>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="divider"></div>

<!-- VOLUNTEER -->
<div class="section-wrap" id="volunteer">
  <div class="section-label">Giving Back</div>
  <h2>Community isn't just <em>a nice-to-have</em>.</h2>
  <p class="section-intro">
    Outside of work, I've spent years investing in communities — leading programs, serving on boards, and showing up for causes I believe in. It's the same muscle I bring to work every day: connect, build, make it better.
  </p>
  <div class="skills-grid">
    <div class="skill-group">
      <div class="skill-group-title">Hands On Atlanta &nbsp;·&nbsp; 2012–2025</div>
      <div style="font-size:0.88rem; color:var(--muted); line-height:1.75; margin-bottom:0.85rem;">
        Over 13 years of volunteer engagement with one of Atlanta's leading civic organizations — from hands-on community service to formal leadership roles.
      </div>
      <div class="skill-pills">
        <span class="pill hi">Civic Leadership Program</span>
        <span class="pill hi">Young Professionals Board</span>
        <span class="pill">Built internal training guides for customer support</span>
        <span class="pill">Long-term volunteer (13 years)</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Junior League of Atlanta &nbsp;·&nbsp; 2022–2023</div>
      <div style="font-size:0.88rem; color:var(--muted); line-height:1.75; margin-bottom:0.85rem;">
        Member of the Junior League of Atlanta — an organization of women committed to promoting voluntarism and developing the potential of women while improving communities.
      </div>
      <div class="skill-pills">
        <span class="pill">Community Development</span>
        <span class="pill">Women's Leadership</span>
        <span class="pill">Civic Engagement</span>
      </div>
    </div>
  </div>
  <div class="skills-grid" style="margin-top:1.1rem;">
    <div class="skill-group">
      <div class="skill-group-title">Young Women Leaders Forum &nbsp;·&nbsp; 2023–2025</div>
      <div style="font-size:0.88rem; color:var(--muted); line-height:1.75; margin-bottom:0.85rem;">
        Member of YWLF — a women's group focused on mid-career women achieving leadership success as their fully authentic selves through transformational professional development, impactful peer-to-peer sharing and ongoing community conversations.
      </div>
      <div class="skill-pills">
        <span class="pill">Community Development</span>
        <span class="pill">Women's Leadership</span>
        <span class="pill">Civic Engagement</span>
      </div>
    </div>
  </div>
</div>

<div class="divider"></div>

<!-- CLOSING CTA -->
<div class="section-wrap" id="connect" style="padding-bottom: 2rem;">
  <div class="closing-inner">
    <div class="section-label" style="justify-content:center;">Ready When You Are</div>
    <h2 style="margin-bottom:0.75rem;">Let's build something<br><em>worth building</em>.</h2>
    <p>
      I bring 7+ years of digital banking product expertise, a genuine love for this industry, and the kind of drive that doesn't clock out at 5pm. I'm excited about what Lumin is building — and I'd love to be part of it. <strong>Let's talk.</strong>
    </p>
    <a href="https://www.linkedin.com/in/KelseyOsman" target="_blank" rel="noopener" class="hero-cta" style="margin: 0 auto;">
      View My LinkedIn Profile
      <svg width="15" height="15" viewBox="0 0 16 16" fill="none">
        <path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </a>
    <div style="margin-top:1.5rem; font-size:0.83rem; color:var(--muted);">
      📍 Denver, CO &nbsp;·&nbsp; Open to 10–20% travel
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <p>Kelsey Osman · Product Manager
</footer>
<script>
  function toggleMenu() {
    const menu = document.getElementById('navLinks');
    const btn = document.getElementById('hamburger');
    menu.classList.toggle('open');
    btn.classList.toggle('open');
  }
  function closeMenu() {
    document.getElementById('navLinks').classList.remove('open');
    document.getElementById('hamburger').classList.remove('open');
  }
  // Close on outside tap
  document.addEventListener('click', function(e) {
    const menu = document.getElementById('navLinks');
    const btn = document.getElementById('hamburger');
    if (menu.classList.contains('open') && !menu.contains(e.target) && !btn.contains(e.target)) {
      closeMenu();
    }
  });

  const navLinks = document.querySelectorAll('.nav-links a');
  const sectionIds = ['why','story','skills','human','volunteer','connect'];

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const id = entry.target.getAttribute('id');
        navLinks.forEach(link => {
          link.classList.remove('active');
          if (link.getAttribute('href') === '#' + id) {
            link.classList.add('active');
          }
        });
      }
    });
  }, { rootMargin: '-20% 0px -70% 0px', threshold: 0 });

  sectionIds.forEach(id => {
    const el = document.getElementById(id);
    if (el) observer.observe(el);
  });
</script>
