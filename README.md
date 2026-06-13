<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bob Thambeliyagoda — Mechanical Engineer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #f8f8f6;
      --surface: #ffffff;
      --border: #e2e0d8;
      --border-strong: #c8c6bc;
      --text-primary: #1a1a18;
      --text-secondary: #5a5a56;
      --text-muted: #8a8a84;
      --accent: #1a5cb8;
      --accent-light: #e8f0fb;
      --accent-dim: #b3c8ea;
      --tag-bg: #eef2f9;
      --tag-text: #1a4a8a;
      --success: #0f6e56;
      --success-bg: #e1f5ee;
      --mono: 'JetBrains Mono', monospace;
      --sans: 'Inter', sans-serif;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: var(--sans);
      background: var(--bg);
      color: var(--text-primary);
      line-height: 1.6;
      font-size: 16px;
    }

    /* ── NAV ── */
    nav {
      position: sticky;
      top: 0;
      z-index: 100;
      background: rgba(248, 248, 246, 0.92);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--border);
      padding: 0 2rem;
    }
    .nav-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 60px;
    }
    .nav-logo {
      font-family: var(--mono);
      font-size: 14px;
      font-weight: 500;
      color: var(--text-primary);
      text-decoration: none;
      letter-spacing: -0.02em;
    }
    .nav-logo span { color: var(--accent); }
    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }
    .nav-links a {
      font-size: 14px;
      color: var(--text-secondary);
      text-decoration: none;
      transition: color 0.15s;
      letter-spacing: 0.01em;
    }
    .nav-links a:hover { color: var(--accent); }
    .nav-cta {
      font-size: 13px;
      font-weight: 500;
      color: var(--accent);
      text-decoration: none;
      border: 1px solid var(--accent-dim);
      padding: 6px 16px;
      border-radius: 6px;
      transition: background 0.15s;
    }
    .nav-cta:hover { background: var(--accent-light); }

    /* ── LAYOUT ── */
    .container { max-width: 1100px; margin: 0 auto; padding: 0 2rem; }
    section { padding: 80px 0; }
    .section-label {
      font-family: var(--mono);
      font-size: 11px;
      font-weight: 500;
      color: var(--accent);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: 1rem;
    }
    h2 {
      font-size: 2rem;
      font-weight: 600;
      letter-spacing: -0.03em;
      color: var(--text-primary);
      margin-bottom: 0.5rem;
    }
    .section-sub {
      font-size: 16px;
      color: var(--text-secondary);
      margin-bottom: 3rem;
      max-width: 560px;
    }
    .divider { border: none; border-top: 1px solid var(--border); }

    /* ── HERO ── */
    #hero {
      padding: 100px 0 80px;
      position: relative;
      overflow: hidden;
    }
    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 380px;
      gap: 4rem;
      align-items: center;
    }
    .hero-eyebrow {
      font-family: var(--mono);
      font-size: 12px;
      color: var(--accent);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .hero-eyebrow::before {
      content: '';
      display: inline-block;
      width: 24px;
      height: 1px;
      background: var(--accent);
    }
    h1 {
      font-size: clamp(2.4rem, 4vw, 3.4rem);
      font-weight: 600;
      letter-spacing: -0.04em;
      line-height: 1.08;
      margin-bottom: 1.5rem;
      color: var(--text-primary);
    }
    h1 .name-accent { color: var(--accent); }
    .hero-desc {
      font-size: 18px;
      color: var(--text-secondary);
      line-height: 1.65;
      margin-bottom: 2.5rem;
      max-width: 520px;
    }
    .hero-actions { display: flex; gap: 12px; flex-wrap: wrap; }
    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: var(--accent);
      color: #fff;
      font-family: var(--sans);
      font-size: 14px;
      font-weight: 500;
      padding: 10px 22px;
      border-radius: 8px;
      text-decoration: none;
      transition: opacity 0.15s;
    }
    .btn-primary:hover { opacity: 0.88; }
    .btn-outline {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border: 1px solid var(--border-strong);
      color: var(--text-primary);
      font-family: var(--sans);
      font-size: 14px;
      font-weight: 500;
      padding: 10px 22px;
      border-radius: 8px;
      text-decoration: none;
      background: var(--surface);
      transition: border-color 0.15s, background 0.15s;
    }
    .btn-outline:hover { border-color: var(--accent-dim); background: var(--accent-light); }

    /* Hero card panel */
    .hero-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 2rem;
    }
    .hero-avatar {
      width: 64px;
      height: 64px;
      border-radius: 50%;
      background: var(--accent-light);
      border: 2px solid var(--accent-dim);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 22px;
      font-weight: 600;
      color: var(--accent);
      margin-bottom: 1.25rem;
      font-family: var(--mono);
    }
    .hero-card-name {
      font-size: 16px;
      font-weight: 600;
      margin-bottom: 2px;
    }
    .hero-card-role {
      font-size: 13px;
      color: var(--text-secondary);
      margin-bottom: 1.25rem;
    }
    .stat-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      margin-bottom: 1.25rem;
    }
    .stat-box {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 10px 12px;
    }
    .stat-val {
      font-family: var(--mono);
      font-size: 18px;
      font-weight: 500;
      color: var(--accent);
      display: block;
    }
    .stat-label {
      font-size: 11px;
      color: var(--text-muted);
    }
    .status-pill {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-size: 12px;
      color: var(--success);
      background: var(--success-bg);
      border-radius: 20px;
      padding: 4px 10px;
      margin-bottom: 1rem;
    }
    .status-dot {
      width: 6px; height: 6px;
      border-radius: 50%;
      background: var(--success);
    }
    .skill-chips { display: flex; flex-wrap: wrap; gap: 6px; }
    .chip {
      font-family: var(--mono);
      font-size: 11px;
      background: var(--tag-bg);
      color: var(--tag-text);
      padding: 4px 9px;
      border-radius: 5px;
      border: 1px solid var(--accent-dim);
    }

    /* ── PROJECTS ── */
    #projects { background: var(--surface); }
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 1.5rem;
    }
    .project-card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 1.75rem;
      display: flex;
      flex-direction: column;
      transition: border-color 0.2s, box-shadow 0.2s;
      text-decoration: none;
      color: inherit;
    }
    .project-card:hover {
      border-color: var(--accent-dim);
      box-shadow: 0 4px 20px rgba(26,92,184,0.06);
    }
    .project-header {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      margin-bottom: 1rem;
    }
    .project-icon {
      width: 40px; height: 40px;
      border-radius: 10px;
      background: var(--accent-light);
      border: 1px solid var(--accent-dim);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
    }
    .project-badge {
      font-family: var(--mono);
      font-size: 10px;
      color: var(--success);
      background: var(--success-bg);
      padding: 3px 8px;
      border-radius: 4px;
      font-weight: 500;
    }
    .project-badge.planned {
      color: #7a5c00;
      background: #fef3c7;
    }
    .project-title {
      font-size: 17px;
      font-weight: 600;
      letter-spacing: -0.02em;
      margin-bottom: 0.5rem;
    }
    .project-org {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--text-muted);
      margin-bottom: 0.75rem;
    }
    .project-desc {
      font-size: 14px;
      color: var(--text-secondary);
      line-height: 1.6;
      margin-bottom: 1.25rem;
      flex-grow: 1;
    }
    .project-tags { display: flex; flex-wrap: wrap; gap: 6px; }
    .tag {
      font-family: var(--mono);
      font-size: 11px;
      background: var(--tag-bg);
      color: var(--tag-text);
      padding: 3px 8px;
      border-radius: 4px;
    }

    /* ── BLOG ── */
    #blog { }
    .blog-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.25rem;
    }
    .blog-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 1.5rem;
      text-decoration: none;
      color: inherit;
      display: flex;
      flex-direction: column;
      transition: border-color 0.2s;
    }
    .blog-card:hover { border-color: var(--accent-dim); }
    .blog-date {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--text-muted);
      margin-bottom: 0.75rem;
    }
    .blog-title {
      font-size: 16px;
      font-weight: 600;
      letter-spacing: -0.02em;
      margin-bottom: 0.5rem;
      line-height: 1.3;
    }
    .blog-excerpt {
      font-size: 14px;
      color: var(--text-secondary);
      line-height: 1.6;
      flex-grow: 1;
      margin-bottom: 1rem;
    }
    .blog-tag {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--accent);
      background: var(--accent-light);
      padding: 3px 8px;
      border-radius: 4px;
      align-self: flex-start;
    }

    /* ── RESUME ── */
    #resume { background: var(--surface); }
    .resume-layout {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
    }
    .resume-col h3 {
      font-size: 13px;
      font-family: var(--mono);
      color: var(--accent);
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
      padding-bottom: 0.5rem;
      border-bottom: 1px solid var(--border);
    }
    .resume-item { margin-bottom: 1.5rem; }
    .resume-item-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 4px;
    }
    .resume-item-title {
      font-size: 15px;
      font-weight: 600;
      letter-spacing: -0.01em;
    }
    .resume-item-date {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--text-muted);
      white-space: nowrap;
      margin-left: 8px;
    }
    .resume-item-org {
      font-size: 13px;
      color: var(--accent);
      margin-bottom: 6px;
    }
    .resume-item-desc {
      font-size: 13px;
      color: var(--text-secondary);
      line-height: 1.6;
    }
    .skills-list {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    .skill-group-label {
      font-size: 13px;
      font-weight: 500;
      color: var(--text-secondary);
      margin-bottom: 6px;
    }
    .skill-chips-sm { display: flex; flex-wrap: wrap; gap: 6px; }
    .chip-sm {
      font-family: var(--mono);
      font-size: 11px;
      background: var(--bg);
      color: var(--text-secondary);
      padding: 4px 9px;
      border-radius: 5px;
      border: 1px solid var(--border);
    }
    .resume-download-row {
      margin-top: 2.5rem;
      display: flex;
      align-items: center;
      gap: 1rem;
    }

    /* ── CONTACT ── */
    #contact { }
    .contact-layout {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
    }
    .contact-desc {
      font-size: 16px;
      color: var(--text-secondary);
      line-height: 1.7;
      margin-bottom: 2rem;
    }
    .contact-links { display: flex; flex-direction: column; gap: 1rem; }
    .contact-link {
      display: flex;
      align-items: center;
      gap: 12px;
      text-decoration: none;
      color: var(--text-secondary);
      font-size: 14px;
      transition: color 0.15s;
    }
    .contact-link:hover { color: var(--accent); }
    .contact-link-icon {
      width: 36px; height: 36px;
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 16px;
    }
    .contact-form {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 2rem;
    }
    .form-row { margin-bottom: 1.25rem; }
    .form-row label {
      display: block;
      font-size: 13px;
      font-weight: 500;
      color: var(--text-secondary);
      margin-bottom: 6px;
    }
    .form-row input,
    .form-row textarea,
    .form-row select {
      width: 100%;
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 10px 14px;
      font-family: var(--sans);
      font-size: 14px;
      background: var(--bg);
      color: var(--text-primary);
      outline: none;
      transition: border-color 0.15s;
      resize: none;
    }
    .form-row input:focus,
    .form-row textarea:focus,
    .form-row select:focus { border-color: var(--accent-dim); background: #fff; }
    .form-submit {
      width: 100%;
      background: var(--accent);
      color: #fff;
      border: none;
      border-radius: 8px;
      padding: 12px;
      font-family: var(--sans);
      font-size: 14px;
      font-weight: 500;
      cursor: pointer;
      transition: opacity 0.15s;
    }
    .form-submit:hover { opacity: 0.88; }
    .form-success {
      display: none;
      background: var(--success-bg);
      color: var(--success);
      border-radius: 8px;
      padding: 1rem;
      font-size: 14px;
      text-align: center;
      margin-top: 1rem;
    }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--border);
      padding: 2rem;
      text-align: center;
    }
    .footer-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }
    .footer-copy {
      font-family: var(--mono);
      font-size: 12px;
      color: var(--text-muted);
    }
    .footer-links { display: flex; gap: 1.5rem; }
    .footer-links a {
      font-size: 13px;
      color: var(--text-muted);
      text-decoration: none;
    }
    .footer-links a:hover { color: var(--accent); }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      .hero-grid { grid-template-columns: 1fr; }
      .hero-card { display: none; }
      .resume-layout { grid-template-columns: 1fr; }
      .contact-layout { grid-template-columns: 1fr; }
      h2 { font-size: 1.6rem; }
      .nav-links { display: none; }
    }

    /* Blueprint grid background on hero */
    #hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(26,92,184,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(26,92,184,0.04) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
    }
    #hero .container { position: relative; }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-inner">
      <a href="#hero" class="nav-logo">bob<span>.eng</span></a>
      <ul class="nav-links">
        <li><a href="#projects">Projects</a></li>
        <li><a href="#blog">Blog</a></li>
        <li><a href="#resume">Resume</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <a href="mailto:loch@buffalo.edu" class="nav-cta">Get in touch →</a>
    </div>
  </nav>

  <!-- HERO -->
  <section id="hero">
    <div class="container">
      <div class="hero-grid">
        <div>
          <p class="hero-eyebrow">Mechanical Engineer · Inventor · Future Patent Attorney</p>
          <h1>Building things that<br /><span class="name-accent">actually work.</span></h1>
          <p class="hero-desc">
            Sophomore ME student at University at Buffalo. I design and build CubeSat payloads, competition rovers, and embedded systems — then think carefully about how innovation gets protected.
          </p>
          <div class="hero-actions">
            <a href="#projects" class="btn-primary">View my work →</a>
            <a href="#resume" class="btn-outline">Download resume</a>
          </div>
        </div>

        <div class="hero-card">
          <div class="hero-avatar">BT</div>
          <p class="hero-card-name">Lochitha (Bob) Thambeliyagoda</p>
          <p class="hero-card-role">B.S. Mechanical Engineering · UB '29</p>
          <div class="status-pill">
            <span class="status-dot"></span>
            Open to internships & research
          </div>
          <div class="stat-row">
            <div class="stat-box">
              <span class="stat-val">3</span>
              <span class="stat-label">Active projects</span>
            </div>
            <div class="stat-box">
              <span class="stat-val">5+</span>
              <span class="stat-label">Tools & languages</span>
            </div>
            <div class="stat-box">
              <span class="stat-val">NASA</span>
              <span class="stat-label">CubeSat funding</span>
            </div>
            <div class="stat-box">
              <span class="stat-val">ASME</span>
              <span class="stat-label">IAM3D Rover</span>
            </div>
          </div>
          <div class="skill-chips">
            <span class="chip">SolidWorks</span>
            <span class="chip">Fusion 360</span>
            <span class="chip">ESP32</span>
            <span class="chip">MATLAB</span>
            <span class="chip">Arduino</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <hr class="divider" />

  <!-- PROJECTS -->
  <section id="projects">
    <div class="container">
      <p class="section-label">// engineering work</p>
      <h2>Projects</h2>
      <p class="section-sub">Hardware, firmware, and fabrication — from orbit to the workshop floor.</p>

      <div class="projects-grid">

        <a class="project-card" href="#projects">
          <div class="project-header">
            <div class="project-icon">🛰️</div>
            <span class="project-badge">Active</span>
          </div>
          <p class="project-org">LASAGNA-E · NASA-funded CubeSat</p>
          <h3 class="project-title">CubeSat Payload Structures</h3>
          <p class="project-desc">
            Structures Lead on a 1U CubeSat payload designed to survive launch loads and operate in LEO. Responsible for mechanical design, tolerance stack-up analysis, and ensuring structural integrity through vibration and thermal cycles.
          </p>
          <div class="project-tags">
            <span class="tag">SolidWorks</span>
            <span class="tag">FEA</span>
            <span class="tag">CubeSat Standard</span>
            <span class="tag">NASA CSLI</span>
          </div>
        </a>

        <a class="project-card" href="#projects">
          <div class="project-header">
            <div class="project-icon">🤖</div>
            <span class="project-badge">Active</span>
          </div>
          <p class="project-org">The Axolotl · ASME IAM3D Competition</p>
          <h3 class="project-title">Competition Rover — Manufacturing Lead</h3>
          <p class="project-desc">
            Co-leading manufacturing for a lightweight competition rover. Overseeing fabrication strategy, DFM decisions, and assembly tolerances across a multi-discipline student team. Extensive use of FDM and SLA printing.
          </p>
          <div class="project-tags">
            <span class="tag">Fusion 360</span>
            <span class="tag">FDM / SLA</span>
            <span class="tag">DFM</span>
            <span class="tag">Team Lead</span>
          </div>
        </a>

        <a class="project-card" href="#projects">
          <div class="project-header">
            <div class="project-icon">🎯</div>
            <span class="project-badge">Active</span>
          </div>
          <p class="project-org">Personal Project · Embedded Systems</p>
          <h3 class="project-title">PuttPal — LiDAR Golf Assistant</h3>
          <p class="project-desc">
            Arduino/Raspberry Pi device using LiDAR to measure green slope and suggest putting line. Hardware prototyped from scratch, firmware written in C/Python. Exploring integration with a TFT display and BLE output.
          </p>
          <div class="project-tags">
            <span class="tag">Arduino</span>
            <span class="tag">Raspberry Pi</span>
            <span class="tag">LiDAR</span>
            <span class="tag">Python</span>
            <span class="tag">C</span>
          </div>
        </a>

        <a class="project-card" href="#projects">
          <div class="project-header">
            <div class="project-icon">🗣️</div>
            <span class="project-badge">Active</span>
          </div>
          <p class="project-org">Personal Project · Edge AI</p>
          <h3 class="project-title">ESP32-S3 AI Voice Assistant</h3>
          <p class="project-desc">
            Offline-capable voice assistant on an ESP32-S3 with a 1.3" TFT display. Using ESP-SR for on-device wake word detection and INMP441 I2S microphone. OpenAI Whisper API as cloud STT fallback.
          </p>
          <div class="project-tags">
            <span class="tag">ESP32-S3</span>
            <span class="tag">ESP-SR</span>
            <span class="tag">I2S / INMP441</span>
            <span class="tag">Whisper API</span>
          </div>
        </a>

        <a class="project-card" href="#projects">
          <div class="project-header">
            <div class="project-icon">🖨️</div>
            <span class="project-badge">Completed</span>
          </div>
          <p class="project-org">Personal · Fabrication</p>
          <h3 class="project-title">3D Printing Farm Build</h3>
          <p class="project-desc">
            Self-built and repaired a multi-printer FDM farm. Taught myself Marlin firmware configuration, bed leveling automation, and CNC routing for enclosure panels. Ongoing source of test parts for other projects.
          </p>
          <div class="project-tags">
            <span class="tag">Marlin Firmware</span>
            <span class="tag">CNC Routing</span>
            <span class="tag">FDM Repair</span>
            <span class="tag">Electronics</span>
          </div>
        </a>

        <a class="project-card" href="#projects">
          <div class="project-header">
            <div class="project-icon">⚙️</div>
            <span class="project-badge planned">Planned</span>
          </div>
          <p class="project-org">Research Interest · Applied Math</p>
          <h3 class="project-title">Catastrophe-Derived Cam Profile</h3>
          <p class="project-desc">
            Exploring whether cusp catastrophe geometry from singularity theory can be used to design gearbox detent mechanisms with tunable bistability. Based on research group work on the Zeeman Machine.
          </p>
          <div class="project-tags">
            <span class="tag">Catastrophe Theory</span>
            <span class="tag">Mechanism Design</span>
            <span class="tag">MATLAB</span>
            <span class="tag">SolidWorks</span>
          </div>
        </a>

      </div>
    </div>
  </section>

  <hr class="divider" />

  <!-- BLOG -->
  <section id="blog">
    <div class="container">
      <p class="section-label">// project logs</p>
      <h2>Build Log</h2>
      <p class="section-sub">Notes from the bench — design decisions, lessons learned, things I'd do differently.</p>

      <div class="blog-grid">
        <a class="blog-card" href="#blog">
          <p class="blog-date">Jun 2025</p>
          <h3 class="blog-title">Getting wake word detection to work on the ESP32-S3</h3>
          <p class="blog-excerpt">ESP-SR's model format is picky about flash layout. Here's how I got the INMP441 and the WakeNet model playing nicely together without stomping on each other's memory.</p>
          <span class="blog-tag">embedded</span>
        </a>
        <a class="blog-card" href="#blog">
          <p class="blog-date">Apr 2025</p>
          <h3 class="blog-title">Structural constraints on a 1U CubeSat: what the standard actually demands</h3>
          <p class="blog-excerpt">Working through CubeSat Design Specification Rev 14 for LASAGNA-E. A practical breakdown of the deployment rail tolerance, shock load, and material requirements that actually matter.</p>
          <span class="blog-tag">structures</span>
        </a>
        <a class="blog-card" href="#blog">
          <p class="blog-date">Feb 2025</p>
          <h3 class="blog-title">Zeeman Machine and the geometry of sudden change</h3>
          <p class="blog-excerpt">A writeup from my singularity theory research group presentation. Why the Zeeman Machine is an elegant physical demonstration of cusp catastrophe, and where it breaks down as a model.</p>
          <span class="blog-tag">research</span>
        </a>
        <a class="blog-card" href="#blog">
          <p class="blog-date">Dec 2024</p>
          <h3 class="blog-title">Four-stroke engine simulation in MATLAB: lessons from EAS 230</h3>
          <p class="blog-excerpt">Building the full engine cycle model for my final project. P-V diagrams, iterative convergence, and the debugging session that taught me more about MATLAB than any lecture.</p>
          <span class="blog-tag">simulation</span>
        </a>
      </div>
    </div>
  </section>

  <hr class="divider" />

  <!-- RESUME -->
  <section id="resume">
    <div class="container">
      <p class="section-label">// background</p>
      <h2>Resume</h2>
      <p class="section-sub">University at Buffalo · B.S. Mechanical Engineering, Manufacturing Minor · Expected May 2029</p>

      <div class="resume-layout">
        <div class="resume-col">
          <h3>Experience</h3>

          <div class="resume-item">
            <div class="resume-item-header">
              <span class="resume-item-title">Structures Lead</span>
              <span class="resume-item-date">2024 – Present</span>
            </div>
            <p class="resume-item-org">LASAGNA-E CubeSat · NASA-funded</p>
            <p class="resume-item-desc">Leading mechanical design and structural analysis for a 1U CubeSat payload. Responsible for DFM, tolerance analysis, and launch survivability.</p>
          </div>

          <div class="resume-item">
            <div class="resume-item-header">
              <span class="resume-item-title">Manufacturing & Co-Lead</span>
              <span class="resume-item-date">2024 – Present</span>
            </div>
            <p class="resume-item-org">The Axolotl Rover · ASME IAM3D</p>
            <p class="resume-item-desc">Directing fabrication strategy and manufacturing decisions for a competition rover. Overseeing FDM/SLA printing, hardware assembly, and part tolerancing.</p>
          </div>

          <div class="resume-item">
            <div class="resume-item-header">
              <span class="resume-item-title">Consulting Extern</span>
              <span class="resume-item-date">2024</span>
            </div>
            <p class="resume-item-org">Bohler Consulting</p>
            <p class="resume-item-desc">Shadowed senior consultants across client engagement cycles. Developed analytical frameworks for technical problem structuring.</p>
          </div>

          <div class="resume-item">
            <div class="resume-item-header">
              <span class="resume-item-title">Tournament Operations</span>
              <span class="resume-item-date">2023 – 2024</span>
            </div>
            <p class="resume-item-org">Metropolitan Golf Association</p>
            <p class="resume-item-desc">Supported tournament logistics, scoring, and course setup for MGA-sanctioned amateur events across the tri-state area.</p>
          </div>

          <h3 style="margin-top: 2rem;">Leadership</h3>

          <div class="resume-item">
            <div class="resume-item-header">
              <span class="resume-item-title">President</span>
              <span class="resume-item-date">2024 – Present</span>
            </div>
            <p class="resume-item-org">Goodyear Resident Hall Association · UB</p>
            <p class="resume-item-desc">Leading hall governance, managing a representative council, and advocating for residential student concerns to university administration.</p>
          </div>
        </div>

        <div class="resume-col">
          <h3>Education</h3>
          <div class="resume-item">
            <div class="resume-item-header">
              <span class="resume-item-title">University at Buffalo</span>
              <span class="resume-item-date">2023 – 2029</span>
            </div>
            <p class="resume-item-org">B.S. Mechanical Engineering · Manufacturing Minor</p>
            <p class="resume-item-desc">Relevant coursework: Multivariable Calculus, Engineering Computations (MATLAB), Physics (SHM, Rotational Mechanics, Momentum). Pre-Law track.</p>
          </div>

          <h3 style="margin-top: 2rem;">Technical Skills</h3>
          <div class="skills-list">
            <div>
              <p class="skill-group-label">CAD / Simulation</p>
              <div class="skill-chips-sm">
                <span class="chip-sm">SolidWorks</span>
                <span class="chip-sm">Fusion 360</span>
                <span class="chip-sm">AutoCAD</span>
                <span class="chip-sm">MATLAB</span>
              </div>
            </div>
            <div>
              <p class="skill-group-label">Embedded & Programming</p>
              <div class="skill-chips-sm">
                <span class="chip-sm">Arduino</span>
                <span class="chip-sm">Raspberry Pi</span>
                <span class="chip-sm">ESP32 / ESP-IDF</span>
                <span class="chip-sm">Python</span>
                <span class="chip-sm">C/C++</span>
                <span class="chip-sm">Marlin</span>
              </div>
            </div>
            <div>
              <p class="skill-group-label">Fabrication</p>
              <div class="skill-chips-sm">
                <span class="chip-sm">FDM / SLA Printing</span>
                <span class="chip-sm">CNC Routing</span>
                <span class="chip-sm">Soldering</span>
                <span class="chip-sm">DFM</span>
              </div>
            </div>
          </div>

          <div class="resume-download-row">
            <a href="#resume" class="btn-primary">Download PDF resume →</a>
            <a href="https://linkedin.com" target="_blank" class="btn-outline">LinkedIn ↗</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <hr class="divider" />

  <!-- CONTACT -->
  <section id="contact">
    <div class="container">
      <p class="section-label">// let's talk</p>
      <h2>Contact</h2>

      <div class="contact-layout">
        <div>
          <p class="contact-desc">
            I'm open to undergraduate research positions, engineering internships, and conversations at the intersection of mechanical engineering and intellectual property law.
          </p>
          <p class="contact-desc" style="margin-top: -1rem;">
            Drop me a line and I'll get back to you within a day or two.
          </p>
          <div class="contact-links">
            <a class="contact-link" href="mailto:loch@buffalo.edu">
              <div class="contact-link-icon">✉</div>
              loch@buffalo.edu
            </a>
            <a class="contact-link" href="https://linkedin.com" target="_blank">
              <div class="contact-link-icon">in</div>
              linkedin.com/in/bobtham
            </a>
            <a class="contact-link" href="https://github.com" target="_blank">
              <div class="contact-link-icon">⌥</div>
              github.com/bobtham
            </a>
            <a class="contact-link" href="#">
              <div class="contact-link-icon">📄</div>
              Download resume (PDF)
            </a>
          </div>
        </div>

        <div class="contact-form">
          <div class="form-row">
            <label>Name</label>
            <input type="text" placeholder="Your name" id="cf-name" />
          </div>
          <div class="form-row">
            <label>Email</label>
            <input type="email" placeholder="your@email.com" id="cf-email" />
          </div>
          <div class="form-row">
            <label>Subject</label>
            <select id="cf-subject">
              <option value="">Select a topic...</option>
              <option>Undergraduate research opportunity</option>
              <option>Internship / job inquiry</option>
              <option>Collaboration on a project</option>
              <option>Patent law / IP discussion</option>
              <option>Something else</option>
            </select>
          </div>
          <div class="form-row">
            <label>Message</label>
            <textarea rows="5" placeholder="What's on your mind?" id="cf-message"></textarea>
          </div>
          <button class="form-submit" onclick="handleSubmit()">Send message →</button>
          <div class="form-success" id="form-success">
            ✓ Message sent! I'll be in touch soon.
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-inner">
      <span class="footer-copy">© 2025 Lochitha Thambeliyagoda · Built from scratch</span>
      <div class="footer-links">
        <a href="#hero">Home</a>
        <a href="#projects">Projects</a>
        <a href="#resume">Resume</a>
        <a href="mailto:loch@buffalo.edu">Email</a>
      </div>
    </div>
  </footer>

  <script>
    function handleSubmit() {
      const name = document.getElementById('cf-name').value.trim();
      const email = document.getElementById('cf-email').value.trim();
      const message = document.getElementById('cf-message').value.trim();
      if (!name || !email || !message) {
        alert('Please fill in your name, email, and message.');
        return;
      }
      document.getElementById('form-success').style.display = 'block';
      document.getElementById('cf-name').value = '';
      document.getElementById('cf-email').value = '';
      document.getElementById('cf-subject').value = '';
      document.getElementById('cf-message').value = '';
    }

    // Smooth active nav highlighting
    const sections = document.querySelectorAll('section[id]');
    const navLinks = document.querySelectorAll('.nav-links a');
    window.addEventListener('scroll', () => {
      let current = '';
      sections.forEach(s => {
        if (window.scrollY >= s.offsetTop - 80) current = s.id;
      });
      navLinks.forEach(a => {
        a.style.color = a.getAttribute('href') === `#${current}` ? 'var(--accent)' : '';
      });
    });
  </script>
</body>
</html>
