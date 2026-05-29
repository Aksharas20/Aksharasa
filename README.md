<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Akshara S A – Full Stack Developer / UI-UX Designer</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #0B0F0E;
    --bg2: #131918;
    --bg3: #1A2220;
    --green: #1D9E75;
    --green-light: #5DCAA5;
    --green-dim: #085041;
    --green-pale: #E1F5EE;
    --text: #E8F0EE;
    --text2: #8FADA6;
    --text3: #4A6560;
    --border: rgba(29,158,117,0.18);
    --border2: rgba(93,202,165,0.12);
    --accent: #5DCAA5;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 16px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.1rem 2.5rem;
    background: rgba(11,15,14,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 0.5px solid var(--border);
  }
  .nav-logo {
    font-family: 'DM Serif Display', serif;
    font-size: 1.25rem;
    color: var(--accent);
    letter-spacing: -0.5px;
  }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    text-decoration: none;
    color: var(--text2);
    font-size: 0.875rem;
    font-weight: 500;
    letter-spacing: 0.03em;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--accent); }

  .hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 6rem 2.5rem 4rem;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; top: -40%; right: -15%;
    width: 700px; height: 700px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(29,158,117,0.08) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero::after {
    content: '';
    position: absolute; bottom: 0; left: 0; right: 0; height: 1px;
    background: linear-gradient(90deg, transparent, var(--green), transparent);
  }
  .hero-inner { max-width: 900px; }
  .hero-tag {
    display: inline-block;
    background: rgba(29,158,117,0.12);
    border: 0.5px solid var(--border);
    color: var(--accent);
    font-size: 0.75rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 0.35rem 1rem;
    border-radius: 100px;
    margin-bottom: 1.5rem;
    animation: fadeUp 0.5s ease both;
  }
  .hero h1 {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(3rem, 7vw, 5.5rem);
    line-height: 1.05;
    letter-spacing: -2px;
    color: var(--text);
    margin-bottom: 0.25rem;
    animation: fadeUp 0.6s 0.1s ease both;
  }
  .hero h1 em { font-style: italic; color: var(--accent); }
  .hero-sub {
    font-size: 1.1rem;
    color: var(--text2);
    max-width: 520px;
    margin: 1.25rem 0 2.5rem;
    line-height: 1.6;
    animation: fadeUp 0.6s 0.2s ease both;
  }
  .hero-cta {
    display: flex; gap: 1rem; flex-wrap: wrap;
    animation: fadeUp 0.6s 0.3s ease both;
  }
  .btn {
    display: inline-flex; align-items: center; gap: 0.5rem;
    padding: 0.7rem 1.5rem;
    border-radius: 8px;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    font-weight: 500;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
  }
  .btn-primary { background: var(--green); color: #fff; border: none; }
  .btn-primary:hover { background: var(--green-light); color: var(--bg); }
  .btn-ghost { background: transparent; color: var(--accent); border: 0.5px solid var(--border); }
  .btn-ghost:hover { background: rgba(29,158,117,0.08); border-color: var(--accent); }

  .hero-stats {
    display: flex; gap: 2.5rem; margin-top: 3.5rem;
    padding-top: 2rem;
    border-top: 0.5px solid var(--border);
    animation: fadeUp 0.6s 0.4s ease both;
  }
  .stat-val {
    font-family: 'DM Serif Display', serif;
    font-size: 1.8rem;
    color: var(--accent);
    line-height: 1;
  }
  .stat-lbl {
    font-size: 0.78rem;
    color: var(--text3);
    font-weight: 500;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    margin-top: 0.25rem;
  }

  section { padding: 5rem 2.5rem; }
  .section-header {
    display: flex; align-items: center; gap: 1rem;
    margin-bottom: 3rem;
  }
  .section-num {
    font-family: 'DM Serif Display', serif;
    font-size: 0.85rem;
    color: var(--text3);
    font-style: italic;
    min-width: 2rem;
  }
  .section-title {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(1.8rem, 3.5vw, 2.6rem);
    letter-spacing: -1px;
    line-height: 1;
  }
  .section-line {
    flex: 1; height: 0.5px;
    background: linear-gradient(90deg, var(--green-dim), transparent);
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1px;
    background: var(--border);
    border: 0.5px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }
  .skill-cell { background: var(--bg2); padding: 1.5rem; transition: background 0.2s; }
  .skill-cell:hover { background: var(--bg3); }
  .skill-cell-label {
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--text3);
    margin-bottom: 0.75rem;
  }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
  .tag {
    background: rgba(29,158,117,0.1);
    color: var(--accent);
    border: 0.5px solid rgba(93,202,165,0.2);
    padding: 0.25rem 0.65rem;
    border-radius: 100px;
    font-size: 0.78rem;
    font-weight: 500;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1.25rem;
  }
  .project-card {
    background: var(--bg2);
    border: 0.5px solid var(--border);
    border-radius: 12px;
    padding: 1.75rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s, transform 0.2s;
    cursor: default;
  }
  .project-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--green-dim), var(--green-light), var(--green-dim));
    opacity: 0;
    transition: opacity 0.2s;
  }
  .project-card:hover { border-color: var(--green); transform: translateY(-3px); }
  .project-card:hover::before { opacity: 1; }
  .project-icon {
    width: 40px; height: 40px;
    border-radius: 10px;
    background: rgba(29,158,117,0.15);
    display: flex; align-items: center; justify-content: center;
    margin-bottom: 1rem;
    font-size: 1.1rem;
  }
  .project-name {
    font-family: 'DM Serif Display', serif;
    font-size: 1.2rem;
    margin-bottom: 0.5rem;
    letter-spacing: -0.3px;
  }
  .project-desc {
    font-size: 0.875rem;
    color: var(--text2);
    line-height: 1.6;
    margin-bottom: 1rem;
  }
  .project-stack { display: flex; flex-wrap: wrap; gap: 0.35rem; }
  .stack-badge {
    background: var(--bg3);
    border: 0.5px solid var(--border2);
    color: var(--text3);
    font-size: 0.72rem;
    padding: 0.2rem 0.55rem;
    border-radius: 4px;
    font-weight: 500;
  }

  .exp-block {
    display: grid; grid-template-columns: 140px 1fr;
    gap: 0 2rem;
    padding: 2rem 0;
    border-bottom: 0.5px solid var(--border);
  }
  .exp-block:first-child { padding-top: 0; }
  .exp-block:last-child { border-bottom: none; }
  .exp-date { font-size: 0.8rem; color: var(--text3); font-weight: 500; padding-top: 0.15rem; line-height: 1.4; }
  .exp-role {
    font-family: 'DM Serif Display', serif;
    font-size: 1.15rem;
    margin-bottom: 0.2rem;
    letter-spacing: -0.3px;
  }
  .exp-org { color: var(--accent); font-size: 0.875rem; font-weight: 500; margin-bottom: 0.75rem; }
  .exp-desc { font-size: 0.875rem; color: var(--text2); line-height: 1.6; }

  .achieve-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1rem;
  }
  .achieve-card {
    background: var(--bg2);
    border: 0.5px solid var(--border);
    border-radius: 10px;
    padding: 1.25rem 1.5rem;
    display: flex; gap: 1rem; align-items: flex-start;
  }
  .achieve-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent);
    margin-top: 0.55rem;
    flex-shrink: 0;
  }
  .achieve-text { font-size: 0.875rem; color: var(--text2); line-height: 1.6; }
  .achieve-text strong { color: var(--text); font-weight: 500; }

  .certs-flow { display: flex; flex-wrap: wrap; gap: 0.6rem; }
  .cert-pill {
    background: var(--bg2);
    border: 0.5px solid var(--border);
    color: var(--text2);
    font-size: 0.8rem;
    padding: 0.4rem 0.9rem;
    border-radius: 100px;
    transition: border-color 0.2s, color 0.2s;
  }
  .cert-pill:hover { border-color: var(--accent); color: var(--accent); }

  .contact-block {
    background: var(--bg2);
    border: 0.5px solid var(--border);
    border-radius: 16px;
    padding: 3rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    align-items: center;
  }
  .contact-headline {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(1.8rem, 3vw, 2.5rem);
    letter-spacing: -1px;
    line-height: 1.15;
    margin-bottom: 0.75rem;
  }
  .contact-headline em { color: var(--accent); font-style: italic; }
  .contact-text { font-size: 0.9rem; color: var(--text2); margin-bottom: 1.5rem; }
  .contact-details { display: flex; flex-direction: column; gap: 0.9rem; }
  .contact-item { display: flex; align-items: center; gap: 0.75rem; font-size: 0.875rem; }
  .contact-icon {
    width: 34px; height: 34px;
    border-radius: 8px;
    background: rgba(29,158,117,0.12);
    border: 0.5px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    font-size: 0.9rem;
    flex-shrink: 0;
  }
  .contact-link { color: var(--text2); text-decoration: none; transition: color 0.2s; }
  .contact-link:hover { color: var(--accent); }

  footer {
    padding: 1.5rem 2.5rem;
    border-top: 0.5px solid var(--border);
    display: flex; justify-content: space-between; align-items: center;
    font-size: 0.78rem; color: var(--text3);
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .reveal { opacity: 0; transform: translateY(24px); transition: opacity 0.5s ease, transform 0.5s ease; }
  .revealed { opacity: 1; transform: none; }

  @media (max-width: 640px) {
    nav { padding: 1rem 1.25rem; }
    .nav-links { display: none; }
    section { padding: 3.5rem 1.25rem; }
    .hero { padding: 5rem 1.25rem 3rem; }
    .contact-block { grid-template-columns: 1fr; padding: 1.75rem; }
    .exp-block { grid-template-columns: 1fr; gap: 0.25rem; }
    .hero-stats { gap: 1.5rem; }
  }
</style>
</head>
<body>

<nav>
  <span class="nav-logo">AKSHARA S A</span>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<section class="hero">
  <div class="hero-inner">
    <span class="hero-tag">Available for opportunities</span>
    <h1>Full Stack<br><em>Developer</em></h1>
    <p class="hero-sub">Building scalable web applications with Python, Django, and modern frontend tech. Passionate about clean code, usability, design and products that matter.</p>
    <div class="hero-cta">
      <a href="#projects" class="btn btn-primary">View Projects →</a>
      <a href="#contact" class="btn btn-ghost">Get in Touch</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-val">4+</div>
        <div class="stat-lbl">Projects Built</div>
      </div>
      <div>
        <div class="stat-val">10+</div>
        <div class="stat-lbl">Certifications</div>
      </div>
      <div>
        <div class="stat-val">2026</div>
        <div class="stat-lbl">B.Tech CSE</div>
      </div>
    </div>
  </div>
</section>

<section id="skills">
  <div class="section-header reveal">
    <span class="section-num">01.</span>
    <h2 class="section-title">Technical skills</h2>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid reveal">
    <div class="skill-cell">
      <div class="skill-cell-label">Languages</div>
      <div class="skill-tags">
        <span class="tag">Python</span>
        <span class="tag">JavaScript</span>
        <span class="tag">Java</span>
        <span class="tag">PHP</span>
        <span class="tag">C</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-cell-label">Frontend</div>
      <div class="skill-tags">
        <span class="tag">HTML</span>
        <span class="tag">CSS</span>
        <span class="tag">jQuery</span>
        <span class="tag">AJAX</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-cell-label">Backend</div>
      <div class="skill-tags">
        <span class="tag">Django</span>
        <span class="tag">REST APIs</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-cell-label">Databases</div>
      <div class="skill-tags">
        <span class="tag">MySQL</span>
        <span class="tag">SQLite</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-cell-label">Tools</div>
      <div class="skill-tags">
        <span class="tag">Git</span>
         <span class="tag">Figma</span>
          <span class="tag">Canva</span>
        <span class="tag">GitHub</span>
        <span class="tag">VS Code</span>
        <span class="tag">JSON</span>
        <span class="tag">Excel</span>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="section-header reveal">
    <span class="section-num">02.</span>
    <h2 class="section-title">Projects</h2>
    <div class="section-line"></div>
  </div>

  <div class="projects-grid">

    <!-- CivicLens -->
    <div class="project-card reveal">
      <div class="project-icon">🏙️</div>
      <div class="project-name">Civic Lens</div>

      <p class="project-desc">
        AI-powered civic issue reporting and management platform with role-based authentication,
        admin dashboards, complaint tracking, and real-time status updates.
      </p>

      <div class="project-stack">
        <span class="stack-badge">Python</span>
        <span class="stack-badge">Django</span>
        <span class="stack-badge">MySQL</span>
        <span class="stack-badge">AJAX</span>
      </div>
    </div>

    <!-- CharitySphere -->
    <div class="project-card reveal">
      <div class="project-icon">💚</div>
      <div class="project-name">CharitySphere</div>

      <p class="project-desc">
        Donation and resource management platform with verification workflows,
        dashboard analytics, and secure allocation tracking system.
      </p>

      <div class="project-stack">
        <span class="stack-badge">Django</span>
        <span class="stack-badge">SQLite</span>
        <span class="stack-badge">JavaScript</span>
        <span class="stack-badge">HTML/CSS</span>
      </div>
    </div>

    <!-- Spam Shield -->
    <div class="project-card reveal">
      <div class="project-icon">🛡️</div>
      <div class="project-name">Spam Shield</div>

      <p class="project-desc">
        PHP-based spam detection and management system for identifying spam calls
        and emails with user alerts, admin control, and reporting interface.
      </p>

      <div class="project-stack">
        <span class="stack-badge">PHP</span>
        <span class="stack-badge">MySQL</span>
        <span class="stack-badge">JavaScript</span>
        <span class="stack-badge">jQuery</span>
      </div>
    </div>

    <!-- Healthy Habit Tracker -->
    <div class="project-card reveal">
      <div class="project-icon">🌿</div>
      <div class="project-name">Healthy Habit Tracker</div>

      <p class="project-desc">
        Wellness and lifestyle tracking application for monitoring environmental
        and personal health habits with visual analytics dashboard.
      </p>

      <div class="project-stack">
        <span class="stack-badge">Python</span>
        <span class="stack-badge">Django</span>
        <span class="stack-badge">CSS</span>
        <span class="stack-badge">JavaScript</span>
      </div>
    </div>

    <!-- Task Management -->
    <div class="project-card reveal">
      <div class="project-icon">📋</div>
      <div class="project-name">Task Management System</div>

      <p class="project-desc">
        Full stack task management web application for organizing daily activities,
        tracking progress, setting priorities, and managing deadlines efficiently.
      </p>

      <div class="project-stack">
        <span class="stack-badge">Python</span>
        <span class="stack-badge">Django</span>
        <span class="stack-badge">SQLite</span>
        <span class="stack-badge">Bootstrap</span>
      </div>
    </div>

    <!-- FoodGo -->
    <div class="project-card reveal">
      <div class="project-icon">🍔</div>
      <div class="project-name">FoodGo – Figma UI Design</div>

      <p class="project-desc">
        Modern food delivery mobile app UI designed in Figma with clean user experience,
        interactive screens, and premium visual design.
      </p>

      <div class="project-stack">
        <span class="stack-badge">Figma</span>
        <span class="stack-badge">UI/UX</span>
        <span class="stack-badge">Mobile Design</span>
      </div>
    </div>

    <!-- GoTravel -->
    <div class="project-card reveal">
      <div class="project-icon">✈️</div>
      <div class="project-name">GoTravel – Figma UI Design</div>

      <p class="project-desc">
        Travel booking application UI created in Figma featuring modern layouts,
        destination cards, booking screens, and responsive design concepts.
      </p>

      <div class="project-stack">
        <span class="stack-badge">Figma</span>
        <span class="stack-badge">UI Design</span>
        <span class="stack-badge">Prototype</span>
      </div>
    </div>

    <!-- WhatsApp Clone -->
    <div class="project-card reveal">
      <div class="project-icon">💬</div>
      <div class="project-name">WhatsApp Clone – Figma UI</div>

      <p class="project-desc">
        WhatsApp-inspired chat application interface designed in Figma with
        modern messaging screens, dark mode concepts, and responsive layouts.
      </p>

      <div class="project-stack">
        <span class="stack-badge">Figma</span>
        <span class="stack-badge">UI/UX</span>
        <span class="stack-badge">Prototype</span>
      </div>
    </div>

  </div>
</section>

<section id="experience">
  <div class="section-header reveal">
    <span class="section-num">03.</span>
    <h2 class="section-title">Experience & education</h2>
    <div class="section-line"></div>
  </div>
  <div class="reveal">
    <div class="exp-block">
      <div class="exp-date">Oct 2025 –<br>Nov 2025</div>
      <div>
        <div class="exp-role">Software Tester Intern</div>
        <div class="exp-org">CodeCraft Infotech</div>
        <div class="exp-desc">Executed functional testing, designed test scenarios, reported defects, and validated fixes to improve overall product reliability and stability.</div>
      </div>
    </div>
    <div class="exp-block">
      <div class="exp-date">Completed</div>
      <div>
        <div class="exp-role">Python Full Stack Training</div>
        <div class="exp-org">IPCS Global</div>
        <div class="exp-desc">Hands-on training in Django-based web application development, backend integration, and responsive frontend design.</div>
      </div>
    </div>
    <div class="exp-block">
      <div class="exp-date">2022 – 2026</div>
      <div>
        <div class="exp-role">B.Tech – Computer Science & Engineering</div>
        <div class="exp-org">LEAD – Sarabhai Institute of Science and Technology, Trivandrum</div>
        <div class="exp-desc">Graduating 2026. Active class representative, NSS coordinator, and participant in technical events and collegiate competitions.</div>
      </div>
    </div>
  </div>
</section>

<section id="achievements">
  <div class="section-header reveal">
    <span class="section-num">04.</span>
    <h2 class="section-title">Achievements & leadership</h2>
    <div class="section-line"></div>
  </div>
  <div class="achieve-grid reveal">
    <div class="achieve-card">
      <div class="achieve-dot"></div>
      <div class="achieve-text"><strong>Hindi Sahithyaacharya First Class</strong> – Kerala Hindi Prachar Sabha, recognizing excellence in Hindi literature.</div>
    </div>
    <div class="achieve-card">
      <div class="achieve-dot"></div>
      <div class="achieve-text"><strong>Student Placement Coordinator</strong> and <strong>NSS Student Coordinator</strong> — led event coordination and community outreach.</div>
    </div>
    <div class="achieve-card">
      <div class="achieve-dot"></div>
      <div class="achieve-text"><strong>NSS Old Age Home Visit</strong> — coordinated volunteer social initiative alongside internship duties.</div>
    </div>
    <div class="achieve-card">
      <div class="achieve-dot"></div>
      <div class="achieve-text"><strong>Class Representative</strong> and active volunteer in technical events and coordination meets.</div>
    </div>
    <div class="achieve-card">
      <div class="achieve-dot"></div>
      <div class="achieve-text"><strong>First Place – Handball</strong> (college-level tournament), demonstrating teamwork and discipline.</div>
    </div>
  </div>
</section>

<section id="certifications">
  <div class="section-header reveal">
    <span class="section-num">05.</span>
    <h2 class="section-title">Certifications</h2>
    <div class="section-line"></div>
  </div>
  <div class="certs-flow reveal">
    <span class="cert-pill">Cyber Security Analyst – EC Council</span>
    <span class="cert-pill">AI for All – Intel</span>
    <span class="cert-pill">Cybersecurity Virtual Experience – Forage</span>
    <span class="cert-pill">Java Workshop – IPCS Global</span>
    <span class="cert-pill">Build Your Own Gen AI Model – NXTWave</span>
    <span class="cert-pill">Generative AI Workshop – CET Trivandrum</span>
    <span class="cert-pill">Arduino – RigLabs</span>
    <span class="cert-pill">Basics of Python – Open Weaver</span>
    <span class="cert-pill">Artificial Intelligence Seminar – LEAD SIST</span>
    <span class="cert-pill">Techmaghi – IIT Kharagpur</span>
    <span class="cert-pill">Interior in Virtual Reality</span>
  </div>
</section>

<section id="contact">
  <div class="section-header reveal">
    <span class="section-num">06.</span>
    <h2 class="section-title">Contact</h2>
    <div class="section-line"></div>
  </div>
  <div class="contact-block reveal">
    <div>
      <h3 class="contact-headline">Let's build something <em>great</em> together.</h3>
      <p class="contact-text">Open to full stack developer roles, product-based companies, and interesting opportunities. Feel free to reach out!</p>
      <a href="mailto:aksharasa2004@gmail.com" class="btn btn-primary">Send a message →</a>
    </div>
    <div class="contact-details">
      <div class="contact-item">
        <div class="contact-icon">✉</div>
        <a href="mailto:aksharasa2004@gmail.com" class="contact-link">aksharasa2004@gmail.com</a>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📞</div>
        <span class="contact-link">+91 8086903157</span>
      </div>
      <div class="contact-item">
        <div class="contact-icon">in</div>
        <a href="https://linkedin.com/in/akshara-s-a-a92531312" class="contact-link" target="_blank">linkedin.com/in/akshara-s-a</a>
      </div>
      <div class="contact-item">
        <div class="contact-icon">⌥</div>
        <a href="https://github.com/Aksharas20" class="contact-link" target="_blank">github.com/Aksharas20</a>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📍</div>
        <span class="contact-link">Trivandrum, India</span>
      </div>
    </div>
  </div>
</section>

<footer>
  <span>Akshara S A · Full Stack Developer · Trivandrum, India</span>
  <span>© 2026</span>
</footer>

<script>
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('revealed'); });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
