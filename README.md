<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EDGE INTERIORS — Premium Interior Design, Bangalore</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        :root {
            --primary: #1a1a1a;
            --accent: #c9a96e;
            --accent-dark: #b8945f;
            --white: #ffffff;
            --cream: #faf8f5;
            --gray: #6b6b6b;
            --light-gray: #e8e8e8;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            color: var(--primary);
            background: var(--white);
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            padding: 20px 0;
            transition: all 0.4s ease;
        }

        .navbar.scrolled {
            background: rgba(255, 255, 255, 0.98);
            box-shadow: 0 2px 30px rgba(0,0,0,0.08);
            padding: 12px 0;
        }

        .navbar.scrolled .nav-logo,
        .navbar.scrolled .nav-links a {
            color: var(--primary);
        }

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