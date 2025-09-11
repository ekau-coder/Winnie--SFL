<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nneka Udoye - Senior Salesforce & FSL Administrator</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <style>
        /* General Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #002244; /* Deep Midnight Blue */
            --secondary-color: #DD5A01; /* Rich Burnt Orange */
            --accent-color: #F0A500; /* Vibrant Gold Accent */
            --dark-color: #222831; /* Dark Grey for text */
            --light-color: #F8F8F8; /* Light background */
            --white: #FFFFFF;
            --gradient-primary: linear-gradient(135deg, #002244 0%, #0A436D 100%);
            --gradient-secondary: linear-gradient(135deg, #DD5A01 0%, #FF8C00 100%);
            --shadow: 0 8px 25px rgba(0, 34, 68, 0.1);
            --shadow-hover: 0 12px 35px rgba(0, 34, 68, 0.2);
            --border-radius: 12px;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            line-height: 1.7;
            color: var(--dark-color);
            background-color: var(--light-color);
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 25px;
        }

        /* Header */
        .header {
            background: var(--gradient-primary);
            color: var(--white);
            padding: 1rem 0;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent-color);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2.5rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--white);
            font-weight: 500;
            font-size: 1.05rem;
            position: relative;
            transition: color 0.3s ease;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 3px;
            background-color: var(--secondary-color);
            left: 0;
            bottom: -8px;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }
        
        .nav-links a:hover {
            color: var(--secondary-color);
        }

        .mobile-menu {
            display: none;
            font-size: 1.8rem;
            cursor: pointer;
            color: var(--white);
        }

        /* Hero/About Section */
        .about-hero {
            background: var(--white);
            padding: 100px 0 60px; /* Adjusted padding */
            text-align: center;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
            border-bottom: 6px solid var(--secondary-color);
            position: relative;
            overflow: hidden;
        }

        .about-hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><filter id="noiseFilter"><feTurbulence type="fractalNoise" baseFrequency="0.6" numOctaves="3" stitchTiles="stitch"/></filter><rect width="100%" height="100%" filter="url(%23noiseFilter)" opacity="0.05"/></svg>') repeat;
            opacity: 0.2;
            pointer-events: none;
        }

        .about-hero .profile-pic {
            width: 220px;
            height: 220px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid var(--accent-color);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
            margin-bottom: 2.5rem;
            animation: fadeInScale 0.8s ease-out forwards;
        }

        .about-hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4.2rem;
            color: var(--primary-color);
            margin-bottom: 0.8rem;
            animation: fadeInUp 1s ease-out forwards 0.2s;
            opacity: 0;
        }

        .about-hero .hero-subtitle {
            font-size: 1.5rem;
            color: var(--secondary-color);
            margin-bottom: 2rem;
            font-weight: 600;
            animation: fadeInUp 1s ease-out forwards 0.4s;
            opacity: 0;
        }

        .about-hero p {
            font-size: 1.15rem;
            max-width: 850px;
            margin: 0 auto 1.8rem;
            color: var(--dark-color);
            line-height: 1.9;
            animation: fadeInUp 1s ease-out forwards 0.6s;
            opacity: 0;
        }
        
        .about-hero .certification-badges {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2.5rem;
            animation: fadeInUp 1s ease-out forwards 0.8s;
            opacity: 0;
        }

        .about-hero .cert-badge {
            background-color: var(--primary-color);
            color: var(--white);
            padding: 0.7rem 1.5rem;
            border-radius: 25px;
            font-size: 0.95rem;
            font-weight: 500;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease, background-color 0.3s ease;
        }

        .about-hero .cert-badge:hover {
            transform: translateY(-3px);
            background-color: var(--secondary-color);
        }

        .contact-info-list {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 25px;
            list-style: none;
            padding: 0;
            margin-top: 3rem;
            animation: fadeInUp 1s ease-out forwards 1s;
            opacity: 0;
        }
        
        .contact-info-list li {
            display: flex;
            align-items: center;
            gap: 12px;
            color: var(--primary-color);
            font-weight: 600;
            font-size: 1.05rem;
        }
        
        .contact-info-list a {
            text-decoration: none;
            color: var(--primary-color);
            transition: color 0.3s ease;
        }
        
        .contact-info-list a:hover {
            color: var(--secondary-color);
        }
        
        .contact-info-list i {
            color: var(--secondary-color);
            font-size: 1.3rem;
        }

        /* Section General */
        .section {
            padding: 80px 0;
            background-color: var(--white);
            margin-bottom: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
        }
        
        .section:hover {
            box-shadow: var(--shadow-hover);
        }

        .section-title {
            font-family: 'Playfair Display', serif;
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3.5rem;
            color: var(--primary-color);
            position: relative;
            font-weight: 700;
        }

        .section-title::after {
            content: '';
            width: 100px;
            height: 5px;
            background-color: var(--accent-color);
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            bottom: -15px;
            border-radius: 3px;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
        }

        .skill-card {
            background: var(--light-color);
            padding: 2.5rem;
            border-radius: var(--border-radius);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border-left: 6px solid var(--secondary-color);
            text-align: left;
        }

        .skill-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.15);
        }

        .skill-icon {
            font-size: 3.5rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
            text-align: center;
        }

        .skill-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
            font-weight: 600;
            text-align: center;
        }

        .skill-description {
            color: var(--dark-color);
            line-height: 1.7;
            font-size: 1rem;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2.5rem;
        }

        .project-card {
            background: var(--white);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .project-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-hover);
        }

        .project-image {
            height: 220px;
            background: var(--gradient-primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent-color);
            font-size: 4rem;
            border-bottom: 3px solid var(--secondary-color);
        }

        .project-content {
            padding: 2rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .project-title {
            font-size: 1.6rem;
            margin-bottom: 0.8rem;
            color: var(--primary-color);
            font-weight: 700;
        }

        .project-description {
            color: var(--dark-color);
            margin-bottom: 1.5rem;
            line-height: 1.7;
            flex-grow: 1;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.7rem;
            margin-bottom: 1.5rem;
            margin-top: auto; /* Push tags to the bottom */
        }

        .tag {
            background: var(--light-color);
            color: var(--dark-color);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
            border: 1px solid #e0e0e0;
        }

        /* Contact Section */
        .contact.section {
            background: var(--gradient-primary);
            color: var(--white);
            padding: 80px 0;
            border-bottom: none;
            margin-bottom: 0;
            border-radius: 0;
        }
        
        .contact .section-title {
            color: var(--accent-color);
            margin-bottom: 4rem;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 4rem;
            align-items: center;
        }

        .contact-info-text p {
            font-size: 1.15rem;
            margin-bottom: 2.5rem;
            opacity: 0.9;
            line-height: 1.8;
        }

        .contact-details {
            list-style: none;
            padding: 0;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            font-weight: 500;
        }

        .contact-item i {
            font-size: 1.5rem;
            color: var(--secondary-color);
            width: 30px;
            text-align: center;
        }

        .contact-item a {
            color: var(--white);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-item a:hover {
            color: var(--accent-color);
        }

        .contact-form {
            background: rgba(255, 255, 255, 0.15);
            padding: 3rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .form-group {
            margin-bottom: 2rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.8rem;
            font-weight: 600;
            font-size: 1.1rem;
            color: var(--white);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 15px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            color: var(--dark-color);
            font-family: 'Montserrat', sans-serif;
            font-size: 1rem;
            box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            box-shadow: 0 0 0 3px var(--secondary-color), inset 0 1px 3px rgba(0, 0, 0, 0.1);
            background: var(--white);
        }

        .form-group textarea {
            height: 150px;
            resize: vertical;
        }

        .btn-submit {
            display: inline-block;
            background: var(--secondary-color);
            color: var(--white);
            padding: 15px 35px;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: var(--shadow);
        }

        .btn-submit:hover {
            background: var(--accent-color);
            transform: translateY(-3px);
            box-shadow: var(--shadow-hover);
        }

        /* Footer */
        .footer {
            background: var(--primary-color);
            color: rgba(255, 255, 255, 0.7);
            text-align: center;
            padding: 2.5rem 0;
            border-top: 2px solid var(--accent-color);
        }

        .footer p {
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
        }

        .social-link {
            color: var(--white);
            font-size: 1.8rem;
            transition: color 0.3s ease, transform 0.3s ease;
        }

        .social-link:hover {
            color: var(--secondary-color);
            transform: translateY(-3px);
        }

        /* Animations */
        @keyframes fadeInScale {
            from {
                opacity: 0;
                transform: scale(0.8) translateY(20px);
            }
            to {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .nav-links {
                gap: 1.5rem;
            }
            .about-hero h1 {
                font-size: 3.5rem;
            }
            .about-hero .hero-subtitle {
                font-size: 1.3rem;
            }
            .section-title {
                font-size: 2.5rem;
            }
            .contact-content {
                grid-template-columns: 1fr;
            }
            .contact-form {
                padding: 2.5rem;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            .mobile-menu {
                display: block;
            }
            .about-hero {
                padding: 80px 0 40px;
            }
            .about-hero h1 {
                font-size: 2.8rem;
            }
            .about-hero .hero-subtitle {
                font-size: 1.1rem;
            }
            .about-hero p {
                font-size: 1rem;
            }
            .section-title {
                font-size: 2rem;
                margin-bottom: 2.5rem;
            }
            .skills-grid, .projects-grid {
                grid-template-columns: 1fr;
            }
            .skill-card, .project-card {
                padding: 2rem;
            }
            .project-image {
                height: 180px;
                font-size: 3rem;
            }
            .contact.section {
                padding: 60px 0;
            }
            .contact-form {
                padding: 2rem;
            }
            .contact-info-list {
                flex-direction: column;
                gap: 15px;
            }
        }

        @media (max-width: 480px) {
            .logo {
                font-size: 1.5rem;
            }
            .about-hero .profile-pic {
                width: 180px;
                height: 180px;
            }
            .about-hero h1 {
                font-size: 2.2rem;
            }
            .about-hero .hero-subtitle {
                font-size: 1rem;
            }
            .about-hero p {
                font-size: 0.9rem;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .skill-card {
                padding: 1.5rem;
            }
            .skill-icon {
                font-size: 3rem;
            }
            .skill-title {
                font-size: 1.3rem;
            }
            .project-title {
                font-size: 1.4rem;
            }
            .tag {
                font-size: 0.8rem;
                padding: 0.4rem 0.8rem;
            }
            .contact-form {
                padding: 1.5rem;
            }
            .form-group input, .form-group textarea, .btn-submit {
                font-size: 0.95rem;
                padding: 12px;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="container">
            <div class="logo">Nneka Udoye</div>
            <nav>
                <ul class="nav-links">
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
            <div class="mobile-menu">
                <i class="fas fa-bars"></i>
            </div>
        </div>
    </header>

    <section id="about" class="about-hero">
        <div class="container">
            <img src="https://i.ibb.co/6y40F2S/Nneka-Udoye.jpg" alt="winifred Udoye - Senior Salesforce & FSL Administrator" class="profile-pic">
            <h1>Winifred Udoye</h1>
            <p class="hero-subtitle">Senior Salesforce Administrator & Field Service (FSL) Specialist</p>
            <p>
                Hello, I'm Winifred Udoye, a dedicated and certified Senior Salesforce Field Service Administrator based in Murrieta, California. With a robust background in leading digital transformations, my passion lies in architecting and implementing robust FSL solutions that not only meet business needs but also exceed operational expectations.
            </p>
            <p>
                I specialize in streamlining complex field service workflows, from intelligent work order automation and resource optimization to comprehensive mobile configurations and asset management. My commitment is to delivering solutions that boost productivity, improve customer satisfaction, and provide clear, actionable insights through advanced analytics.
            </p>
            <div class="certification-badges">
                <span class="cert-badge">Salesforce FSL Certified</span>
                <span class="cert-badge">Salesforce Administrator Certified</span>
                <span class="cert-badge">Project Management Professional (PMP)</span>
            </div>
            <ul class="contact-info-list">
                <li><i class="fas fa-map-marker-alt"></i> Murrieta, California, USA</li>
                <li><i class="fas fa-envelope"></i> <a href="mailto:winifred.udoye@gmail.com">winifred.udoye@gmail.com</a></li>
                <li><i class="fas fa-phone"></i> <a href="tel:+19514046278">+1 (951) 404-6278</a></li>
                <li><i class="fab fa-linkedin"></i> <a href="https://www.linkedin.com/in/salesforcewinnie/" target="_blank">LinkedIn Profile</a></li>
            </ul>
        </div>
    </section>

    <div class="container">
        <section id="skills" class="section">
            <h2 class="section-title">Skills & Expertise</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-icon"><i class="fas fa-cogs"></i></div>
                    <h3 class="skill-title">Automation & Optimization</h3>
                    <p class="skill-description">Expert in Work Orders & Service Appointments automation using Flows, scheduling policies, and optimization algorithms for maximum efficiency.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon"><i class="fas fa-users-cog"></i></div>
                    <h3 class="skill-title">Resource Management</h3>
                    <p class="skill-description">Advanced resource, skill, and territory management with operating hours configuration for optimal workforce allocation.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon"><i class="fas fa-calendar-alt"></i></div>
                    <h3 class="skill-title">Dispatcher Console</h3>
                    <p class="skill-description">Gantt optimization specialist with geolocation services and intelligent routing for enhanced dispatch operations.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon"><i class="fas fa-mobile-alt"></i></div>
                    <h3 class="skill-title">Mobile Configuration</h3>
                    <p class="skill-description">Mobile app customization expert including offline capabilities, quick actions, and screen flows for field technicians.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon"><i class="fas fa-tools"></i></div>
                    <h3 class="skill-title">Asset & Inventory Management</h3>
                    <p class="skill-description">Comprehensive asset management, maintenance plans, and parts/inventory tracking with returns processing systems.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon"><i class="fas fa-cloud"></i></div>
                    <h3 class="skill-title">Service Cloud Integration</h3>
                    <p class="skill-description">Seamless FSL integration with Service Cloud including Cases, Entitlements, Milestones, and Knowledge management.</p>
                </div>
            </div>
        </section>

        <section id="projects" class="section">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image"><i class="fas fa-robot"></i></div>
                    <div class="project-content">
                        <h3 class="project-title">Smart Scheduling System Implementation</h3>
                        <p class="project-description">Implemented intelligent work order automation with dynamic scheduling policies, reducing manual dispatch time by 65% and improving first-visit fix rates to 89% for a leading logistics company.</p>
                        <div class="project-tags">
                            <span class="tag">Salesforce FSL</span>
                            <span class="tag">Automation</span>
                            <span class="tag">Scheduling</span>
                            <span class="tag">Workflows</span>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image"><i class="fas fa-mobile-screen-button"></i></div>
                    <div class="project-content">
                        <h3 class="project-title">Offline-First Mobile Solution Development</h3>
                        <p class="project-description">Configured a comprehensive mobile solution with offline capabilities, custom quick actions, and screen flows, enabling 40% faster job completion in remote areas for field technicians.</p>
                        <div class="project-tags">
                            <span class="tag">FSL Mobile App</span>
                            <span class="tag">Offline Sync</span>
                            <span class="tag">Custom Flows</span>
                            <span class="tag">Field Service</span>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image"><i class="fas fa-map-marked-alt"></i></div>
                    <div class="project-content">
                        <h3 class="project-title">Advanced Geolocation Routing Engine</h3>
                        <p class="project-description">Built an advanced dispatcher console with Gantt optimization and real-time geolocation routing, cutting travel time by 30% and increasing daily job capacity by 25% for a national service provider.</p>
                        <div class="project-tags">
                            <span class="tag">Dispatcher Console</span>
                            <span class="tag">Route Optimization</span>
                            <span class="tag">Geolocation</span>
                            <span class="tag">Efficiency</span>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image"><i class="fas fa-handshake"></i></div>
                    <div class="project-content">
                        <h3 class="project-title">Unified Service Platform Integration</h3>
                        <p class="project-description">Seamlessly integrated FSL with Service Cloud, implementing a streamlined case-to-work-order flow with entitlements and SLA tracking, improving customer satisfaction by 45%.</p>
                        <div class="project-tags">
                            <span class="tag">Service Cloud</span>
                            <span class="tag">Integration</span>
                            <span class="tag">SLA Management</span>
                            <span class="tag">Customer Service</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <section id="contact" class="section contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <div class="contact-info-text">
                    <p>I am always open to discussing new projects, creative ideas, or opportunities to be part of your vision. Whether you have a question or just want to say hi, feel free to reach out!</p>
                    <ul class="contact-details">
                        <li class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Murrieta, California, USA</span>
                        </li>
                        <li class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <span><a href="mailto:winifred.udoye@gmail.com">winifred.udoye@gmail.com</a></span>
                        </li>
                        <li class="contact-item">
                            <i class="fas fa-phone"></i>
                            <span><a href="tel:+19514046278">+1 (951) 404-6278</a></span>
                        </li>
                        <li class="contact-item">
                            <i class="fab fa-linkedin"></i>
                            <span><a href="https://www.linkedin.com/in/salesforcewinnie/" target="_blank">linkedin.com/in/salesforcewinnie/</a></span>
                        </li>
                    </ul>
                </div>
                <form class="contact-form">
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" name="name" required placeholder="Your Name">
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required placeholder="Your Email">
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" required placeholder="Your Message"></textarea>
                    </div>
                    <button type="submit" class="btn-submit">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <footer class="footer">
        <div class="container">
            <p>&copy; 2023 Winifred Udoye. All rights reserved.</p>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/salesforcewinnie/" target="_blank" class="social-link"><i class="fab fa-linkedin-in"></i></a>
            </div>
        </div>
    </footer>
</body>
</html>
