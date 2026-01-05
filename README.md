<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Coen Howerter | Astrobiology & Astrophysics</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-dark: #0a0e27;
            --secondary-dark: #1a1f3a;
            --accent-blue: #4a90e2;
            --accent-light: #7ab8f5;
            --text-primary: #e8eef2;
            --text-secondary: #b8c5d0;
            --border-color: rgba(74, 144, 226, 0.2);
        }

        body {
            font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;
            line-height: 1.7;
            color: var(--text-primary);
            background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 50%, #0f1419 100%);
            min-height: 100vh;
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 4s ease-in-out infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.2; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.2); }
        }

        header {
            background: rgba(10, 14, 39, 0.95);
            backdrop-filter: blur(20px);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid var(--border-color);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
        }

        .header-content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--accent-light);
            letter-spacing: -0.5px;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 2.5rem;
        }

        nav a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            transition: color 0.3s;
            position: relative;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-blue);
            transition: width 0.3s;
        }

        nav a:hover {
            color: var(--accent-light);
        }

        nav a:hover::after {
            width: 100%;
        }

        .hero {
            position: relative;
            z-index: 1;
            padding: 6rem 2rem;
            text-align: center;
            background: linear-gradient(180deg, rgba(10, 14, 39, 0) 0%, rgba(26, 31, 58, 0.3) 100%);
        }

        .hero-content {
            max-width: 900px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            background: linear-gradient(135deg, #7ab8f5 0%, #4a90e2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero .subtitle {
            font-size: 1.5rem;
            color: var(--text-secondary);
            margin-bottom: 1rem;
        }

        .hero .tagline {
            font-size: 1.1rem;
            color: var(--text-secondary);
            max-width: 700px;
            margin: 0 auto;
            line-height: 1.8;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 1;
        }

        section {
            background: rgba(26, 31, 58, 0.6);
            backdrop-filter: blur(15px);
            margin: 3rem 0;
            padding: 3rem;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
        }

        h2 {
            color: var(--accent-light);
            margin-bottom: 2rem;
            font-size: 2.2rem;
            font-weight: 600;
            position: relative;
            padding-bottom: 1rem;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 3px;
            background: var(--accent-blue);
        }

        h3 {
            color: var(--accent-light);
            margin-top: 2rem;
            margin-bottom: 1rem;
            font-size: 1.4rem;
            font-weight: 600;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: 3rem;
            align-items: start;
        }

        .headshot-container {
            position: relative;
        }

        .headshot {
            width: 100%;
            aspect-ratio: 1;
            border-radius: 12px;
            object-fit: cover;
            border: 3px solid var(--accent-blue);
            box-shadow: 0 12px 40px rgba(74, 144, 226, 0.3);
            background: rgba(26, 31, 58, 0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        .about-content p {
            margin-bottom: 1.2rem;
            color: var(--text-secondary);
            font-size: 1.05rem;
        }

        .credentials {
            margin-top: 2rem;
            padding: 1.5rem;
            background: rgba(15, 20, 40, 0.6);
            border-radius: 10px;
            border-left: 3px solid var(--accent-blue);
        }

        .credentials h4 {
            color: var(--accent-light);
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        .credentials p {
            color: var(--text-secondary);
            margin: 0.3rem 0;
        }

        .research-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .research-card {
            background: rgba(15, 20, 40, 0.6);
            padding: 2rem;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .research-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--accent-blue), var(--accent-light));
            transform: scaleX(0);
            transition: transform 0.4s;
        }

        .research-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 35px rgba(74, 144, 226, 0.25);
            border-color: var(--accent-blue);
        }

        .research-card:hover::before {
            transform: scaleX(1);
        }

        .research-card h3 {
            margin-top: 0;
            font-size: 1.3rem;
        }

        .research-card p {
            color: var(--text-secondary);
            font-size: 0.98rem;
        }

        .projects-category {
            margin-bottom: 2.5rem;
        }

        .projects-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.2rem;
            margin-top: 1rem;
        }

        .project-item {
            background: rgba(15, 20, 40, 0.4);
            padding: 1.2rem;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            transition: all 0.3s;
        }

        .project-item:hover {
            background: rgba(15, 20, 40, 0.7);
            border-color: var(--accent-blue);
            transform: translateX(5px);
        }

        .project-item a {
            color: var(--accent-light);
            text-decoration: none;
            font-weight: 500;
            display: block;
        }

        .project-item a:hover {
            color: var(--accent-blue);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-category h4 {
            color: var(--accent-light);
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }

        .skill-tag {
            background: rgba(74, 144, 226, 0.15);
            color: var(--accent-light);
            padding: 0.6rem 1.2rem;
            border-radius: 20px;
            font-size: 0.9rem;
            border: 1px solid rgba(74, 144, 226, 0.3);
            transition: all 0.3s;
        }

        .skill-tag:hover {
            background: rgba(74, 144, 226, 0.25);
            border-color: var(--accent-blue);
            transform: translateY(-2px);
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .contact-card {
            background: rgba(15, 20, 40, 0.5);
            padding: 1.5rem;
            border-radius: 10px;
            border: 1px solid var(--border-color);
        }

        .contact-card h4 {
            color: var(--accent-light);
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin: 0.8rem 0;
            color: var(--text-secondary);
        }

        .contact-item strong {
            color: var(--text-primary);
            min-width: 80px;
        }

        .contact-item a {
            color: var(--accent-light);
            text-decoration: none;
            transition: color 0.3s;
        }

        .contact-item a:hover {
            color: var(--accent-blue);
            text-decoration: underline;
        }

        footer {
            background: rgba(10, 14, 39, 0.95);
            text-align: center;
            padding: 2.5rem 2rem;
            margin-top: 4rem;
            border-top: 1px solid var(--border-color);
            position: relative;
            z-index: 1;
        }

        footer p {
            color: var(--text-secondary);
            font-size: 0.95rem;
        }

        @media (max-width: 1024px) {
            .about-grid {
                grid-template-columns: 1fr;
            }

            .headshot {
                max-width: 300px;
                margin: 0 auto;
            }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .subtitle {
                font-size: 1.2rem;
            }

            nav ul {
                gap: 1.5rem;
            }

            section {
                padding: 2rem 1.5rem;
            }

            h2 {
                font-size: 1.8rem;
            }

            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>

    <header>
        <div class="header-content">
            <div class="logo">Coen Howerter</div>
            <nav>
                <ul>
                    <li><a href="#about">About</a></li>
                    <li><a href="#research">Research</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <div class="hero">
        <div class="hero-content">
            <h1>Coen Howerter</h1>
            <p class="subtitle">Astrobiology & Astrophysics</p>
            <p class="tagline">Exploring the intersection of life and the cosmos through interdisciplinary research in planetary habitability, biosignatures, and astrobiology</p>
        </div>
    </div>

    <div class="container">
        <section id="about">
            <h2>About Me</h2>
            <div class="about-grid">
                <div class="headshot-container">
                    <div class="headshot">
                        <!-- Replace the src below with your actual headshot URL -->
                        <img src="YOUR_HEADSHOT_URL_HERE" alt="Coen Howerter" style="width: 100%; height: 100%; object-fit: cover; border-radius: 12px;" onerror="this.parentElement.innerHTML='Add Your Photo<br>Replace URL Above'">
                    </div>
                    <div class="credentials">
                        <h4>Education</h4>
                        <p><strong>Florida Institute of Technology</strong></p>
                        <p>B.S. Astrobiology (Expected)</p>
                        <p>Minor: Physics</p>
                    </div>
                </div>
                <div class="about-content">
                    <p>I am an undergraduate student at Florida Institute of Technology pursuing a Bachelor's degree in Astrobiology with a minor in Physics. My passion lies at the intersection of biology, chemistry, and astrophysics, where I investigate the fundamental questions about life's origins and its potential distribution throughout the universe.</p>
                    
                    <p>My academic journey has equipped me with a unique interdisciplinary perspective, combining rigorous training in molecular biology, organic chemistry, and planetary science. I'm particularly fascinated by extremophile organisms on Earth and their implications for life in extreme extraterrestrial environments.</p>
                    
                    <p>Through hands-on research projects and computational modeling, I've developed skills in spectroscopy, astrobiology simulation, and data analysis. My goal is to contribute to humanity's understanding of habitability beyond Earth and to participate in the search for biosignatures on exoplanets and within our own solar system.</p>
                    
                    <p>Outside of academics, I enjoy programming in Python, developing scientific tools, and staying current with the latest discoveries in planetary exploration and astrobiology missions.</p>
                </div>
            </div>
        </section>

        <section id="research">
            <h2>Research Interests</h2>
            <div class="research-grid">
                <div class="research-card">
                    <h3>Planetary Habitability</h3>
                    <p>Investigating the conditions necessary for life to emerge and persist on planetary bodies, including the study of habitable zones, atmospheric composition, and subsurface oceans in moons like Europa and Enceladus.</p>
                </div>
                <div class="research-card">
                    <h3>Extremophile Biology</h3>
                    <p>Studying organisms that thrive in extreme conditions on Earth as analogs for potential extraterrestrial life, with focus on thermophiles, psychrophiles, and organisms surviving in high-radiation environments.</p>
                </div>
                <div class="research-card">
                    <h3>Biosignature Detection</h3>
                    <p>Developing methodologies for identifying chemical and spectroscopic signatures of life in exoplanet atmospheres and on surfaces of solar system bodies through remote sensing and in-situ analysis.</p>
                </div>
                <div class="research-card">
                    <h3>Prebiotic Chemistry</h3>
                    <p>Exploring the chemical pathways that could lead from simple organic molecules to self-replicating systems, including RNA world hypothesis and hydrothermal vent chemistry relevant to life's origins.</p>
                </div>
            </div>
        </section>

        <section id="projects">
            <h2>Projects</h2>
            
            <div class="projects-category">
                <h3>Biology & Chemistry</h3>
                <div class="projects-list">
                    <div class="project-item">
                        <a href="#" target="_blank">Extremophile Cultivation Study</a>
                    </div>
                    <div class="project-item">
                        <a href="#" target="_blank">Organic Molecule Analysis</a>
                    </div>
                    <div class="project-item">
                        <a href="#" target="_blank">Biosignature Research</a>
                    </div>
                    <div class="project-item">
                        <a href="#" target="_blank">Prebiotic Chemistry Simulation</a>
                    </div>
                </div>
            </div>
            
            <div class="projects-category">
                <h3>Physics & Astronomy</h3>
                <div class="projects-list">
                    <div class="project-item">
                        <a href="#" target="_blank">Exoplanet Atmosphere Modeling</a>
                    </div>
                    <div class="project-item">
                        <a href="#" target="_blank">Spectroscopy Analysis</a>
                    </div>
                    <div class="project-item">
                        <a href="#" target="_blank">Habitable Zone Calculations</a>
                    </div>
                    <div class="project-item">
                        <a href="#" target="_blank">Planetary Science Research</a>
                    </div>
                </div>
            </div>
            
            <div class="projects-category">
                <h3>Python & Computational</h3>
                <div class="projects-list">
                    <div class="project-item">
                        <a href="https://github.com/coenhowerter/LibraryPy" target="_blank">LibraryPy</a>
                    </div>
                    <div class="project-item">
                        <a href="#" target="_blank">Astrobiology Data Tools</a>
                    </div>
                    <div class="project-item">
                        <a href="#" target="_blank">Spectral Analysis Package</a>
                    </div>
                </div>
            </div>
        </section>

        <section id="skills">
            <h2>Skills & Expertise</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h4>Laboratory Techniques</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">Microbiology</span>
                        <span class="skill-tag">Spectroscopy</span>
                        <span class="skill-tag">Cell Culture</span>
                        <span class="skill-tag">PCR</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h4>Computational</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">Data Analysis</span>
                        <span class="skill-tag">Scientific Computing</span>
                        <span class="skill-tag">Modeling</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h4>Analytical</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">Statistical Analysis</span>
                        <span class="skill-tag">Research Design</span>
                        <span class="skill-tag">Literature Review</span>
                        <span class="skill-tag">Technical Writing</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h4>Scientific Focus</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">Astrobiology</span>
                        <span class="skill-tag">Planetary Science</span>
                        <span class="skill-tag">Biochemistry</span>
                        <span class="skill-tag">Astrophysics</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact">
            <h2>Contact</h2>
            <div class="contact-grid">
                <div class="contact-card">
                    <h4>Get In Touch</h4>
                    <div class="contact-item">
                        <strong>Email:</strong>
                        <a href="mailto:coenhowerter@gmail.com">coenhowerter@gmail.com</a>
                    </div>
                    <div class="contact-item">
                        <strong>Phone:</strong>
                        <a href="tel:+15616138675">+1 (561) 613-8675</a>
                    </div>
                </div>
                <div class="contact-card">
                    <h4>Professional Links</h4>
                    <div class="contact-item">
                        <strong>LinkedIn:</strong>
                        <a href="https://www.linkedin.com/in/coen-howerter/" target="_blank">linkedin.com/in/coen-howerter</a>
                    </div>
                    <div class="contact-item">
                        <strong>GitHub:</strong>
                        <a href="https://github.com/coenhowerter" target="_blank">github.com/coenhowerter</a>
                    </div>
                </div>
                <div class="contact-card">
                    <h4>Institution</h4>
                    <div class="contact-item">
                        <strong>University:</strong>
                        <span>Florida Institute of Technology</span>
                    </div>
                    <div class="contact-item">
                        <strong>Location:</strong>
                        <span>Melbourne, Florida</span>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <footer>
        <p>&copy; 2025 Coen Howerter | Astrobiology & Astrophysics Research | Florida Institute of Technology</p>
    </footer>

    <script>
        // Create animated star field
        const starsContainer = document.getElementById('stars');
        const starCount = 150;
        
        for (let i = 0; i < starCount; i++) {
            const star = document.createElement('div');
            star.className = 'star';
            star.style.left = Math.random() * 100 + '%';
            star.style.top = Math.random() * 100 + '%';
            const size = Math.random() * 2 + 0.5;
            star.style.width = size + 'px';
            star.style.height = size + 'px';
            star.style.animationDelay = Math.random() * 4 + 's';
            star.style.animationDuration = (Math.random() * 3 + 3) + 's';
            starsContainer.appendChild(star);
        }

        // Smooth scrolling for navigation
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                const headerOffset = 80;
                const elementPosition = target.getBoundingClientRect().top;
                const offsetPosition = elementPosition + window.pageYOffset - headerOffset;

                window.scrollTo({
                    top: offsetPosition,
                    behavior: 'smooth'
                });
            });
        });

        // Add scroll animation for sections
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('section').forEach(section => {
            section.style.opacity = '0';
            section.style.transform = 'translateY(20px)';
            section.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(section);
        });
    </script>
</body>
</html>
