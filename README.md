<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Alex Mora — Designer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #F9F7F4;
    --ink: #111111;
    --muted: #6B7280;
    --accent: #E8613A;
    --rule: #E0DDD8;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--ink);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 3rem;
    background: var(--bg);
    border-bottom: 1px solid transparent;
    transition: border-color 0.3s;
  }
  nav.scrolled { border-color: var(--rule); }
  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.1rem;
    font-weight: 400;
    letter-spacing: 0.02em;
    color: var(--ink);
    text-decoration: none;
  }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    font-size: 0.8rem;
    font-weight: 400;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--ink); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 3rem;
    padding-top: 6rem;
    align-items: center;
    gap: 2rem;
  }

  .hero-text { padding-right: 4rem; }

  .eyebrow {
    font-size: 0.75rem;
    font-weight: 500;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1.5rem;
  }

  h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3.5rem, 7vw, 6.5rem);
    font-weight: 300;
    line-height: 0.95;
    letter-spacing: -0.01em;
    margin-bottom: 2rem;
  }

  h1 em {
    font-style: italic;
    color: var(--muted);
  }

  .hero-desc {
    font-size: 1rem;
    color: var(--muted);
    max-width: 38ch;
    line-height: 1.75;
    margin-bottom: 2.5rem;
  }

  .hero-cta {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.06em;
    color: var(--ink);
    text-decoration: none;
    border-bottom: 1.5px solid var(--accent);
    padding-bottom: 0.2rem;
    transition: gap 0.2s;
  }
  .hero-cta:hover { gap: 1.25rem; }
  .hero-cta svg { width: 14px; height: 14px; }

  /* ROTATING BADGE */
  .hero-badge-wrap {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  .badge-ring {
    position: relative;
    width: clamp(260px, 30vw, 360px);
    height: clamp(260px, 30vw, 360px);
  }

  .badge-ring svg.rotating {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    animation: spin 18s linear infinite;
  }

  @keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  @media (prefers-reduced-motion: reduce) {
    .badge-ring svg.rotating { animation: none; }
  }

  .badge-center {
    position: absolute;
    inset: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
  }

  .badge-center-symbol {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3.5rem;
    font-weight: 300;
    line-height: 1;
    color: var(--ink);
  }

  .badge-center-label {
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    margin-top: 0.5rem;
  }

  /* STATS ROW */
  .stats {
    display: flex;
    gap: 0;
    border-top: 1px solid var(--rule);
    border-bottom: 1px solid var(--rule);
    margin: 0 3rem;
  }
  .stat {
    flex: 1;
    padding: 2rem 0;
    border-right: 1px solid var(--rule);
    padding-left: 2.5rem;
  }
  .stat:last-child { border-right: none; }
  .stat-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2.8rem;
    font-weight: 300;
    line-height: 1;
    color: var(--ink);
    display: block;
  }
  .stat-label {
    font-size: 0.75rem;
    font-weight: 400;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--muted);
    margin-top: 0.4rem;
    display: block;
  }

  /* WORK */
  .work { padding: 6rem 3rem; }

  .section-header {
    display: flex;
    align-items: baseline;
    gap: 1.5rem;
    margin-bottom: 3.5rem;
  }

  h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 300;
    line-height: 1.1;
  }

  .section-tag {
    font-size: 0.75rem;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* WORK GRID */
  .work-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }

  .work-card {
    position: relative;
    overflow: hidden;
    background: var(--rule);
    cursor: pointer;
  }

  .work-card:first-child {
    grid-row: span 2;
  }

  .card-img {
    width: 100%;
    aspect-ratio: 4/3;
    object-fit: cover;
    display: block;
    transition: transform 0.5s ease;
  }

  .work-card:first-child .card-img {
    aspect-ratio: unset;
    height: 100%;
    min-height: 480px;
  }

  .work-card:hover .card-img {
    transform: scale(1.03);
  }

  .card-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to top, rgba(17,17,17,0.75) 0%, transparent 55%);
    opacity: 0;
    transition: opacity 0.3s;
    display: flex;
    align-items: flex-end;
    padding: 1.75rem;
  }

  .work-card:hover .card-overlay { opacity: 1; }

  .card-info { color: #fff; }
  .card-cat {
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    opacity: 0.75;
    margin-bottom: 0.3rem;
  }
  .card-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.5rem;
    font-weight: 400;
  }

  /* Placeholder colored backgrounds for cards */
  .card-bg-1 { background: #C8BFBA; }
  .card-bg-2 { background: #B5C4BF; }
  .card-bg-3 { background: #C4BAC8; }
  .card-bg-4 { background: #C4C2B5; }

  .card-placeholder {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Cormorant Garamond', serif;
    font-size: 4rem;
    font-weight: 300;
    color: rgba(255,255,255,0.4);
    transition: transform 0.5s ease;
  }
  .card-placeholder.tall { min-height: 480px; }
  .card-placeholder.short { aspect-ratio: 4/3; }

  .work-card:hover .card-placeholder { transform: scale(1.03); }

  /* ABOUT */
  .about {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
    border-top: 1px solid var(--rule);
    margin: 0 3rem;
    padding: 5rem 0;
  }

  .about-left { padding-right: 4rem; }

  .about-left h2 { margin-bottom: 1.5rem; }

  .about-text {
    color: var(--muted);
    line-height: 1.8;
    margin-bottom: 1.5rem;
    font-size: 0.95rem;
  }

  .about-right {
    padding-left: 4rem;
    border-left: 1px solid var(--rule);
  }

  .skills-group { margin-bottom: 2rem; }
  .skills-group-label {
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.75rem;
  }
  .skills-list {
    list-style: none;
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }
  .skills-list li {
    font-size: 0.82rem;
    color: var(--ink);
    border: 1px solid var(--rule);
    padding: 0.3rem 0.75rem;
  }

  /* CONTACT */
  .contact {
    background: var(--ink);
    color: var(--bg);
    padding: 5rem 3rem;
    text-align: center;
  }

  .contact h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2.5rem, 6vw, 5rem);
    font-weight: 300;
    margin-bottom: 1rem;
    color: var(--bg);
  }
  .contact h2 em { color: var(--accent); font-style: italic; }

  .contact-sub {
    color: #888;
    font-size: 0.9rem;
    margin-bottom: 2.5rem;
  }

  .contact-email {
    display: inline-block;
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(1.2rem, 3vw, 2rem);
    font-weight: 300;
    color: var(--bg);
    text-decoration: none;
    border-bottom: 1px solid var(--accent);
    padding-bottom: 0.2rem;
    transition: color 0.2s;
  }
  .contact-email:hover { color: var(--accent); }

  .contact-socials {
    margin-top: 3rem;
    display: flex;
    justify-content: center;
    gap: 2rem;
    list-style: none;
  }
  .contact-socials a {
    font-size: 0.75rem;
    font-weight: 400;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: #666;
    text-decoration: none;
    transition: color 0.2s;
  }
  .contact-socials a:hover { color: var(--bg); }

  /* FOOTER */
  footer {
    padding: 1.5rem 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: var(--ink);
    border-top: 1px solid #222;
  }
  footer span {
    font-size: 0.72rem;
    color: #444;
    letter-spacing: 0.06em;
  }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    nav { padding: 1.2rem 1.5rem; }
    .nav-links { gap: 1.5rem; }

    .hero {
      grid-template-columns: 1fr;
      padding: 6rem 1.5rem 3rem;
      text-align: center;
    }
    .hero-text { padding-right: 0; }
    .hero-desc { margin: 0 auto 2rem; }
    .hero-cta { margin: 0 auto; }
    .hero-badge-wrap { display: none; }

    .stats { margin: 0 1.5rem; flex-wrap: wrap; }
    .stat { border-right: none; border-bottom: 1px solid var(--rule); padding: 1.5rem 1.5rem; min-width: 50%; }

    .work { padding: 4rem 1.5rem; }
    .work-grid { grid-template-columns: 1fr; }
    .work-card:first-child { grid-row: span 1; }
    .card-placeholder.tall { min-height: 260px; }
    .card-overlay { opacity: 1; }

    .about { grid-template-columns: 1fr; margin: 0 1.5rem; }
    .about-left { padding-right: 0; margin-bottom: 2.5rem; }
    .about-right { border-left: none; border-top: 1px solid var(--rule); padding: 2rem 0 0; }

    .contact { padding: 4rem 1.5rem; }
    footer { padding: 1.2rem 1.5rem; flex-direction: column; gap: 0.5rem; text-align: center; }
  }
</style>
</head>
<body>

<nav id="nav">
  <a href="#" class="nav-logo">Alex Mora</a>
  <ul class="nav-links">
    <li><a href="#work">Work</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-text">
    <p class="eyebrow">Visual &amp; Brand Designer</p>
    <h1>Making things<br><em>look</em> like<br>they feel</h1>
    <p class="hero-desc">I help brands, startups, and studios turn ideas into visual identities, digital products, and experiences worth remembering.</p>
    <a href="#work" class="hero-cta">
      View selected work
      <svg viewBox="0 0 14 14" fill="none" stroke="currentColor" stroke-width="1.5">
        <path d="M2 7h10M8 3l4 4-4 4"/>
      </svg>
    </a>
  </div>

  <div class="hero-badge-wrap">
    <div class="badge-ring">
      <!-- Rotating text badge -->
      <svg class="rotating" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <path id="circle-path" d="M 100,100 m -75,0 a 75,75 0 1,1 150,0 a 75,75 0 1,1 -150,0"/>
        </defs>
        <text font-family="DM Sans, sans-serif" font-size="11.5" font-weight="500" letter-spacing="7" fill="#6B7280" text-transform="uppercase">
          <textPath href="#circle-path" startOffset="0%">
            AVAILABLE FOR WORK · OPEN TO PROJECTS · AVAILABLE FOR WORK · OPEN TO PROJECTS ·
          </textPath>
        </text>
        <circle cx="100" cy="25" r="2.5" fill="#E8613A"/>
      </svg>
      <!-- Center content -->
      <div class="badge-center">
        <span class="badge-center-symbol">AM</span>
        <span class="badge-center-label">Since 2018</span>
      </div>
    </div>
  </div>
</section>

<!-- STATS -->
<div class="stats">
  <div class="stat">
    <span class="stat-number">47</span>
    <span class="stat-label">Projects completed</span>
  </div>
  <div class="stat">
    <span class="stat-number">6+</span>
    <span class="stat-label">Years of practice</span>
  </div>
  <div class="stat">
    <span class="stat-number">23</span>
    <span class="stat-label">Happy clients</span>
  </div>
  <div class="stat">
    <span class="stat-number">3</span>
    <span class="stat-label">Design awards</span>
  </div>
</div>

<!-- WORK -->
<section class="work" id="work">
  <div class="section-header">
    <h2>Selected Work</h2>
    <span class="section-tag">2022 – 2025</span>
  </div>

  <div class="work-grid">
    <!-- Card 1: tall -->
    <div class="work-card card-bg-1">
      <div class="card-placeholder tall">◈</div>
      <div class="card-overlay">
        <div class="card-info">
          <p class="card-cat">Brand Identity</p>
          <p class="card-title">Solenne Café — Full identity system</p>
        </div>
      </div>
    </div>

    <!-- Card 2 -->
    <div class="work-card card-bg-2">
      <div class="card-placeholder short">◇</div>
      <div class="card-overlay">
        <div class="card-info">
          <p class="card-cat">Digital Product</p>
          <p class="card-title">Fern Studio — App design</p>
        </div>
      </div>
    </div>

    <!-- Card 3 -->
    <div class="work-card card-bg-3">
      <div class="card-placeholder short">△</div>
      <div class="card-overlay">
        <div class="card-info">
          <p class="card-cat">Editorial</p>
          <p class="card-title">Meridian Magazine — Art direction</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-left">
    <p class="eyebrow">About</p>
    <h2>Design that<br><em>earns</em> its place</h2>
    <p class="about-text">I'm Alex — a designer working at the intersection of brand, type, and digital product. I believe every visual decision should earn its place: nothing decorative for its own sake, everything in service of the work.</p>
    <p class="about-text">Previously at Studio Roto and Collective Goods. Now independent, taking on the kind of projects where the brief says "we don't want it to look like everything else."</p>
    <a href="#contact" class="hero-cta" style="margin-top:0.5rem">
      Let's talk
      <svg viewBox="0 0 14 14" fill="none" stroke="currentColor" stroke-width="1.5">
        <path d="M2 7h10M8 3l4 4-4 4"/>
      </svg>
    </a>
  </div>

  <div class="about-right">
    <div class="skills-group">
      <p class="skills-group-label">Craft</p>
      <ul class="skills-list">
        <li>Brand identity</li>
        <li>Visual systems</li>
        <li>Typography</li>
        <li>Art direction</li>
        <li>Editorial design</li>
        <li>Packaging</li>
      </ul>
    </div>
    <div class="skills-group">
      <p class="skills-group-label">Digital</p>
      <ul class="skills-list">
        <li>UI / UX design</li>
        <li>Figma</li>
        <li>Prototyping</li>
        <li>Design systems</li>
        <li>Motion</li>
      </ul>
    </div>
    <div class="skills-group">
      <p class="skills-group-label">Process</p>
      <ul class="skills-list">
        <li>Strategy workshops</li>
        <li>Research</li>
        <li>Print production</li>
        <li>Client presentation</li>
      </ul>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <h2>Let's make<br>something <em>real</em></h2>
  <p class="contact-sub">Open to brand, product, and editorial projects.</p>
  <a class="contact-email" href="mailto:alex@alexmora.co">alex@alexmora.co</a>
  <ul class="contact-socials">
    <li><a href="#">Instagram</a></li>
    <li><a href="#">Behance</a></li>
    <li><a href="#">LinkedIn</a></li>
    <li><a href="#">Are.na</a></li>
  </ul>
</section>

<footer>
  <span>© 2025 Alex Mora</span>
  <span>Designed independently · Built with intention</span>
</footer>

<script>
  // Nav scroll state
  const nav = document.getElementById('nav');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('scrolled', window.scrollY > 40);
  });
</script>

</body>
</html>
# My-repo-