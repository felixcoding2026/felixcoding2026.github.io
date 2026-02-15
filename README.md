
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Felix A. Quintana Jr. - IT Professional & Developer</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-primary: #0a0e1a;
            --bg-secondary: #131824;
            --accent: #00ff88;
            --accent-dim: #00cc6a;
            --text-primary: #e8f0ff;
            --text-secondary: #8a9ab0;
            --border: rgba(0, 255, 136, 0.2);
            --glow: rgba(0, 255, 136, 0.3);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'JetBrains Mono', monospace;
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        body::before {
            content: '';
            position: fixed;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(0, 255, 136, 0.05) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(0, 136, 255, 0.05) 0%, transparent 50%);
            animation: rotate 40s linear infinite;
            z-index: -1;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        body::after {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(0, 255, 136, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 255, 136, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            pointer-events: none;
            z-index: -1;
        }

        header {
            padding: 2rem 5%;
            border-bottom: 1px solid var(--border);
            position: sticky;
            top: 0;
            background: rgba(10, 14, 26, 0.8);
            backdrop-filter: blur(10px);
            z-index: 100;
            animation: slideDown 0.8s ease;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-family: 'Syne', sans-serif;
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--accent);
            text-shadow: 0 0 20px var(--glow);
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-size: 0.9rem;
            transition: all 0.3s ease;
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

        .nav-links a:hover {
            color: var(--accent);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        main {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 5%;
        }

        section {
            padding: 5rem 0;
            animation: fadeInUp 1s ease;
            animation-fill-mode: both;
        }

        section:nth-child(1) { animation-delay: 0.2s; }
        section:nth-child(2) { animation-delay: 0.4s; }
        section:nth-child(3) { animation-delay: 0.6s; }
        section:nth-child(4) { animation-delay: 0.8s; }

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

        h1, h2 {
            font-family: 'Syne', sans-serif;
            font-weight: 800;
        }

        h1 {
            font-size: clamp(2.5rem, 8vw, 5rem);
            line-height: 1.1;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--accent) 0%, #00ccff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        h2 {
            font-size: clamp(2rem, 5vw, 3rem);
            margin-bottom: 2rem;
            color: var(--accent);
            position: relative;
            display: inline-block;
        }

        h2::before {
            content: '// ';
            color: var(--text-secondary);
        }

        .hero {
            min-height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .hero-subtitle {
            font-size: clamp(1rem, 3vw, 1.5rem);
            color: var(--text-secondary);
            margin-bottom: 2rem;
            font-weight: 400;
        }

        .hero-description {
            max-width: 800px;
            font-size: 1.1rem;
            color: var(--text-secondary);
            margin-bottom: 3rem;
            line-height: 1.8;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2rem;
            border: 2px solid var(--accent);
            background: transparent;
            color: var(--accent);
            text-decoration: none;
            font-family: 'JetBrains Mono', monospace;
            font-weight: 700;
            font-size: 0.9rem;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            display: inline-block;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--accent);
            transition: left 0.3s ease;
            z-index: -1;
        }

        .btn:hover {
            color: var(--bg-primary);
        }

        .btn:hover::before {
            left: 0;
        }

        .btn-secondary {
            border-color: var(--text-secondary);
            color: var(--text-secondary);
        }

        .btn-secondary::before {
            background: var(--text-secondary);
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .stat-card {
            padding: 2rem;
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--accent), transparent);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.5s ease;
        }

        .stat-card::after {
            content: 'Click to view projects';
            position: absolute;
            bottom: 1rem;
            right: 1rem;
            font-size: 0.7rem;
            color: var(--accent);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .stat-card:hover::before {
            transform: scaleX(1);
        }

        .stat-card:hover::after {
            opacity: 1;
        }

        .stat-card:hover {
            border-color: var(--accent);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.1);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--accent);
            font-family: 'Syne', sans-serif;
        }

        .stat-label {
            color: var(--text-secondary);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(10, 14, 26, 0.95);
            backdrop-filter: blur(10px);
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal.active {
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: var(--bg-secondary);
            border: 2px solid var(--accent);
            max-width: 900px;
            width: 90%;
            max-height: 85vh;
            overflow-y: auto;
            padding: 3rem;
            position: relative;
            animation: slideUp 0.4s ease;
            box-shadow: 0 20px 60px rgba(0, 255, 136, 0.2);
        }

        @keyframes slideUp {
            from {
                transform: translateY(50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .modal-close {
            position: absolute;
            top: 1.5rem;
            right: 1.5rem;
            font-size: 2rem;
            color: var(--accent);
            cursor: pointer;
            background: none;
            border: none;
            transition: transform 0.3s ease;
            line-height: 1;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .modal-close:hover {
            transform: rotate(90deg);
        }

        .modal-title {
            font-family: 'Syne', sans-serif;
            font-size: 2rem;
            color: var(--accent);
            margin-bottom: 2rem;
            padding-right: 3rem;
        }

        .project-grid {
            display: grid;
            gap: 2rem;
        }

        .project-item {
            background: var(--bg-primary);
            border: 1px solid var(--border);
            padding: 1.5rem;
            transition: all 0.3s ease;
        }

        .project-item:hover {
            border-color: var(--accent);
            transform: translateX(10px);
        }

        .project-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1), rgba(0, 136, 255, 0.1));
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            border: 1px solid var(--border);
            position: relative;
        }

        .project-image-placeholder {
            font-size: 3rem;
            z-index: 1;
        }

        /* Hide placeholder when image is loaded */
        .project-image[style*="background-image: url('http"]:not([style*="url('')"]) .project-image-placeholder,
        .project-image[style*="background-image: url('images"]:not([style*="url('')"]) .project-image-placeholder,
        .project-image[style*="background-image: url('assets"]:not([style*="url('')"]) .project-image-placeholder,
        .project-image[style*="background-image: url('./"]:not([style*="url('')"]) .project-image-placeholder {
            display: none;
        }

        .project-name {
            font-family: 'Syne', sans-serif;
            font-size: 1.3rem;
            color: var(--text-primary);
            margin-bottom: 0.5rem;
        }

        .project-description {
            color: var(--text-secondary);
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-tag {
            padding: 0.3rem 0.8rem;
            background: rgba(0, 255, 136, 0.1);
            border: 1px solid var(--border);
            color: var(--accent);
            font-size: 0.75rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-category {
            background: var(--bg-secondary);
            padding: 2rem;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            border-color: var(--accent);
            box-shadow: 0 0 30px rgba(0, 255, 136, 0.1);
        }

        .skill-category h3 {
            font-family: 'Syne', sans-serif;
            color: var(--accent);
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            font-weight: 700;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }

        .skill-tag {
            padding: 0.5rem 1rem;
            background: rgba(0, 255, 136, 0.1);
            border: 1px solid var(--border);
            color: var(--text-primary);
            font-size: 0.85rem;
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: var(--accent);
            color: var(--bg-primary);
            transform: translateY(-2px);
        }

        .experience-timeline {
            position: relative;
            margin-top: 3rem;
        }

        .experience-item {
            margin-bottom: 3rem;
            padding-left: 3rem;
            position: relative;
            border-left: 2px solid var(--border);
            transition: all 0.3s ease;
        }

        .experience-item::before {
            content: '';
            position: absolute;
            left: -6px;
            top: 0;
            width: 10px;
            height: 10px;
            background: var(--accent);
            border-radius: 50%;
            box-shadow: 0 0 20px var(--glow);
        }

        .experience-item:hover {
            border-left-color: var(--accent);
        }

        .experience-header {
            margin-bottom: 1rem;
        }

        .experience-title {
            font-size: 1.3rem;
            color: var(--text-primary);
            font-weight: 700;
            font-family: 'Syne', sans-serif;
        }

        .experience-company {
            color: var(--accent);
            font-size: 1.1rem;
            margin-top: 0.3rem;
        }

        .experience-period {
            color: var(--text-secondary);
            font-size: 0.9rem;
            margin-top: 0.3rem;
        }

        .experience-description {
            color: var(--text-secondary);
            line-height: 1.8;
            margin-top: 1rem;
        }

        .experience-description ul {
            list-style: none;
            margin-top: 1rem;
        }

        .experience-description li {
            padding-left: 1.5rem;
            margin-bottom: 0.8rem;
            position: relative;
        }

        .experience-description li::before {
            content: '▹';
            position: absolute;
            left: 0;
            color: var(--accent);
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            margin-top: 3rem;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            border-color: var(--accent);
            transform: translateX(10px);
        }

        .contact-icon {
            width: 24px;
            height: 24px;
            fill: var(--accent);
        }

        .contact-link {
            color: var(--text-primary);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-link:hover {
            color: var(--accent);
        }

        .certifications {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 3rem;
        }

        .cert-item {
            padding: 1.5rem;
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            border-left: 4px solid var(--accent);
            transition: all 0.3s ease;
        }

        .cert-item:hover {
            transform: translateX(10px);
            box-shadow: 0 5px 20px rgba(0, 255, 136, 0.1);
        }

        .cert-item h4 {
            color: var(--accent);
            margin-bottom: 0.5rem;
            font-family: 'Syne', sans-serif;
        }

        .cert-item p {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        footer {
            text-align: center;
            padding: 3rem 5%;
            border-top: 1px solid var(--border);
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .contact-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .stats {
                grid-template-columns: 1fr;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .modal-content {
                padding: 2rem 1.5rem;
            }
        }

        .scroll-progress {
            position: fixed;
            top: 0;
            left: 0;
            width: 0%;
            height: 3px;
            background: linear-gradient(90deg, var(--accent), #00ccff);
            z-index: 1000;
            transition: width 0.1s ease;
        }
    </style>
</head>
<body>
    <div class="scroll-progress" id="scrollProgress"></div>

    <header>
        <nav>
            <div class="logo">FAQ.dev</div>
            <ul class="nav-links">
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#certifications">Certifications</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="hero" id="about">
            <h1>FELIX A. QUINTANA JR.</h1>
            <p class="hero-subtitle">IT Professional | Technician | Developer</p>
            <p class="hero-description">
                Results-driven IT professional with expertise in software development, hardware troubleshooting, and technical training. Certified Java programmer who has taught 500+ students across multiple programming languages and maintained 1,000+ mobile devices and critical systems. Experienced in government IT operations and delivering efficient solutions in fast-paced environments.
            </p>
            <div class="cta-buttons">
                <a href="#contact" class="btn">Get In Touch</a>
                <a href="https://github.com/FelixQ2024/JAVA" class="btn btn-secondary" target="_blank">View GitHub</a>
            </div>

            <div class="stats">
                <div class="stat-card" onclick="openModal('students')">
                    <div class="stat-number">500+</div>
                    <div class="stat-label">Students Taught</div>
                </div>
                <div class="stat-card" onclick="openModal('devices')">
                    <div class="stat-number">1,000+</div>
                    <div class="stat-label">Devices Repaired</div>
                </div>
                <div class="stat-card" onclick="openModal('iot')">
                    <div class="stat-number">30+</div>
                    <div class="stat-label">IoT Projects</div>
                </div>
                <div class="stat-card" onclick="openModal('vcms')">
                    <div class="stat-number">100+</div>
                    <div class="stat-label">VCMs Supported</div>
                </div>
            </div>
        </section>

        <section id="skills">
            <h2>Technical Arsenal</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3>Programming Languages</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Java</span>
                        <span class="skill-tag">C</span>
                        <span class="skill-tag">C++</span>
                        <span class="skill-tag">PHP</span>
                        <span class="skill-tag">JavaScript</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Web Technologies</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">HTML</span>
                        <span class="skill-tag">CSS</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">XML</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>IoT & Embedded Systems</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Arduino</span>
                        <span class="skill-tag">Sensor Integration</span>
                        <span class="skill-tag">Automation</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Databases</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">MySQL</span>
                        <span class="skill-tag">MongoDB</span>
                        <span class="skill-tag">Firebase</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Development Tools</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">VS Code</span>
                        <span class="skill-tag">Eclipse</span>
                        <span class="skill-tag">Visual Studio</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Hardware & Systems</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">PC Assembly</span>
                        <span class="skill-tag">iOS/Android</span>
                        <span class="skill-tag">Device Repair</span>
                        <span class="skill-tag">Troubleshooting</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="experience">
            <h2>Work Experience</h2>
            <div class="experience-timeline">
                <div class="experience-item">
                    <div class="experience-header">
                        <div class="experience-title">Desktop, Laptop, Cellphone Technician</div>
                        <div class="experience-company">TECHLIX MOBILE REPAIR</div>
                        <div class="experience-period">Jan 2023 – Present</div>
                    </div>
                    <div class="experience-description">
                        <ul>
                            <li>Diagnosed, repaired, and maintained 1,000+ phones, tablets, desktops, and peripherals</li>
                            <li>Performed installations, upgrades, and troubleshooting to ensure optimal system performance</li>
                            <li>Delivered technical support and maintained accurate service records</li>
                            <li>Improved user satisfaction and streamlined documentation processes</li>
                        </ul>
                    </div>
                </div>

                <div class="experience-item">
                    <div class="experience-header">
                        <div class="experience-title">Freelance Developer & IT Consultant</div>
                        <div class="experience-company">VARIOUS CLIENTS</div>
                        <div class="experience-period">April 2020 – Present</div>
                    </div>
                    <div class="experience-description">
                        <ul>
                            <li>Completed 30+ IoT and Arduino-based automation projects for clients across various industries</li>
                            <li>Perform GIS data annotation and geospatial data processing for mapping projects</li>
                            <li>Successfully recovered ₱1M+ in cryptocurrency and NFT assets</li>
                            <li>Provide account recovery services for social media platforms and digital payment systems</li>
                            <li>Deliver custom technical solutions including hardware integration and IT consulting</li>
                        </ul>
                    </div>
                </div>

                <div class="experience-item">
                    <div class="experience-header">
                        <div class="experience-title">IT Instructor</div>
                        <div class="experience-company">COLEGIO DE MONTALBAN</div>
                        <div class="experience-period">Jan 2021 – Sept 2023</div>
                    </div>
                    <div class="experience-description">
                        <ul>
                            <li>Taught 500+ students across multiple programming disciplines</li>
                            <li>Delivered courses in C, C++, Visual Basic, Java, HTML, CSS, JavaScript, PHP, and XML</li>
                            <li>Instructed computer networking, DBMS fundamentals, and web development technologies</li>
                            <li>Maintained high student engagement and course completion rates</li>
                        </ul>
                    </div>
                </div>

                <div class="experience-item">
                    <div class="experience-header">
                        <div class="experience-title">Election Job Order</div>
                        <div class="experience-company">COMMISSION ON ELECTIONS (COMELEC)</div>
                        <div class="experience-period">Jan 2022 – July 2022</div>
                    </div>
                    <div class="experience-description">
                        <ul>
                            <li>Trained 200+ Electoral Board members for National and Local Elections</li>
                            <li>Assisted the Election Officer in conducting preparedness training sessions</li>
                            <li>Monitored 100+ Vote Counting Machines (VCMs) on Election Day</li>
                            <li>Promptly addressed technical issues to maintain smooth voting operations</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="certifications">
            <h2>Certifications & Achievements</h2>
            <div class="certifications">
                <div class="cert-item">
                    <h4>TESDA Java Programming NC III</h4>
                    <p>Eastern Star Institute of Science and Technology (2024)</p>
                </div>
                <div class="cert-item">
                    <h4>Masters in Information Technology</h4>
                    <p>Our Lady of Fatima University - 24 Units (2021-2022)</p>
                </div>
                <div class="cert-item">
                    <h4>Bachelor of Science in IT</h4>
                    <p>Colegio de Montalban - Magna Cum Laude (2016-2020)</p>
                </div>
                <div class="cert-item">
                    <h4>PD 907 Eligibility</h4>
                    <p>Latin Honor (2020)</p>
                </div>
                <div class="cert-item">
                    <h4>Civil Service Professional</h4>
                    <p>CSE-PPT (2018)</p>
                </div>
                <div class="cert-item">
                    <h4>Academic Excellence Awardee</h4>
                    <p>2020</p>
                </div>
                <div class="cert-item">
                    <h4>I.S.I.T.E Awardee</h4>
                    <p>2020</p>
                </div>
                <div class="cert-item">
                    <h4>Best Capstone Project</h4>
                    <p>"Farm Bot" Documentation (2020)</p>
                </div>
                <div class="cert-item">
                    <h4>Dean's & President's Lister</h4>
                    <p>2016-2020</p>
                </div>
            </div>
        </section>

        <section id="contact">
            <h2>Let's Connect</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <div class="contact-item">
                        <svg class="contact-icon" viewBox="0 0 24 24" fill="currentColor">
                            <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                        </svg>
                        <a href="mailto:felixquintana.work@gmail.com" class="contact-link">felixquintana.work@gmail.com</a>
                    </div>

                    <div class="contact-item">
                        <svg class="contact-icon" viewBox="0 0 24 24" fill="currentColor">
                            <path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/>
                        </svg>
                        <a href="tel:+639652633112" class="contact-link">0965 263 3112</a>
                    </div>

                    <div class="contact-item">
                        <svg class="contact-icon" viewBox="0 0 24 24" fill="currentColor">
                            <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                        </svg>
                        <a href="https://github.com/FelixQ2024/JAVA" class="contact-link" target="_blank">github.com/FelixQ2024/JAVA</a>
                    </div>

                    <div class="contact-item">
                        <svg class="contact-icon" viewBox="0 0 24 24" fill="currentColor">
                            <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                        </svg>
                        <a href="https://linkedin.com/in/felixquintanajr" class="contact-link" target="_blank">linkedin.com/in/felixquintanajr</a>
                    </div>

                    <div class="contact-item">
                        <svg class="contact-icon" viewBox="0 0 24 24" fill="currentColor">
                            <path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/>
                        </svg>
                        <span class="contact-link">Rodriguez, Rizal, Philippines</span>
                    </div>
                </div>

                <div>
                    <p style="color: var(--text-secondary); line-height: 1.8;">
                        I'm always open to discussing new opportunities, collaborations, or interesting projects. Whether you need technical expertise, development services, or IT consulting, feel free to reach out. Let's build something great together.
                    </p>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 Felix A. Quintana Jr. Built with passion for technology.</p>
    </footer>

    <!-- Modals -->
    <div id="studentsModal" class="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal('students')">&times;</button>
            <h2 class="modal-title">Teaching Portfolio</h2>
            <div class="project-grid">
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url('images/student.png'); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">💻</span>
                    </div>
                    <h3 class="project-name">Programming Fundamentals Course</h3>
                    <p class="project-description">
                        Taught C, C++, and Java programming to 200+ students at Colegio de Montalban. Developed comprehensive curriculum covering data structures, algorithms, and object-oriented programming principles.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">C/C++</span>
                        <span class="tech-tag">Java</span>
                        <span class="tech-tag">OOP</span>
                    </div>
                </div>
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url('images/student.png'); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">🌐</span>
                    </div>
                    <h3 class="project-name">Web Development Track</h3>
                    <p class="project-description">
                        Instructed 150+ students in HTML, CSS, JavaScript, PHP, and XML. Students built responsive websites and dynamic web applications, with 95% course completion rate.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">HTML/CSS</span>
                        <span class="tech-tag">JavaScript</span>
                        <span class="tech-tag">PHP</span>
                    </div>
                </div>
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url('images/student.png'); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">🗄️</span>
                    </div>
                    <h3 class="project-name">Database Management Systems</h3>
                    <p class="project-description">
                        Delivered DBMS fundamentals and SQL programming to 150+ students. Covered database design, normalization, queries, and practical implementations using MySQL and MongoDB.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">MySQL</span>
                        <span class="tech-tag">MongoDB</span>
                        <span class="tech-tag">SQL</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="devicesModal" class="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal('devices')">&times;</button>
            <h2 class="modal-title">Device Repair Expertise</h2>
            <div class="project-grid">
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">📱</span>
                    </div>
                    <h3 class="project-name">Mobile Device Repairs</h3>
                    <p class="project-description">
                        Specialized in iPhone and Android repairs including screen replacements, battery replacements, charging port repairs, and software troubleshooting. Successfully repaired 600+ mobile devices with 98% success rate.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">iOS</span>
                        <span class="tech-tag">Android</span>
                        <span class="tech-tag">Hardware</span>
                    </div>
                </div>
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">💻</span>
                    </div>
                    <h3 class="project-name">Laptop & Desktop Repairs</h3>
                    <p class="project-description">
                        Expertise in diagnosing and repairing motherboard issues, RAM upgrades, SSD installations, thermal paste replacement, and OS reinstallations. Serviced 300+ computers at TECHLIX Mobile Repair.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">PC Assembly</span>
                        <span class="tech-tag">Diagnostics</span>
                        <span class="tech-tag">Upgrades</span>
                    </div>
                </div>
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">🔧</span>
                    </div>
                    <h3 class="project-name">Peripheral & Accessory Repairs</h3>
                    <p class="project-description">
                        Fixed tablets, smartwatches, gaming peripherals, and computer accessories. Maintained detailed service records and customer satisfaction tracking system improving retention by 40%.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">Tablets</span>
                        <span class="tech-tag">Peripherals</span>
                        <span class="tech-tag">Testing</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="iotModal" class="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal('iot')">&times;</button>
            <h2 class="modal-title">IoT & Arduino Projects</h2>
            <div class="project-grid">
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">🤖</span>
                    </div>
                    <h3 class="project-name">Farm Bot - Award-Winning Capstone</h3>
                    <p class="project-description">
                        Best Capstone Project (2020). Automated farming system using Arduino with soil moisture sensors, automatic irrigation, and mobile app monitoring. Reduced water usage by 40% in test fields.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">Arduino</span>
                        <span class="tech-tag">Sensors</span>
                        <span class="tech-tag">Mobile App</span>
                        <span class="tech-tag">IoT</span>
                    </div>
                </div>
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">🏠</span>
                    </div>
                    <h3 class="project-name">Smart Home Automation Systems</h3>
                    <p class="project-description">
                        Developed 15+ home automation projects for clients including voice-controlled lighting, automated security systems, temperature monitoring, and energy management solutions using ESP8266/ESP32.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">ESP32</span>
                        <span class="tech-tag">Home Automation</span>
                        <span class="tech-tag">WiFi</span>
                    </div>
                </div>
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">📊</span>
                    </div>
                    <h3 class="project-name">Environmental Monitoring Systems</h3>
                    <p class="project-description">
                        Created real-time environmental monitoring stations measuring temperature, humidity, air quality, and noise levels. Data logged to Firebase with web dashboard for visualization and alerts.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">Sensors</span>
                        <span class="tech-tag">Firebase</span>
                        <span class="tech-tag">Data Logging</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="vcmsModal" class="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal('vcms')">&times;</button>
            <h2 class="modal-title">COMELEC Election Support</h2>
            <div class="project-grid">
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">🗳️</span>
                    </div>
                    <h3 class="project-name">Vote Counting Machine (VCM) Management</h3>
                    <p class="project-description">
                        Monitored and maintained 100+ Vote Counting Machines during the 2022 National and Local Elections. Provided real-time technical support ensuring 99.5% uptime on election day, critical for democratic process.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">Hardware Support</span>
                        <span class="tech-tag">Troubleshooting</span>
                        <span class="tech-tag">Critical Systems</span>
                    </div>
                </div>
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">👥</span>
                    </div>
                    <h3 class="project-name">Electoral Board Training Program</h3>
                    <p class="project-description">
                        Trained 200+ Electoral Board members on VCM operation, troubleshooting procedures, and election day protocols. Developed training materials and conducted hands-on sessions ensuring smooth election operations.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">Training</span>
                        <span class="tech-tag">Documentation</span>
                        <span class="tech-tag">Leadership</span>
                    </div>
                </div>
                <div class="project-item">
                    <!-- 📸 ADD YOUR IMAGE URL BELOW - Replace the empty quotes '' with your image URL -->
                    <div class="project-image" style="background-image: url(''); background-size: cover; background-position: center;">
                        <span class="project-image-placeholder">⚡</span>
                    </div>
                    <h3 class="project-name">Rapid Response Technical Support</h3>
                    <p class="project-description">
                        Provided emergency technical support during voting hours, resolving printer issues, connectivity problems, and hardware malfunctions. Average response time under 5 minutes, minimizing voter disruption.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">Emergency Response</span>
                        <span class="tech-tag">Problem Solving</span>
                        <span class="tech-tag">Government IT</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Scroll Progress Bar
        window.addEventListener('scroll', () => {
            const scrollProgress = document.getElementById('scrollProgress');
            const scrollTotal = document.documentElement.scrollHeight - window.innerHeight;
            const scrollPosition = window.pageYOffset;
            const progress = (scrollPosition / scrollTotal) * 100;
            scrollProgress.style.width = progress + '%';
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Modal functions
        function openModal(type) {
            const modal = document.getElementById(type + 'Modal');
            if (modal) {
                modal.classList.add('active');
                document.body.style.overflow = 'hidden';
            }
        }

        function closeModal(type) {
            const modal = document.getElementById(type + 'Modal');
            if (modal) {
                modal.classList.remove('active');
                document.body.style.overflow = 'auto';
            }
        }

        // Close modal when clicking outside
        document.querySelectorAll('.modal').forEach(modal => {
            modal.addEventListener('click', function(e) {
                if (e.target === this) {
                    this.classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            });
        });

        // Close modal with Escape key
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                document.querySelectorAll('.modal.active').forEach(modal => {
                    modal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                });
            }
        });
    </script>
</body>
</html>
