<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Inazawa Electronics — Premium Laptops & Apple Devices</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Space+Mono:wght@400;700&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #030508;
    --bg2: #080d14;
    --surface: #0d1520;
    --surface2: #111c2d;
    --border: rgba(0,200,255,0.12);
    --cyan: #00d4ff;
    --cyan-dim: rgba(0,212,255,0.15);
    --cyan-glow: rgba(0,212,255,0.4);
    --white: #eef4ff;
    --muted: #6a7f99;
    --accent: #ff6b35;
    --green: #00ff88;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--white);
    font-family: 'DM Sans', sans-serif;
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom cursor */
  .cursor {
    width: 12px; height: 12px;
    background: var(--cyan);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none;
    z-index: 9999;
    transition: transform 0.1s ease;
    mix-blend-mode: screen;
  }
  .cursor-ring {
    width: 36px; height: 36px;
    border: 1px solid var(--cyan);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none;
    z-index: 9998;
    transition: transform 0.18s ease, opacity 0.2s;
    opacity: 0.5;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.2rem 5vw;
    background: rgba(3,5,8,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }
  .logo {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1.4rem;
    letter-spacing: -0.02em;
    color: var(--white);
    text-decoration: none;
  }
  .logo span { color: var(--cyan); }
  .nav-links {
    display: flex; gap: 2.4rem; list-style: none;
  }
  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 500;
    letter-spacing: 0.04em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--cyan); }
  .nav-cta {
    background: var(--cyan);
    color: #000 !important;
    padding: 0.5rem 1.4rem;
    border-radius: 4px;
    font-weight: 700 !important;
    transition: box-shadow 0.2s, transform 0.2s !important;
  }
  .nav-cta:hover {
    box-shadow: 0 0 24px var(--cyan-glow);
    transform: translateY(-1px);
    color: #000 !important;
  }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 8rem 5vw 4rem;
    position: relative;
    overflow: hidden;
  }
  .hero-grid-bg {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(var(--border) 1px, transparent 1px),
      linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 40%, black 40%, transparent 100%);
  }
  .hero-glow {
    position: absolute;
    width: 700px; height: 700px;
    background: radial-gradient(circle, rgba(0,212,255,0.08) 0%, transparent 70%);
    top: -100px; right: -100px;
    pointer-events: none;
  }
  .hero-glow2 {
    position: absolute;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(255,107,53,0.06) 0%, transparent 70%);
    bottom: 0; left: 10%;
    pointer-events: none;
  }
  .hero-content { position: relative; z-index: 2; max-width: 720px; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 0.4rem 1rem;
    border-radius: 100px;
    font-size: 0.78rem;
    font-family: 'Space Mono', monospace;
    color: var(--cyan);
    margin-bottom: 1.8rem;
    letter-spacing: 0.05em;
  }
  .hero-badge::before {
    content: '';
    width: 7px; height: 7px;
    background: var(--green);
    border-radius: 50%;
    box-shadow: 0 0 8px var(--green);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }
  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(3rem, 7vw, 5.5rem);
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -0.03em;
    margin-bottom: 1.5rem;
  }
  .hero h1 .line2 { color: var(--cyan); display: block; }
  .hero p {
    font-size: 1.15rem;
    color: var(--muted);
    line-height: 1.7;
    max-width: 520px;
    margin-bottom: 2.5rem;
    font-weight: 300;
  }
  .hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; }
  .btn-primary {
    background: var(--cyan);
    color: #000;
    padding: 0.85rem 2.2rem;
    border-radius: 6px;
    font-weight: 700;
    font-size: 0.95rem;
    text-decoration: none;
    transition: box-shadow 0.25s, transform 0.2s;
    display: inline-block;
  }
  .btn-primary:hover {
    box-shadow: 0 0 30px var(--cyan-glow);
    transform: translateY(-2px);
  }
  .btn-ghost {
    border: 1px solid var(--border);
    color: var(--white);
    padding: 0.85rem 2.2rem;
    border-radius: 6px;
    font-weight: 500;
    font-size: 0.95rem;
    text-decoration: none;
    transition: border-color 0.2s, background 0.2s;
    display: inline-block;
  }
  .btn-ghost:hover {
    border-color: var(--cyan);
    background: var(--cyan-dim);
  }
  .hero-stats {
    display: flex; gap: 3rem; margin-top: 4rem;
    padding-top: 2rem;
    border-top: 1px solid var(--border);
  }
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    color: var(--cyan);
  }
  .stat-label {
    font-size: 0.8rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.06em;
    margin-top: 0.2rem;
  }

  /* MARQUEE */
  .marquee-wrap {
    overflow: hidden;
    background: var(--surface);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 0.9rem 0;
  }
  .marquee {
    display: flex; gap: 3rem;
    animation: marquee 18s linear infinite;
    white-space: nowrap;
  }
  .marquee-item {
    font-family: 'Space Mono', monospace;
    font-size: 0.78rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    flex-shrink: 0;
  }
  .marquee-item .dot { color: var(--cyan); margin: 0 1rem; }
  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  /* SECTION SHARED */
  section { padding: 6rem 5vw; }
  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 0.72rem;
    color: var(--cyan);
    text-transform: uppercase;
    letter-spacing: 0.14em;
    margin-bottom: 0.8rem;
    display: flex; align-items: center; gap: 0.6rem;
  }
  .section-label::before {
    content: '//';
    opacity: 0.5;
  }
  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 800;
    letter-spacing: -0.02em;
    margin-bottom: 1rem;
  }
  .section-sub {
    color: var(--muted);
    font-size: 1rem;
    max-width: 500px;
    line-height: 1.7;
    margin-bottom: 3rem;
    font-weight: 300;
  }

  /* BRANDS */
  #brands { background: var(--bg2); }
  .brands-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
    gap: 1px;
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    max-width: 900px;
  }
  .brand-card {
    background: var(--surface);
    padding: 2rem 1.5rem;
    display: flex; flex-direction: column; align-items: center; gap: 0.7rem;
    transition: background 0.2s;
    border-right: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
  .brand-card:hover { background: var(--surface2); }
  .brand-icon { font-size: 2rem; }
  .brand-name {
    font-family: 'Syne', sans-serif;
    font-size: 0.85rem;
    font-weight: 700;
    letter-spacing: 0.04em;
    color: var(--muted);
  }

  /* PRODUCTS */
  #products { background: var(--bg); }
  .products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5rem;
  }
  .product-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
    position: relative;
  }
  .product-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 20px 60px rgba(0,0,0,0.5), 0 0 0 1px rgba(0,212,255,0.2);
    border-color: rgba(0,212,255,0.3);
  }
  .product-tag {
    position: absolute; top: 1rem; left: 1rem;
    background: var(--cyan);
    color: #000;
    font-size: 0.68rem;
    font-family: 'Space Mono', monospace;
    font-weight: 700;
    padding: 0.25rem 0.6rem;
    border-radius: 4px;
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }
  .product-tag.used {
    background: var(--accent);
  }
  .product-img {
    height: 200px;
    background: var(--surface2);
    display: flex; align-items: center; justify-content: center;
    font-size: 5rem;
    border-bottom: 1px solid var(--border);
  }
  .product-body { padding: 1.4rem; }
  .product-brand {
    font-family: 'Space Mono', monospace;
    font-size: 0.68rem;
    color: var(--cyan);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-bottom: 0.4rem;
  }
  .product-name {
    font-family: 'Syne', sans-serif;
    font-size: 1.05rem;
    font-weight: 700;
    margin-bottom: 0.8rem;
    line-height: 1.3;
  }
  .product-specs {
    display: flex; flex-wrap: wrap; gap: 0.4rem;
    margin-bottom: 1.2rem;
  }
  .spec-pill {
    background: var(--bg);
    border: 1px solid var(--border);
    padding: 0.25rem 0.65rem;
    border-radius: 100px;
    font-size: 0.72rem;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
  }
  .product-footer {
    display: flex; align-items: center; justify-content: space-between;
  }
  .product-price {
    font-family: 'Syne', sans-serif;
    font-size: 1.4rem;
    font-weight: 800;
    color: var(--cyan);
  }
  .product-price span {
    font-size: 0.75rem;
    font-family: 'DM Sans', sans-serif;
    color: var(--muted);
    font-weight: 400;
  }
  .btn-card {
    background: var(--cyan-dim);
    color: var(--cyan);
    border: 1px solid rgba(0,212,255,0.3);
    padding: 0.5rem 1.1rem;
    border-radius: 6px;
    font-size: 0.82rem;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.2s, box-shadow 0.2s;
    text-decoration: none;
  }
  .btn-card:hover {
    background: var(--cyan);
    color: #000;
    box-shadow: 0 0 20px var(--cyan-glow);
  }

  /* WHY */
  #why { background: var(--bg2); }
  .why-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5rem;
  }
  .why-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 2rem;
    transition: border-color 0.25s, transform 0.25s;
    position: relative;
    overflow: hidden;
  }
  .why-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--cyan), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .why-card:hover::before { opacity: 1; }
  .why-card:hover { border-color: rgba(0,212,255,0.25); transform: translateY(-3px); }
  .why-icon {
    font-size: 2rem;
    margin-bottom: 1rem;
    display: block;
  }
  .why-title {
    font-family: 'Syne', sans-serif;
    font-size: 1.05rem;
    font-weight: 700;
    margin-bottom: 0.6rem;
  }
  .why-desc {
    font-size: 0.88rem;
    color: var(--muted);
    line-height: 1.65;
    font-weight: 300;
  }

  /* REVIEWS */
  #reviews { background: var(--bg); }
  .rating-hero {
    display: flex; align-items: center; gap: 2rem;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 2.5rem;
    margin-bottom: 2.5rem;
    max-width: 550px;
  }
  .rating-big {
    font-family: 'Syne', sans-serif;
    font-size: 5rem;
    font-weight: 800;
    color: var(--cyan);
    line-height: 1;
  }
  .stars { color: #ffd700; font-size: 1.4rem; letter-spacing: 0.1em; }
  .rating-count { color: var(--muted); font-size: 0.9rem; margin-top: 0.3rem; }
  .reviews-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1.2rem;
  }
  .review-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.6rem;
    transition: border-color 0.2s;
  }
  .review-card:hover { border-color: rgba(0,212,255,0.2); }
  .review-header {
    display: flex; justify-content: space-between; align-items: flex-start;
    margin-bottom: 0.8rem;
  }
  .reviewer-name {
    font-family: 'Syne', sans-serif;
    font-size: 0.95rem;
    font-weight: 700;
  }
  .review-stars { color: #ffd700; font-size: 0.85rem; }
  .review-text {
    font-size: 0.88rem;
    color: var(--muted);
    line-height: 1.65;
    font-weight: 300;
  }
  .review-date {
    font-family: 'Space Mono', monospace;
    font-size: 0.68rem;
    color: rgba(106,127,153,0.5);
    margin-top: 0.8rem;
  }

  /* CONTACT */
  #contact {
    background: var(--bg2);
    position: relative;
    overflow: hidden;
  }
  #contact::before {
    content: '';
    position: absolute;
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(0,212,255,0.06), transparent 70%);
    bottom: -100px; right: -50px;
    pointer-events: none;
  }
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
  }
  .contact-item {
    display: flex; align-items: center; gap: 1rem;
    margin-bottom: 1.5rem;
  }
  .contact-icon-wrap {
    width: 48px; height: 48px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.2rem;
    flex-shrink: 0;
  }
  .contact-label {
    font-family: 'Space Mono', monospace;
    font-size: 0.68rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-bottom: 0.2rem;
  }
  .contact-value {
    font-size: 0.95rem;
    font-weight: 500;
    color: var(--white);
  }
  .contact-value a {
    color: var(--cyan);
    text-decoration: none;
  }
  .map-placeholder {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    height: 280px;
    display: flex; align-items: center; justify-content: center;
    flex-direction: column; gap: 0.8rem;
    color: var(--muted);
    font-size: 0.88rem;
  }
  .map-placeholder .pin { font-size: 2.5rem; }

  /* FOOTER */
  footer {
    background: var(--bg);
    border-top: 1px solid var(--border);
    padding: 2.5rem 5vw;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 1rem;
  }
  .footer-copy {
    font-size: 0.82rem;
    color: var(--muted);
  }
  .footer-links { display: flex; gap: 1.8rem; }
  .footer-links a {
    font-size: 0.82rem;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .footer-links a:hover { color: var(--cyan); }

  /* ANIMATIONS */
  .fade-in {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .fade-in.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* MOBILE */
  @media (max-width: 768px) {
    .nav-links { display: none; }
    .hero-stats { gap: 2rem; flex-wrap: wrap; }
    .contact-grid { grid-template-columns: 1fr; gap: 2rem; }
    .brands-grid { grid-template-columns: repeat(3, 1fr); }
  }
</style>
</head>
<body>

<!-- Cursor -->
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav>
  <a href="#" class="logo">INAZAWA<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#brands">Brands</a></li>
    <li><a href="#products">Products</a></li>
    <li><a href="#why">Why Us</a></li>
    <li><a href="#reviews">Reviews</a></li>
    <li><a href="#contact" class="nav-cta">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <div class="hero-content">
    <div class="hero-badge">Open Now — Mawanella, Sri Lanka</div>
    <h1>
      Premium Laptops<br/>
      <span class="line2">Delivered Right.</span>
    </h1>
    <p>Sri Lanka's most trusted source for brand new and certified used laptops. Apple, Asus, Lenovo, HP, Dell, MSI — genuine warranty, zero compromise.</p>
    <div class="hero-actions">
      <a href="#products" class="btn-primary">Browse Laptops</a>
      <a href="#contact" class="btn-ghost">WhatsApp Us</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">4.9★</div>
        <div class="stat-label">Google Rating</div>
      </div>
      <div>
        <div class="stat-num">412+</div>
        <div class="stat-label">Reviews</div>
      </div>
      <div>
        <div class="stat-num">100%</div>
        <div class="stat-label">Trusted Store</div>
      </div>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee">
    <span class="marquee-item">Apple MacBook<span class="dot">◆</span></span>
    <span class="marquee-item">ASUS ROG<span class="dot">◆</span></span>
    <span class="marquee-item">Lenovo ThinkPad<span class="dot">◆</span></span>
    <span class="marquee-item">HP Spectre<span class="dot">◆</span></span>
    <span class="marquee-item">Dell XPS<span class="dot">◆</span></span>
    <span class="marquee-item">MSI Gaming<span class="dot">◆</span></span>
    <span class="marquee-item">Apple iPad<span class="dot">◆</span></span>
    <span class="marquee-item">iPhone<span class="dot">◆</span></span>
    <span class="marquee-item">Genuine Warranty<span class="dot">◆</span></span>
    <span class="marquee-item">Free Inspection<span class="dot">◆</span></span>
    <!-- repeat for seamless loop -->
    <span class="marquee-item">Apple MacBook<span class="dot">◆</span></span>
    <span class="marquee-item">ASUS ROG<span class="dot">◆</span></span>
    <span class="marquee-item">Lenovo ThinkPad<span class="dot">◆</span></span>
    <span class="marquee-item">HP Spectre<span class="dot">◆</span></span>
    <span class="marquee-item">Dell XPS<span class="dot">◆</span></span>
    <span class="marquee-item">MSI Gaming<span class="dot">◆</span></span>
    <span class="marquee-item">Apple iPad<span class="dot">◆</span></span>
    <span class="marquee-item">iPhone<span class="dot">◆</span></span>
    <span class="marquee-item">Genuine Warranty<span class="dot">◆</span></span>
    <span class="marquee-item">Free Inspection<span class="dot">◆</span></span>
  </div>
</div>

<!-- BRANDS -->
<section id="brands">
  <div class="fade-in">
    <div class="section-label">Brands</div>
    <div class="section-title">We Stock Only The Best</div>
    <p class="section-sub">Every brand selected for quality, performance, and reliability — new and certified used.</p>
  </div>
  <div class="brands-grid fade-in">
    <div class="brand-card"><span class="brand-icon">🍎</span><span class="brand-name">Apple</span></div>
    <div class="brand-card"><span class="brand-icon">⚡</span><span class="brand-name">ASUS</span></div>
    <div class="brand-card"><span class="brand-icon">🔷</span><span class="brand-name">Lenovo</span></div>
    <div class="brand-card"><span class="brand-icon">🖥️</span><span class="brand-name">HP</span></div>
    <div class="brand-card"><span class="brand-icon">💻</span><span class="brand-name">Dell</span></div>
    <div class="brand-card"><span class="brand-icon">🎮</span><span class="brand-name">MSI</span></div>
  </div>
</section>

<!-- PRODUCTS -->
<section id="products">
  <div class="fade-in">
    <div class="section-label">Inventory</div>
    <div class="section-title">Featured Products</div>
    <p class="section-sub">Handpicked machines — all tested, graded, and ready to ship.</p>
  </div>
  <div class="products-grid">

    <div class="product-card fade-in">
      <div class="product-tag used">Used</div>
      <div class="product-img">💻</div>
      <div class="product-body">
        <div class="product-brand">Apple</div>
        <div class="product-name">MacBook Air M2 — 2022</div>
        <div class="product-specs">
          <span class="spec-pill">M2 Chip</span>
          <span class="spec-pill">8GB RAM</span>
          <span class="spec-pill">256GB SSD</span>
          <span class="spec-pill">13.6"</span>
        </div>
        <div class="product-footer">
          <div class="product-price">On Request <span>/ LKR</span></div>
          <a href="#contact" class="btn-card">Enquire</a>
        </div>
      </div>
    </div>

    <div class="product-card fade-in">
      <div class="product-tag used">Used</div>
      <div class="product-img">📱</div>
      <div class="product-body">
        <div class="product-brand">Apple</div>
        <div class="product-name">iPad 10th Gen — 2022</div>
        <div class="product-specs">
          <span class="spec-pill">A14 Bionic</span>
          <span class="spec-pill">64GB</span>
          <span class="spec-pill">10.9" Retina</span>
        </div>
        <div class="product-footer">
          <div class="product-price">On Request <span>/ LKR</span></div>
          <a href="#contact" class="btn-card">Enquire</a>
        </div>
      </div>
    </div>

    <div class="product-card fade-in">
      <div class="product-tag">New</div>
      <div class="product-img">⚡</div>
      <div class="product-body">
        <div class="product-brand">ASUS</div>
        <div class="product-name">ASUS ROG / VivoBook Series</div>
        <div class="product-specs">
          <span class="spec-pill">Various Configs</span>
          <span class="spec-pill">Gaming / Pro</span>
          <span class="spec-pill">Warranty</span>
        </div>
        <div class="product-footer">
          <div class="product-price">On Request <span>/ LKR</span></div>
          <a href="#contact" class="btn-card">Enquire</a>
        </div>
      </div>
    </div>

    <div class="product-card fade-in">
      <div class="product-tag">New</div>
      <div class="product-img">🔷</div>
      <div class="product-body">
        <div class="product-brand">Lenovo</div>
        <div class="product-name">ThinkPad / IdeaPad Series</div>
        <div class="product-specs">
          <span class="spec-pill">Business / Home</span>
          <span class="spec-pill">Intel / AMD</span>
          <span class="spec-pill">Warranty</span>
        </div>
        <div class="product-footer">
          <div class="product-price">On Request <span>/ LKR</span></div>
          <a href="#contact" class="btn-card">Enquire</a>
        </div>
      </div>
    </div>

    <div class="product-card fade-in">
      <div class="product-tag">New</div>
      <div class="product-img">🖥️</div>
      <div class="product-body">
        <div class="product-brand">HP</div>
        <div class="product-name">HP Pavilion / Spectre Series</div>
        <div class="product-specs">
          <span class="spec-pill">Various Configs</span>
          <span class="spec-pill">Intel Core</span>
          <span class="spec-pill">Warranty</span>
        </div>
        <div class="product-footer">
          <div class="product-price">On Request <span>/ LKR</span></div>
          <a href="#contact" class="btn-card">Enquire</a>
        </div>
      </div>
    </div>

    <div class="product-card fade-in">
      <div class="product-tag">New</div>
      <div class="product-img">🎮</div>
      <div class="product-body">
        <div class="product-brand">MSI</div>
        <div class="product-name">MSI Gaming Series</div>
        <div class="product-specs">
          <span class="spec-pill">RTX GPU</span>
          <span class="spec-pill">High Refresh</span>
          <span class="spec-pill">Warranty</span>
        </div>
        <div class="product-footer">
          <div class="product-price">On Request <span>/ LKR</span></div>
          <a href="#contact" class="btn-card">Enquire</a>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- WHY -->
<section id="why">
  <div class="fade-in">
    <div class="section-label">Why Choose Us</div>
    <div class="section-title">Zero Compromise Quality</div>
    <p class="section-sub">Every device passes our rigorous inspection before it reaches you.</p>
  </div>
  <div class="why-grid">
    <div class="why-card fade-in">
      <span class="why-icon">🔍</span>
      <div class="why-title">Every Unit Inspected</div>
      <div class="why-desc">All used devices are fully tested — battery, display, keyboard, ports — before listing. What you see is exactly what you get.</div>
    </div>
    <div class="why-card fade-in">
      <span class="why-icon">🛡️</span>
      <div class="why-title">Genuine Warranty</div>
      <div class="why-desc">Brand new laptops come with official manufacturer warranty. Used devices include our own service guarantee.</div>
    </div>
    <div class="why-card fade-in">
      <span class="why-icon">⭐</span>
      <div class="why-title">4.9★ on Google</div>
      <div class="why-desc">Over 412 verified reviews. Our customers keep coming back — and they bring their friends too.</div>
    </div>
    <div class="why-card fade-in">
      <span class="why-icon">💬</span>
      <div class="why-title">WhatsApp Support</div>
      <div class="why-desc">Got a question? Message us directly on WhatsApp. Fast, friendly, real answers — not bots.</div>
    </div>
    <div class="why-card fade-in">
      <span class="why-icon">📦</span>
      <div class="why-title">Wide Selection</div>
      <div class="why-desc">Apple, ASUS, Lenovo, HP, Dell, MSI — new and used. Budget laptops to pro-grade MacBooks, all in one place.</div>
    </div>
    <div class="why-card fade-in">
      <span class="why-icon">📍</span>
      <div class="why-title">Visit In-Store</div>
      <div class="why-desc">Located on Samithiya Road, Mawanella. Come in, try before you buy, and leave with your new machine same day.</div>
    </div>
  </div>
</section>

<!-- REVIEWS -->
<section id="reviews">
  <div class="fade-in">
    <div class="section-label">Reviews</div>
    <div class="section-title">What Customers Say</div>
  </div>
  <div class="rating-hero fade-in">
    <div class="rating-big">4.9</div>
    <div>
      <div class="stars">★★★★★</div>
      <div class="rating-count">412 Google Reviews</div>
    </div>
  </div>
  <div class="reviews-grid">
    <div class="review-card fade-in">
      <div class="review-header">
        <div class="reviewer-name">Kiru Shan</div>
        <div class="review-stars">★★★★★</div>
      </div>
      <div class="review-text">100% trustable store. Not a single issue with the iPad. Highly recommend!</div>
      <div class="review-date">1 month ago</div>
    </div>
    <div class="review-card fade-in">
      <div class="review-header">
        <div class="reviewer-name">Aashif Musheer</div>
        <div class="review-stars">★★★★★</div>
      </div>
      <div class="review-text">Really happy with the laptop I got from Inazawa Electronics. The staff was extremely helpful and knowledgeable. Great experience overall.</div>
      <div class="review-date">3 months ago</div>
    </div>
    <div class="review-card fade-in">
      <div class="review-header">
        <div class="reviewer-name">Verified Buyer</div>
        <div class="review-stars">★★★★★</div>
      </div>
      <div class="review-text">Perfect place to buy used and brand new laptops. Genuine warranty and fair pricing. Will definitely return.</div>
      <div class="review-date">2 months ago</div>
    </div>
    <div class="review-card fade-in">
      <div class="review-header">
        <div class="reviewer-name">M. Fahim</div>
        <div class="review-stars">★★★★★</div>
      </div>
      <div class="review-text">Highly recommended for brand new laptops with genuine warranty. Very professional service from the team.</div>
      <div class="review-date">2 months ago</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="fade-in">
    <div class="section-label">Contact</div>
    <div class="section-title">Come Visit Us</div>
    <p class="section-sub">We're open 7 days. Busy hours are between 3 PM – 9 PM. Most customers spend 30 min to 4 hours exploring our stock.</p>
  </div>
  <div class="contact-grid">
    <div class="fade-in">
      <div class="contact-item">
        <div class="contact-icon-wrap">📍</div>
        <div>
          <div class="contact-label">Location</div>
          <div class="contact-value">Samithiya Road, Mawanella, Sri Lanka</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon-wrap">📞</div>
        <div>
          <div class="contact-label">Phone</div>
          <div class="contact-value"><a href="tel:0777279719">077 727 9719</a></div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon-wrap">💬</div>
        <div>
          <div class="contact-label">WhatsApp</div>
          <div class="contact-value"><a href="https://wa.me/94777279719" target="_blank">Message us on WhatsApp →</a></div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon-wrap">🕐</div>
        <div>
          <div class="contact-label">Busiest Hours</div>
          <div class="contact-value">3 PM – 9 PM Daily</div>
        </div>
      </div>
      <a href="tel:0777279719" class="btn-primary" style="margin-top: 1rem; display: inline-block;">Call Now</a>
    </div>
    <div class="fade-in">
      <div class="map-placeholder">
        <span class="pin">📍</span>
        <span>Samithiya Road, Mawanella</span>
        <a href="https://maps.google.com/?q=Inazawa+Electronics+Mawanella" target="_blank" class="btn-ghost" style="margin-top: 0.5rem; font-size: 0.82rem;">Open in Google Maps →</a>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-copy">© 2026 Inazawa Electronics Pvt Ltd — Mawanella, Sri Lanka</div>
  <div class="footer-links">
    <a href="#products">Products</a>
    <a href="#reviews">Reviews</a>
    <a href="#contact">Contact</a>
  </div>
</footer>

<script>
  // Cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  document.addEventListener('mousemove', e => {
    cursor.style.transform = `translate(${e.clientX - 6}px, ${e.clientY - 6}px)`;
    ring.style.transform = `translate(${e.clientX - 18}px, ${e.clientY - 18}px)`;
  });

  // Scroll fade-in
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); }
    });
  }, { threshold: 0.12 });
  document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
</script>
</body>
</html>
