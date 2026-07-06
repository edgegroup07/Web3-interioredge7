<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Edge Interiors | Luxury Interior Design Studio</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,400;1,500&family=Inter:wght@300;400;500;600&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #FAF7F2;
    --warm-white: #F5F0E8;
    --sand: #E8DFD0;
    --taupe: #B8A99A;
    --warm-gray: #8C7E6E;
    --espresso: #3D3229;
    --charcoal: #2A2420;
    --gold: #C9A962;
    --rose-gold: #D4A5A5;
    --sage: #9CAF88;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--cream);
    color: var(--charcoal);
    overflow-x: hidden;
  }

  h1, h2, h3, .serif { font-family: 'Playfair Display', serif; }
  .accent-font { font-family: 'Cormorant Garamond', serif; }

  .nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 1000;
    padding: 1.5rem 3rem;
    display: flex; justify-content: space-between; align-items: center;
    transition: all 0.4s ease;
  }
  .nav.scrolled {
    background: rgba(250, 247, 242, 0.95);
    backdrop-filter: blur(20px);
    box-shadow: 0 2px 30px rgba(0,0,0,0.05);
    padding: 1rem 3rem;
  }
  .logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem; font-weight: 600;
    color: var(--cream);
    letter-spacing: 2px;
  }
  .nav.scrolled .logo { color: var(--espresso); }
  .nav-links {
    display: flex; gap: 2.5rem;
    list-style: none;
  }
  .nav-links a {
    text-decoration: none;
    color: var(--cream);
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    position: relative;
    transition: color 0.3s;
  }
  .nav.scrolled .nav-links a { color: var(--warm-gray); }
  .nav-links a::after {
    content: ''; position: absolute;
    bottom: -4px; left: 0;
    width: 0; height: 1px;
    background: var(--gold);
    transition: width 0.3s ease;
  }
  .nav-links a:hover::after { width: 100%; }
  .nav-links a:hover { color: var(--gold); }

  .hero {
    height: 100vh;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background: linear-gradient(135deg, #2A2420 0%, #3D3229 50%, #1a1612 100%);
  }
  .hero-bg::before {
    content: '';
    position: absolute; inset: 0;
    background: url('https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?w=1920&q=80') center/cover;
    opacity: 0.4;
  }
  .hero-content {
    position: relative;
    z-index: 2;
    text-align: center;
    color: var(--cream);
    max-width: 900px;
    padding: 0 2rem;
  }
  .hero-label {
    font-family: 'Inter', sans-serif;
    font-size: 0.75rem;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.5rem;
    opacity: 0;
    animation: fadeUp 1s ease 0.3s forwards;
  }
  .hero h1 {
    font-size: clamp(2.5rem, 6vw, 5rem);
    font-weight: 400;
    line-height: 1.1;
    margin-bottom: 1.5rem;
    opacity: 0;
    animation: fadeUp 1s ease 0.6s forwards;
  }
  .hero h1 em { font-style: italic; color: var(--gold); }
  .hero-subtitle {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(1.1rem, 2vw, 1.5rem);
    font-weight: 300;
    color: var(--sand);
    margin-bottom: 2.5rem;
    opacity: 0;
    animation: fadeUp 1s ease 0.9s forwards;
  }
  .hero-cta {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    padding: 1rem 2.5rem;
    background: transparent;
    border: 1px solid var(--gold);
    color: var(--gold);
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.4s ease;
    opacity: 0;
    animation: fadeUp 1s ease 1.2s forwards;
  }
  .hero-cta:hover { background: var(--gold); color: var(--charcoal); }
  .scroll-indicator {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    color: var(--taupe);
    font-size: 0.7rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    animation: bounce 2s infinite;
  }
  .scroll-line {
    width: 1px;
    height: 40px;
    background: linear-gradient(to bottom, var(--gold), transparent);
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes bounce {
    0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
    40% { transform: translateX(-50%) translateY(-10px); }
    60% { transform: translateX(-50%) translateY(-5px); }
  }

  section { padding: 6rem 0; }
  .container { max-width: 1200px; margin: 0 auto; padding: 0 2rem; }
  .section-header { text-align: center; margin-bottom: 4rem; }
  .section-label {
    font-family: 'Inter', sans-serif;
    font-size: 0.7rem;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }
  .section-title {
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 400;
    color: var(--espresso);
    line-height: 1.2;
  }
  .section-title em { font-style: italic; color: var(--warm-gray); }

  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }
  .about-images { position: relative; height: 500px; }
  .about-img-main {
    position: absolute;
    width: 75%;
    height: 85%;
    object-fit: cover;
    border-radius: 2px;
    box-shadow: 0 20px 60px rgba(0,0,0,0.15);
  }
  .about-img-accent {
    position: absolute;
    right: 0;
    bottom: 0;
    width: 50%;
    height: 55%;
    object-fit: cover;
    border-radius: 2px;
    box-shadow: 0 15px 40px rgba(0,0,0,0.12);
    border: 8px solid var(--cream);
  }
  .about-text h3 {
    font-size: 2rem;
    font-weight: 400;
    margin-bottom: 1.5rem;
    color: var(--espresso);
  }
  .about-text p {
    font-size: 0.95rem;
    line-height: 1.8;
    color: var(--warm-gray);
    margin-bottom: 1.5rem;
  }
  .stats {
    display: flex;
    gap: 2.5rem;
    margin-top: 2rem;
    padding-top: 2rem;
    border-top: 1px solid var(--sand);
  }
  .stat-item h4 {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    font-weight: 400;
    color: var(--espresso);
  }
  .stat-item span {
    font-size: 0.75rem;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--taupe);
  }

  .services { background: var(--warm-white); }
  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
  .service-card {
    background: var(--cream);
    padding: 2.5rem;
    border-radius: 2px;
    transition: all 0.4s ease;
    cursor: pointer;
    border: 1px solid transparent;
  }
  .service-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 20px 50px rgba(0,0,0,0.08);
    border-color: var(--sand);
  }
  .service-icon {
    width: 50px;
    height: 50px;
    margin-bottom: 1.5rem;
    color: var(--gold);
  }
  .service-card h3 {
    font-size: 1.3rem;
    font-weight: 500;
    margin-bottom: 0.75rem;
    color: var(--espresso);
  }
  .service-card p {
    font-size: 0.9rem;
    line-height: 1.7;
    color: var(--warm-gray);
  }
  .service-list {
    margin-top: 1.5rem;
    list-style: none;
  }
  .service-list li {
    font-size: 0.8rem;
    color: var(--taupe);
    padding: 0.4rem 0;
    border-bottom: 1px solid var(--sand);
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }
  .service-list li::before {
    content: '—';
    color: var(--gold);
  }

  .portfolio-filter {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin-bottom: 3rem;
    flex-wrap: wrap;
  }
  .filter-btn {
    padding: 0.6rem 1.5rem;
    background: transparent;
    border: 1px solid var(--sand);
    color: var(--warm-gray);
    font-family: 'Inter', sans-serif;
    font-size: 0.75rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    cursor: pointer;
    transition: all 0.3s;
    border-radius: 2px;
  }
  .filter-btn.active, .filter-btn:hover {
    background: var(--espresso);
    color: var(--cream);
    border-color: var(--espresso);
  }
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }
  .portfolio-item {
    position: relative;
    overflow: hidden;
    border-radius: 2px;
    cursor: pointer;
    aspect-ratio: 4/5;
  }
  .portfolio-item img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.6s ease;
  }
  .portfolio-item:hover img { transform: scale(1.08); }
  .portfolio-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to top, rgba(42,36,32,0.85) 0%, transparent 60%);
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 1.5rem;
    opacity: 0;
    transition: opacity 0.4s ease;
  }
  .portfolio-item:hover .portfolio-overlay { opacity: 1; }
  .portfolio-overlay h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    color: var(--cream);
    margin-bottom: 0.25rem;
  }
  .portfolio-overlay span {
    font-size: 0.7rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--gold);
  }

  .process {
    background: var(--espresso);
    color: var(--cream);
  }
  .process .section-title { color: var(--cream); }
  .process .section-label { color: var(--gold); }
  .process-steps {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2rem;
    position: relative;
  }
  .process-step {
    text-align: center;
    padding: 2rem;
    position: relative;
  }
  .step-number {
    font-family: 'Playfair Display', serif;
    font-size: 3.5rem;
    font-weight: 300;
    color: var(--gold);
    opacity: 0.3;
    line-height: 1;
    margin-bottom: 1rem;
  }
  .process-step h4 {
    font-size: 1.1rem;
    font-weight: 500;
    margin-bottom: 0.75rem;
    color: var(--cream);
  }
  .process-step p {
    font-size: 0.85rem;
    line-height: 1.7;
    color: var(--taupe);
  }
  .step-connector {
    position: absolute;
    top: 3.5rem;
    right: -1rem;
    width: 2rem;
    height: 1px;
    background: var(--warm-gray);
    opacity: 0.3;
  }

  .testimonials-slider {
    max-width: 800px;
    margin: 0 auto;
    position: relative;
  }
  .testimonial {
    text-align: center;
    padding: 2rem;
    display: none;
  }
  .testimonial.active { display: block; }
  .testimonial-quote {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(1.3rem, 2.5vw, 1.8rem);
    font-style: italic;
    line-height: 1.6;
    color: var(--espresso);
    margin-bottom: 2rem;
  }
  .testimonial-author {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1rem;
  }
  .testimonial-author img {
    width: 50px; height: 50px;
    border-radius: 50%;
    object-fit: cover;
  }
  .testimonial-author-info h5 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--espresso);
  }
  .testimonial-author-info span {
    font-size: 0.8rem;
    color: var(--taupe);
  }
  .testimonial-dots {
    display: flex;
    justify-content: center;
    gap: 0.5rem;
    margin-top: 2rem;
  }
  .dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--sand);
    cursor: pointer;
    transition: all 0.3s;
  }
  .dot.active {
    background: var(--espresso);
    transform: scale(1.2);
  }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
  }
  .contact-info h3 {
    font-size: 2rem;
    font-weight: 400;
    margin-bottom: 1rem;
    color: var(--espresso);
  }
  .contact-info > p {
    color: var(--warm-gray);
    line-height: 1.7;
    margin-bottom: 2rem;
  }
  .contact-detail {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 1.5rem;
  }
  .contact-detail svg {
    width: 20px; height: 20px;
    color: var(--gold);
    flex-shrink: 0;
    margin-top: 0.2rem;
  }
  .contact-detail h5 {
    font-size: 0.8rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--taupe);
    margin-bottom: 0.25rem;
  }
  .contact-detail p {
    font-size: 0.95rem;
    color: var(--espresso);
  }
  .contact-detail a {
    text-decoration: none;
    color: inherit;
    transition: color 0.3s;
  }
  .contact-detail a:hover { color: var(--gold); }

  .contact-form {
    background: var(--warm-white);
    padding: 2.5rem;
    border-radius: 2px;
  }
  .form-group { margin-bottom: 1.5rem; }
  .form-group label {
    display: block;
    font-size: 0.7rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--taupe);
    margin-bottom: 0.5rem;
  }
  .form-group input,
  .form-group textarea,
  .form-group select {
    width: 100%;
    padding: 0.875rem 1rem;
    border: 1px solid var(--sand);
    background: var(--cream);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    color: var(--espresso);
    border-radius: 2px;
    transition: border-color 0.3s;
  }
  .form-group input:focus,
  .form-group textarea:focus,
  .form-group select:focus {
    outline: none;
    border-color: var(--gold);
  }
  .form-group textarea {
    min-height: 120px;
    resize: vertical;
  }
  .submit-btn {
    width: 100%;
    padding: 1rem;
    background: var(--espresso);
    color: var(--cream);
    border: none;
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    cursor: pointer;
    transition: all 0.3s;
    border-radius: 2px;
  }
  .submit-btn:hover { background: var(--charcoal); }

  footer {
    background: var(--charcoal);
    color: var(--taupe);
    padding: 4rem 0 2rem;
  }
  .footer-grid {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 1fr;
    gap: 3rem;
    margin-bottom: 3rem;
  }
  .footer-brand .logo {
    color: var(--cream);
    margin-bottom: 1rem;
    display: inline-block;
  }
  .footer-brand p {
    font-size: 0.85rem;
    line-height: 1.7;
    max-width: 300px;
  }
  .footer-col h5 {
    font-family: 'Inter', sans-serif;
    font-size: 0.7rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--cream);
    margin-bottom: 1.5rem;
  }
  .footer-col ul { list-style: none; }
  .footer-col li { margin-bottom: 0.75rem; }
  .footer-col a {
    color: var(--taupe);
    text-decoration: none;
    font-size: 0.85rem;
    transition: color 0.3s;
  }
  .footer-col a:hover { color: var(--gold); }
  .footer-bottom {
    border-top: 1px solid rgba(184,169,154,0.2);
    padding-top: 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.8rem;
  }
  .social-links { display: flex; gap: 1rem; }
  .social-links a {
    width: 36px; height: 36px;
    border: 1px solid rgba(184,169,154,0.3);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--taupe);
    transition: all 0.3s;
  }
  .social-links a:hover {
    border-color: var(--gold);
    color: var(--gold);
  }

  .reveal {
    opacity: 0;
    transform: translateY(40px);
    transition: all 0.8s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  @media (max-width: 768px) {
    .nav-links { display: none; }
    .about-grid,
    .contact-grid,
    .footer-grid { grid-template-columns: 1fr; }
    .services-grid,
    .portfolio-grid,
    .process-steps { grid-template-columns: 1fr; }
    .process-step .step-connector { display: none; }
    .about-images { height: 350px; }
  }
</style>
</head>
<body>

<nav class="nav" id="navbar">
  <a href="#" class="logo">EDGE INTERIORS</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#portfolio">Portfolio</a></li>
    <li><a href="#process">Process</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <div class="hero-label">Luxury Interior Design Studio</div>
    <h1>Spaces That Tell <em>Your Story</em></h1>
    <p class="hero-subtitle">We craft bespoke interiors that harmonize elegance with livability, transforming houses into homes that reflect the soul of those who inhabit them.</p>
    <a href="#contact" class="hero-cta">
      Begin Your Journey
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
    </a>
  </div>
  <div class="scroll-indicator">
    <span>Scroll</span>
    <div class="scroll-line"></div>
  </div>
</section>

<section id="about">
  <div class="container">
    <div class="about-grid reveal">
      <div class="about-images">
        <img src="https://images.unsplash.com/photo-1618221195710-dd6b41faaea6?w=600&q=80" alt="Interior Design" class="about-img-main">
        <img src="https://images.unsplash.com/photo-1616486338812-3dadae4b4ace?w=400&q=80" alt="Design Detail" class="about-img-accent">
      </div>
      <div class="about-text">
        <div class="section-label">About Us</div>
        <h3>Designing with Intention, <em>Crafting with Soul</em></h3>
        <p>At Edge Interiors, we believe that exceptional interior design is not merely about aesthetics—it is about understanding how people live, work, and dream within their spaces. Founded in 2010, our studio has completed over 200 residential and commercial projects across India and beyond.</p>
        <p>Our multidisciplinary team brings together architects, interior designers, and artisans who share a singular vision: to create environments that inspire, comfort, and endure. From luxury apartments in Bangalore to serene villas in Goa, we approach each project with fresh eyes and unwavering dedication.</p>
        <div class="stats">
          <div class="stat-item"><h4>200+</h4><span>Projects</span></div>
          <div class="stat-item"><h4>14</h4><span>Years</span></div>
          <div class="stat-item"><h4>35</h4><span>Awards</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="services" class="services">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-label">What We Do</div>
      <h2 class="section-title">Comprehensive Design <em>Services</em></h2>
    </div>
    <div class="services-grid reveal">
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M3 9l9-7 9 7v11a2 2 0 01-2 2H5a2 2 0 01-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
        <h3>Residential Design</h3>
        <p>Full-service interior design for homes, apartments, and estates. From concept to completion, we manage every detail.</p>
        <ul class="service-list">
          <li>Space Planning & Layout</li>
          <li>Custom Furniture Design</li>
          <li>Material & Finish Selection</li>
          <li>Art Curation</li>
        </ul>
      </div>
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>
        <h3>Commercial Spaces</h3>
        <p>Elevating workplaces, hotels, and retail environments through strategic design that enhances brand identity and user experience.</p>
        <ul class="service-list">
          <li>Office & Workplace Design</li>
          <li>Hospitality Interiors</li>
          <li>Retail & Showroom Design</li>
          <li>Brand Integration</li>
        </ul>
      </div>
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
        <h3>Design Consultation</h3>
        <p>Expert guidance for clients who seek professional direction while maintaining hands-on involvement in their project.</p>
        <ul class="service-list">
          <li>Design Direction Sessions</li>
          <li>Color & Material Consulting</li>
          <li>Furniture Sourcing</li>
          <li>Virtual Design Services</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<section id="portfolio">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-label">Our Work</div>
      <h2 class="section-title">Featured <em>Projects</em></h2>
    </div>
    <div class="portfolio-filter reveal">
      <button class="filter-btn active" data-filter="all">All</button>
      <button class="filter-btn" data-filter="residential">Residential</button>
      <button class="filter-btn" data-filter="commercial">Commercial</button>
      <button class="filter-btn" data-filter="hospitality">Hospitality</button>
    </div>
    <div class="portfolio-grid reveal" id="portfolioGrid">
      <div class="portfolio-item" data-category="residential">
        <img src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?w=600&q=80" alt="The Madison Residence">
        <div class="portfolio-overlay"><h4>The Madison Residence</h4><span>Bangalore, India</span></div>
      </div>
      <div class="portfolio-item" data-category="hospitality">
        <img src="https://images.unsplash.com/photo-1618773928121-c32242e63f39?w=600&q=80" alt="Casa del Sol">
        <div class="portfolio-overlay"><h4>Casa del Sol</h4><span>Goa, India</span></div>
      </div>
      <div class="portfolio-item" data-category="commercial">
        <img src="https://images.unsplash.com/photo-1497366216548-37526070297c?w=600&q=80" alt="Meridian Offices">
        <div class="portfolio-overlay"><h4>Meridian Offices</h4><span>Bangalore, India</span></div>
      </div>
      <div class="portfolio-item" data-category="residential">
        <img src="https://images.unsplash.com/photo-1600566753190-17f0baa2a6c3?w=600&q=80" alt="The Hudson Loft">
        <div class="portfolio-overlay"><h4>The Hudson Loft</h4><span>Delhi, India</span></div>
      </div>
      <div class="portfolio-item" data-category="hospitality">
        <img src="https://images.unsplash.com/photo-1582719478250-c89cae4dc85b?w=600&q=80" alt="Azure Boutique Hotel">
        <div class="portfolio-overlay"><h4>Azure Boutique Hotel</h4><span>Jaipur, India</span></div>
      </div>
      <div class="portfolio-item" data-category="commercial">
        <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c?w=600&q=80" alt="Vista Gallery">
        <div class="portfolio-overlay"><h4>Vista Gallery</h4><span>Pune, India</span></div>
      </div>
    </div>
  </div>
</section>

<section id="process" class="process">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-label">How We Work</div>
      <h2 class="section-title">Our Design <em>Process</em></h2>
    </div>
    <div class="process-steps reveal">
      <div class="process-step">
        <div class="step-number">01</div>
        <h4>Discovery</h4>
        <p>We begin with deep listening—understanding your lifestyle, aspirations, and the story you want your space to tell.</p>
        <div class="step-connector"></div>
      </div>
      <div class="process-step">
        <div class="step-number">02</div>
        <h4>Concept</h4>
        <p>Our designers translate your vision into mood boards, spatial plans, and 3D visualizations that bring ideas to life.</p>
        <div class="step-connector"></div>
      </div>
      <div class="process-step">
        <div class="step-number">03</div>
        <h4>Development</h4>
        <p>We refine every detail—materials, finishes, custom furniture, and lighting—to ensure cohesive, timeless design.</p>
        <div class="step-connector"></div>
      </div>
      <div class="process-step">
        <div class="step-number">04</div>
        <h4>Delivery</h4>
        <p>From procurement to installation, we manage the entire execution with meticulous attention to quality and timeline.</p>
      </div>
    </div>
  </div>
</section>

<section id="testimonials">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-label">Testimonials</div>
      <h2 class="section-title">Words from Our <em>Clients</em></h2>
    </div>
    <div class="testimonials-slider reveal">
      <div class="testimonial active">
        <p class="testimonial-quote">"Edge Interiors transformed our penthouse into a sanctuary. Their attention to detail and ability to capture our personality in every corner was extraordinary. It feels like home in a way we never imagined possible."</p>
        <div class="testimonial-author">
          <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=100&q=80" alt="Priya Sharma">
          <div class="testimonial-author-info"><h5>Priya Sharma</h5><span>The Madison Residence, Bangalore</span></div>
        </div>
      </div>
      <div class="testimonial">
        <p class="testimonial-quote">"Working with the Edge Interiors team on our boutique hotel was a revelation. They understood our brand instantly and created spaces that our guests never want to leave. Truly world-class design."</p>
        <div class="testimonial-author">
          <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&q=80" alt="Rajesh Mehta">
          <div class="testimonial-author-info"><h5>Rajesh Mehta</h5><span>Azure Boutique Hotel, Jaipur</span></div>
        </div>
      </div>
      <div class="testimonial">
        <p class="testimonial-quote">"The team balanced creativity with practicality perfectly. Our office now inspires productivity while feeling warm and inviting. The best investment we've made for our company culture."</p>
        <div class="testimonial-author">
          <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=100&q=80" alt="Vikram Patel">
          <div class="testimonial-author-info"><h5>Vikram Patel</h5><span>Meridian Offices, Bangalore</span></div>
        </div>
      </div>
      <div class="testimonial-dots">
        <span class="dot active" data-index="0"></span>
        <span class="dot" data-index="1"></span>
        <span class="dot" data-index="2"></span>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="container">
    <div class="contact-grid reveal">
      <div class="contact-info">
        <div class="section-label">Get in Touch</div>
        <h3>Let's Create <em>Something Beautiful</em></h3>
        <p>Whether you are envisioning a complete transformation or seeking expert guidance, we'd love to hear about your project. Every great space begins with a conversation.</p>
        <div class="contact-detail">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
          <div><h5>Studio</h5><p>12, MG Road, Suite 301<br>Bangalore Central, Karnataka 560001</p></div>
        </div>
        <div class="contact-detail">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          <div><h5>Email</h5><p><a href="mailto:hello@edgeinteriors.in">hello@edgeinteriors.in</a></p></div>
        </div>
        <div class="contact-detail">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07 19.5 19.5 0 01-6-6 19.79 19.79 0 01-3.07-8.67A2 2 0 014.11 2h3a2 2 0 012 1.72c.127.96.361 1.903.7 2.81a2 2 0 01-.45 2.11L8.09 9.91a16 16 0 006 6l1.27-1.27a2 2 0 012.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0122 16.92z"/></svg>
          <div><h5>Phone</h5><p><a href="tel:+917975780715">+91 79757 80715</a></p></div>
        </div>
        <div class="contact-detail">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 11.5a8.38 8.38 0 01-.9 3.8 8.5 8.5 0 01-7.6 4.7 8.38 8.38 0 01-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 01-.9-3.8 8.5 8.5 0 014.7-7.6 8.38 8.38 0 013.8-.9h.5a8.48 8.48 0 018 8v.5z"/></svg>
          <div><h5>WhatsApp</h5><p><a href="https://wa.me/917975780715" target="_blank">+91 79757 80715</a></p></div>
        </div>
      </div>
      <form class="contact-form" id="contactForm">
        <div class="form-group"><label>Full Name</label><input type="text" placeholder="Your name" required></div>
        <div class="form-group"><label>Email Address</label><input type="email" placeholder="your@email.com" required></div>
        <div class="form-group"><label>Phone Number</label><input type="tel" placeholder="+91 XXXXX XXXXX"></div>
        <div class="form-group">
          <label>Project Type</label>
          <select required>
            <option value="">Select a service</option>
            <option value="residential">Residential Design</option>
            <option value="commercial">Commercial Design</option>
            <option value="consultation">Design Consultation</option>
            <option value="other">Other</option>
          </select>
        </div>
        <div class="form-group"><label>Tell Us About Your Project</label><textarea placeholder="Share your vision, timeline, and any specific requirements..."></textarea></div>
        <button type="submit" class="submit-btn">Send Inquiry</button>
      </form>
    </div>
  </div>
</section>

<footer>
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <span class="logo">EDGE INTERIORS</span>
        <p>Creating timeless interiors that inspire and endure. Based in Bangalore Central, designing across India.</p>
      </div>
      <div class="footer-col">
        <h5>Services</h5>
        <ul>
          <li><a href="#">Residential Design</a></li>
          <li><a href="#">Commercial Spaces</a></li>
          <li><a href="#">Design Consultation</a></li>
          <li><a href="#">Art Curation</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Company</h5>
        <ul>
          <li><a href="#">About Us</a></li>
          <li><a href="#">Our Team</a></li>
          <li><a href="#">Careers</a></li>
          <li><a href="#">Press</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Connect</h5>
        <ul>
          <li><a href="#">Instagram</a></li>
          <li><a href="#">Pinterest</a></li>
          <li><a href="#">LinkedIn</a></li>
          <li><a href="#">Houzz</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>&copy; 2026 Edge Interiors. All rights reserved.</span>
      <div class="social-links">
        <a href="#"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><path d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg></a>
        <a href="#"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"/></svg></a>
        <a href="#"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg></a>
      </div>
    </div>
  </div>
</footer>

<script>
  const navbar = document.getElementById('navbar');
  window.addEventListener('scroll', () => {
    navbar.classList.toggle('scrolled', window.scrollY > 50);
  });

  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
      e.preventDefault();
      const target = document.querySelector(this.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    });
  });

  const revealElements = document.querySelectorAll('.reveal');
  const revealObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add('visible'); });
  }, { threshold: 0.1 });
  revealElements.forEach(el => revealObserver.observe(el));

  const filterBtns = document.querySelectorAll('.filter-btn');
  const portfolioItems = document.querySelectorAll('.portfolio-item');
  filterBtns.forEach(btn => {
    btn.addEventListener('click', () => {
      filterBtns.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      const filter = btn.dataset.filter;
      portfolioItems.forEach(item => {
        if (filter === 'all' || item.dataset.category === filter) {
          item.style.display = 'block';
          setTimeout(() => item.style.opacity = '1', 10);
        } else {
          item.style.opacity = '0';
          setTimeout(() => item.style.display = 'none', 300);
        }
      });
    });
  });

  const testimonials = document.querySelectorAll('.testimonial');
  const dots = document.querySelectorAll('.dot');
  let currentSlide = 0;
  function showSlide(index) {
    testimonials.forEach((t, i) => t.classList.toggle('active', i === index));
    dots.forEach((d, i) => d.classList.toggle('active', i === index));
    currentSlide = index;
  }
  dots.forEach(dot => dot.addEventListener('click', () => showSlide(parseInt(dot.dataset.index))));
  setInterval(() => showSlide((currentSlide + 1) % testimonials.length), 5000);

  document.getElementById('contactForm').addEventListener('submit', (e) => {
    e.preventDefault();
    const btn = e.target.querySelector('.submit-btn');
    const originalText = btn.textContent;
    btn.textContent = 'Message Sent!';
    btn.style.background = '#9CAF88';
    setTimeout(() => { btn.textContent = originalText; btn.style.background = ''; e.target.reset(); }, 3000);
  });
</script>

</body>
</html>        }

        .navbar.scrolled .nav-links a:hover {
            color: var(--accent);
        }

        .nav-container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .nav-logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.6rem;
            font-weight: 700;
            color: var(--white);
            text-decoration: none;
            letter-spacing: 2px;
        }

        .nav-logo span {
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 35px;
            list-style: none;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: 1px;
            text-transform: uppercase;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-cta {
            background: var(--accent);
            color: var(--white) !important;
            padding: 10px 24px;
            border-radius: 4px;
            font-weight: 600 !important;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .nav-cta:hover {
            background: var(--accent-dark);
        }

        .nav-cta::after {
            display: none !important;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, rgba(26,26,26,0.85) 0%, rgba(26,26,26,0.6) 100%),
                        url('https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?w=1920&q=80') center/cover no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
            position: relative;
        }

        .hero-content {
            max-width: 900px;
            padding: 0 30px;
            animation: fadeInUp 1s ease;
        }

        .hero-subtitle {
            font-size: 0.85rem;
            letter-spacing: 4px;
            text-transform: uppercase;
            color: var(--accent);
            margin-bottom: 20px;
            font-weight: 500;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 25px;
        }

        .hero p {
            font-size: 1.15rem;
            line-height: 1.8;
            color: rgba(255,255,255,0.85);
            margin-bottom: 40px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-btns {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 14px 36px;
            border-radius: 4px;
            font-size: 0.9rem;
            font-weight: 600;
            letter-spacing: 1px;
            text-transform: uppercase;
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .btn-primary {
            background: var(--accent);
            color: var(--white);
        }

        .btn-primary:hover {
            background: var(--accent-dark);
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(201,169,110,0.3);
        }

        .btn-outline {
            background: transparent;
            color: var(--white);
            border: 2px solid var(--white);
        }

        .btn-outline:hover {
            background: var(--white);
            color: var(--primary);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        .scroll-indicator i {
            font-size: 1.5rem;
            color: var(--accent);
        }

        /* Section Styles */
        section {
            padding: 100px 0;
        }

        .container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 30px;
        }

        .section-header {
            text-align: center;
            margin-bottom: 70px;
        }

        .section-header h2 {
            font-size: clamp(2rem, 4vw, 3rem);
            margin-bottom: 15px;
            color: var(--primary);
        }

        .section-header p {
            color: var(--gray);
            font-size: 1.05rem;
            max-width: 600px;
            margin: 0 auto;
            line-height: 1.7;
        }

        .section-label {
            display: inline-block;
            font-size: 0.8rem;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: var(--accent);
            font-weight: 600;
            margin-bottom: 15px;
        }

        /* About Section */
        .about {
            background: var(--cream);
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-images {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .about-images img {
            width: 100%;
            height: 280px;
            object-fit: cover;
            border-radius: 8px;
        }

        .about-images img:first-child {
            grid-column: span 2;
            height: 350px;
        }

        .about-content h2 {
            font-size: clamp(2rem, 3vw, 2.8rem);
            margin-bottom: 20px;
        }

        .about-content p {
            color: var(--gray);
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .about-features {
            display: flex;
            gap: 30px;
            margin-top: 30px;
        }

        .about-feature {
            text-align: center;
        }

        .about-feature h4 {
            font-size: 2rem;
            color: var(--accent);
            margin-bottom: 5px;
        }

        .about-feature span {
            font-size: 0.85rem;
            color: var(--gray);
        }

        /* Services */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: var(--white);
            border: 1px solid var(--light-gray);
            border-radius: 12px;
            padding: 45px 35px;
            text-align: center;
            transition: all 0.4s ease;
            cursor: pointer;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(0,0,0,0.1);
            border-color: var(--accent);
        }

        .service-icon {
            width: 70px;
            height: 70px;
            background: var(--cream);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 25px;
            font-size: 1.5rem;
            color: var(--accent);
            transition: all 0.3s ease;
        }

        .service-card:hover .service-icon {
            background: var(--accent);
            color: var(--white);
        }

        .service-card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
        }

        .service-card p {
            color: var(--gray);
            line-height: 1.7;
            font-size: 0.95rem;
        }

        /* Portfolio */
        .portfolio {
            background: var(--primary);
            color: var(--white);
        }

        .portfolio .section-header h2,
        .portfolio .section-header p {
            color: var(--white);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 25px;
        }

        .portfolio-item {
            position: relative;
            overflow: hidden;
            border-radius: 12px;
            cursor: pointer;
            height: 400px;
        }

        .portfolio-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .portfolio-item:hover img {
            transform: scale(1.1);
        }

        .portfolio-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(26,26,26,0.9) 0%, transparent 60%);
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            padding: 30px;
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }

        .portfolio-overlay h3 {
            font-size: 1.4rem;
            margin-bottom: 5px;
        }

        .portfolio-overlay span {
            color: var(--accent);
            font-size: 0.9rem;
        }

        /* Stats */
        .stats {
            background: var(--cream);
            padding: 80px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            text-align: center;
        }

        .stat-item h3 {
            font-size: 3rem;
            color: var(--accent);
            margin-bottom: 10px;
        }

        .stat-item p {
            color: var(--gray);
            font-size: 0.95rem;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        /* Process */
        .process-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 30px;
            position: relative;
        }

        .process-step {
            text-align: center;
            padding: 30px;
            position: relative;
        }

        .process-step::after {
            content: '';
            position: absolute;
            top: 50px;
            right: -15px;
            width: 30px;
            height: 2px;
            background: var(--accent);
        }

        .process-step:last-child::after {
            display: none;
        }

        .process-number {
            width: 60px;
            height: 60px;
            background: var(--accent);
            color: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            font-weight: 700;
            margin: 0 auto 25px;
            font-family: 'Playfair Display', serif;
        }

        .process-step h3 {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }

        .process-step p {
            color: var(--gray);
            font-size: 0.9rem;
            line-height: 1.6;
        }

        /* Testimonials */
        .testimonials {
            background: var(--cream);
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background: var(--white);
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 5px 30px rgba(0,0,0,0.05);
        }

        .testimonial-stars {
            color: var(--accent);
            margin-bottom: 20px;
            font-size: 0.9rem;
        }

        .testimonial-card p {
            font-style: italic;
            line-height: 1.8;
            color: var(--gray);
            margin-bottom: 25px;
            font-size: 1.05rem;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .testimonial-author img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            object-fit: cover;
        }

        .testimonial-author h4 {
            font-size: 1rem;
            margin-bottom: 3px;
        }

        .testimonial-author span {
            font-size: 0.85rem;
            color: var(--gray);
        }

        /* CTA Section */
        .cta-section {
            background: linear-gradient(135deg, var(--primary) 0%, #2d2d2d 100%);
            color: var(--white);
            text-align: center;
            padding: 100px 0;
        }

        .cta-section h2 {
            font-size: clamp(2rem, 4vw, 3rem);
            margin-bottom: 20px;
        }

        .cta-section p {
            font-size: 1.1rem;
            color: rgba(255,255,255,0.8);
            margin-bottom: 40px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-phone {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            background: var(--accent);
            color: var(--white);
            padding: 16px 40px;
            border-radius: 4px;
            font-size: 1.3rem;
            font-weight: 700;
            text-decoration: none;
            margin-bottom: 20px;
            transition: all 0.3s ease;
        }

        .cta-phone:hover {
            background: var(--accent-dark);
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(201,169,110,0.3);
        }

        .cta-phone i {
            font-size: 1.1rem;
        }

        .cta-note {
            font-size: 0.9rem;
            color: rgba(255,255,255,0.6);
        }

        /* Footer */
        .footer {
            background: #111;
            color: rgba(255,255,255,0.7);
            padding: 80px 0 30px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1.5fr;
            gap: 50px;
            margin-bottom: 60px;
        }

        .footer-brand h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            color: var(--white);
            margin-bottom: 20px;
        }

        .footer-brand h3 span {
            color: var(--accent);
        }

        .footer-brand p {
            line-height: 1.8;
            margin-bottom: 25px;
        }

        .footer-social {
            display: flex;
            gap: 15px;
        }

        .footer-social a {
            width: 40px;
            height: 40px;
            border: 1px solid rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .footer-social a:hover {
            background: var(--accent);
            border-color: var(--accent);
        }

        .footer-links h4 {
            color: var(--white);
            font-size: 1.1rem;
            margin-bottom: 25px;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 12px;
        }

        .footer-links a {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--accent);
        }

        .footer-contact p {
            display: flex;
            align-items: flex-start;
            gap: 12px;
            margin-bottom: 18px;
            line-height: 1.6;
        }

        .footer-contact i {
            color: var(--accent);
            margin-top: 3px;
        }

        .footer-contact a {
            color: var(--accent);
            text-decoration: none;
            font-weight: 600;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,0.1);
            padding-top: 30px;
            text-align: center;
            font-size: 0.9rem;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-15px);
            }
            60% {
                transform: translateX(-50%) translateY(-8px);
            }
        }

        /* Scroll Reveal */
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Mobile Responsive */
        @media (max-width: 992px) {
            .about-grid {
                grid-template-columns: 1fr;
            }

            .footer-grid {
                grid-template-columns: 1fr 1fr;
            }

            .process-step::after {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: rgba(26,26,26,0.98);
                flex-direction: column;
                padding: 30px;
                gap: 20px;
            }

            .nav-links.active {
                display: flex;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .footer-grid {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .portfolio-grid {
                grid-template-columns: 1fr;
            }

            .about-images {
                grid-template-columns: 1fr;
            }

            .about-images img:first-child {
                grid-column: span 1;
            }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <a href="#" class="nav-logo">EDGE <span>INTERIORS</span></a>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#portfolio">Portfolio</a></li>
                <li><a href="#process">Process</a></li>
                <li><a href="#contact">Contact</a></li>
                <li><a href="tel:+917975780715" class="nav-cta"><i class="fas fa-phone"></i> +91 79757 80715</a></li>
            </ul>
            <button class="mobile-menu-btn" id="mobileMenuBtn"><i class="fas fa-bars"></i></button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <p class="hero-subtitle">Premium Interior Design Studio</p>
            <h1>Transform Your Space Into a Masterpiece</h1>
            <p>We create sophisticated, functional interiors that reflect your personality and elevate your everyday living experience in Bangalore and beyond.</p>
            <div class="hero-btns">
                <a href="#portfolio" class="btn btn-primary"><i class="fas fa-images"></i> View Our Work</a>
                <a href="tel:+917975780715" class="btn btn-outline"><i class="fas fa-phone"></i> Call Now: +91 79757 80715</a>
            </div>
        </div>
        <div class="scroll-indicator">
            <i class="fas fa-chevron-down"></i>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <div class="about-grid">
                <div class="about-images reveal">
                    <img src="https://images.unsplash.com/photo-1618221195710-dd6b41faaea6?w=800&q=80" alt="Interior Design">
                    <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c?w=600&q=80" alt="Living Room">
                    <img src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?w=600&q=80" alt="Modern Kitchen">
                </div>
                <div class="about-content reveal">
                    <span class="section-label">About Us</span>
                    <h2>Crafting Spaces That Inspire</h2>
                    <p>EDGE INTERIORS is a premier interior design firm dedicated to creating sophisticated spaces that seamlessly blend aesthetics with functionality. Our team of experienced designers brings innovative solutions to every project.</p>
                    <p>We believe that great design is more than just beautiful spaces — it's about creating environments that enhance the way you live and work. From residential havens to commercial masterpieces, we transform visions into reality.</p>
                    <div class="about-features">
                        <div class="about-feature">
                            <h4>10+</h4>
                            <span>Years Experience</span>
                        </div>
                        <div class="about-feature">
                            <h4>500+</h4>
                            <span>Projects Done</span>
                        </div>
                        <div class="about-feature">
                            <h4>300+</h4>
                            <span>Happy Clients</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <div class="container">
            <div class="section-header reveal">
                <span class="section-label">Our Services</span>
                <h2>What We Offer</h2>
                <p>Comprehensive interior design solutions tailored to your unique style and requirements.</p>
            </div>
            <div class="services-grid">
                <div class="service-card reveal">
                    <div class="service-icon"><i class="fas fa-home"></i></div>
                    <h3>Residential Design</h3>
                    <p>Transform your home into a sanctuary with our bespoke residential interior design services, from apartments to villas.</p>
                </div>
                <div class="service-card reveal">
                    <div class="service-icon"><i class="fas fa-building"></i></div>
                    <h3>Commercial Spaces</h3>
                    <p>Create inspiring workspaces that boost productivity and leave a lasting impression on clients and employees.</p>
                </div>
                <div class="service-card reveal">
                    <div class="service-icon"><i class="fas fa-utensils"></i></div>
                    <h3>Modular Kitchens</h3>
                    <p>Custom kitchen designs that combine style, functionality, and smart storage solutions for the heart of your home.</p>
                </div>
                <div class="service-card reveal">
                    <div class="service-icon"><i class="fas fa-couch"></i></div>
                    <h3>Furniture Design</h3>
                    <p>Handcrafted, custom furniture pieces designed to perfectly complement your space and personal aesthetic.</p>
                </div>
                <div class="service-card reveal">
                    <div class="service-icon"><i class="fas fa-ruler-combined"></i></div>
                    <h3>Space Planning</h3>
                    <p>Optimize your layout for flow, functionality, and comfort with expert space planning and 2D/3D visualization.</p>
                </div>
                <div class="service-card reveal">
                    <div class="service-icon"><i class="fas fa-cube"></i></div>
                    <h3>3D Visualization</h3>
                    <p>See your future space before it's built with photorealistic 3D renders and virtual walkthroughs.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio" id="portfolio">
        <div class="container">
            <div class="section-header reveal">
                <span class="section-label">Our Portfolio</span>
                <h2>Featured Projects</h2>
                <p>A glimpse into our finest interior design transformations across Bangalore.</p>
            </div>
            <div class="portfolio-grid">
                <div class="portfolio-item reveal">
                    <img src="https://images.unsplash.com/photo-1600210492493-0946911123ea?w=800&q=80" alt="Luxury Living Room">
                    <div class="portfolio-overlay">
                        <h3>Luxury Living Room</h3>
                        <span>Indiranagar, Bangalore</span>
                    </div>
                </div>
                <div class="portfolio-item reveal">
                    <img src="https://images.unsplash.com/photo-1600585154526-990dced4db0d?w=800&q=80" alt="Modern Kitchen">
                    <div class="portfolio-overlay">
                        <h3>Modern Modular Kitchen</h3>
                        <span>Whitefield, Bangalore</span>
                    </div>
                </div>
                <div class="portfolio-item reveal">
                    <img src="https://images.unsplash.com/photo-1600566753086-00f18fb6b3ea?w=800&q=80" alt="Master Bedroom">
                    <div class="portfolio-overlay">
                        <h3>Master Bedroom Suite</h3>
                        <span>Koramangala, Bangalore</span>
                    </div>
                </div>
                <div class="portfolio-item reveal">
                    <img src="https://images.unsplash.com/photo-1600607687644-c7171b42498f?w=800&q=80" alt="Office Space">
                    <div class="portfolio-overlay">
                        <h3>Corporate Office</h3>
                        <span>Electronic City, Bangalore</span>
                    </div>
                </div>
                <div class="portfolio-item reveal">
                    <img src="https://images.unsplash.com/photo-1600573472550-8090b5e0745e?w=800&q=80" alt="Dining Area">
                    <div class="portfolio-overlay">
                        <h3>Elegant Dining Space</h3>
                        <span>Jayanagar, Bangalore</span>
                    </div>
                </div>
                <div class="portfolio-item reveal">
                    <img src="https://images.unsplash.com/photo-1600566752355-35792bedcfea?w=800&q=80" alt="Bathroom">
                    <div class="portfolio-overlay">
                        <h3>Spa-Inspired Bathroom</h3>
                        <span>HSR Layout, Bangalore</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
        <div class="container">
            <div class="stats-grid">
                <div class="stat-item reveal">
                    <h3>10+</h3>
                    <p>Years of Experience</p>
                </div>
                <div class="stat-item reveal">
                    <h3>500+</h3>
                    <p>Projects Completed</p>
                </div>
                <div class="stat-item reveal">
                    <h3>300+</h3>
                    <p>Happy Clients</p>
                </div>
                <div class="stat-item reveal">
                    <h3>15+</h3>
                    <p>Design Awards</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Process Section -->
    <section class="process" id="process">
        <div class="container">
            <div class="section-header reveal">
                <span class="section-label">How We Work</span>
                <h2>Our Design Process</h2>
                <p>A streamlined approach to bring your dream space to life, from concept to completion.</p>
            </div>
            <div class="process-grid">
                <div class="process-step reveal">
                    <div class="process-number">1</div>
                    <h3>Consultation</h3>
                    <p>We discuss your vision, requirements, budget, and timeline to understand your needs.</p>
                </div>
                <div class="process-step reveal">
                    <div class="process-number">2</div>
                    <h3>Design Concept</h3>
                    <p>Our team creates mood boards, layouts, and initial design concepts for your approval.</p>
                </div>
                <div class="process-step reveal">
                    <div class="process-number">3</div>
                    <h3>3D Visualization</h3>
                    <p>Experience your space with photorealistic 3D renders before construction begins.</p>
                </div>
                <div class="process-step reveal">
                    <div class="process-number">4</div>
                    <h3>Execution</h3>
                    <p>Our skilled team brings the design to life with precision craftsmanship and quality materials.</p>
                </div>
                <div class="process-step reveal">
                    <div class="process-number">5</div>
                    <h3>Handover</h3>
                    <p>We deliver your transformed space with a final walkthrough and quality assurance.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <div class="section-header reveal">
                <span class="section-label">Testimonials</span>
                <h2>What Our Clients Say</h2>
                <p>Hear from the people who have experienced the EDGE INTERIORS difference.</p>
            </div>
            <div class="testimonials-grid">
                <div class="testimonial-card reveal">
                    <div class="testimonial-stars">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                    </div>
                    <p>"EDGE INTERIORS transformed our apartment into a dream home. Their attention to detail and understanding of our style was exceptional. Highly recommend!"</p>
                    <div class="testimonial-author">
                        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&q=80" alt="Client">
                        <div>
                            <h4>Rahul Sharma</h4>
                            <span>Indiranagar, Bangalore</span>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card reveal">
                    <div class="testimonial-stars">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                    </div>
                    <p>"The team designed our office space brilliantly. Productivity has increased and our clients are always impressed. Professional and creative throughout."</p>
                    <div class="testimonial-author">
                        <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=100&q=80" alt="Client">
                        <div>
                            <h4>Priya Nair</h4>
                            <span>Koramangala, Bangalore</span>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card reveal">
                    <div class="testimonial-stars">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                    </div>
                    <p>"From the modular kitchen to the living room, everything was perfect. They delivered on time and within budget. Best interior designers in Bangalore!"</p>
                    <div class="testimonial-author">
                        <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=100&q=80" alt="Client">
                        <div>
                            <h4>Arun Kumar</h4>
                            <span>Whitefield, Bangalore</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section" id="contact">
        <div class="container">
            <div class="reveal">
                <h2>Ready to Transform Your Space?</h2>
                <p>Get a free consultation with our expert designers. Call us now and take the first step towards your dream interior.</p>
                <a href="tel:+917975780715" class="cta-phone">
                    <i class="fas fa-phone-alt"></i>
                    +91 79757 80715
                </a>
                <p class="cta-note">Available Monday - Saturday, 9 AM - 7 PM</p>
                <div style="margin-top: 30px;">
                    <a href="mailto:info@edgeinteriors.com" class="btn btn-outline" style="border-color: var(--accent); color: var(--accent);">
                        <i class="fas fa-envelope"></i> Email Us
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand">
                    <h3>EDGE <span>INTERIORS</span></h3>
                    <p>Premium interior design studio based in Bangalore, creating sophisticated spaces that blend aesthetics with functionality since 2014.</p>
                    <div class="footer-social">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-pinterest-p"></i></a>
                    </div>
                </div>
                <div class="footer-links">
                    <h4>Quick Links</h4>
                    <ul>
                        <li><a href="#home">Home</a></li>
                        <li><a href="#about">About Us</a></li>
                        <li><a href="#services">Services</a></li>
                        <li><a href="#portfolio">Portfolio</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-links">
                    <h4>Services</h4>
                    <ul>
                        <li><a href="#">Residential Design</a></li>
                        <li><a href="#">Commercial Spaces</a></li>
                        <li><a href="#">Modular Kitchens</a></li>
                        <li><a href="#">Furniture Design</a></li>
                        <li><a href="#">3D Visualization</a></li>
                    </ul>
                </div>
                <div class="footer-links footer-contact">
                    <h4>Contact Us</h4>
                    <p><i class="fas fa-map-marker-alt"></i> Bangalore, Karnataka, India</p>
                    <p><i class="fas fa-phone"></i> <a href="tel:+917975780715">+91 79757 80715</a></p>
                    <p><i class="fas fa-envelope"></i> <a href="mailto:info@edgeinteriors.com">info@edgeinteriors.com</a></p>
                    <p><i class="fas fa-clock"></i> Mon - Sat: 9:00 AM - 7:00 PM</p>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2026 EDGE INTERIORS. All rights reserved. | Designed with passion in Bangalore.</p>
            </div>
        </div>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Mobile menu toggle
        document.getElementById('mobileMenuBtn').addEventListener('click', function() {
            document.getElementById('navLinks').classList.toggle('active');
        });

        // Scroll reveal animation
        const revealElements = document.querySelectorAll('.reveal');

        const revealOnScroll = () => {
            revealElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;

                if (elementTop < windowHeight - 100) {
                    element.classList.add('active');
                }
            });
        };

        window.addEventListener('scroll', revealOnScroll);
        window.addEventListener('load', revealOnScroll);
    </script>

</body>
</html>
