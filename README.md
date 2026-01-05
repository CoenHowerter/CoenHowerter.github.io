<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Forensic Psychology Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.8;
            color: #1a1a1a;
            background: #f4f4f4;
            min-height: 100vh;
        }

        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 280px;
            height: 100vh;
            background: linear-gradient(180deg, #1b5e20 0%, #2e7d32 50%, #388e3c 100%);
            padding: 2rem 1.5rem;
            box-shadow: 4px 0 15px rgba(0, 0, 0, 0.2);
            overflow-y: auto;
            z-index: 1000;
        }

        .sidebar-header {
            text-align: center;
            margin-bottom: 2rem;
            padding-bottom: 2rem;
            border-bottom: 2px solid rgba(255, 255, 255, 0.3);
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 1rem;
            display: block;
            border: 4px solid rgba(255, 255, 255, 0.9);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            background: #ffffff;
        }

        .sidebar h1 {
            color: #ffffff;
            font-size: 1.6rem;
            margin-bottom: 0.5rem;
            font-weight: 700;
        }

        .sidebar .subtitle {
            color: #c8e6c9;
            font-size: 0.95rem;
            font-style: italic;
        }

        .sidebar nav {
            margin-top: 2rem;
        }

        .sidebar nav ul {
            list-style: none;
        }

        .sidebar nav li {
            margin: 0.8rem 0;
        }

        .sidebar nav a {
            color: #ffffff;
            text-decoration: none;
            font-size: 1.1rem;
            display: block;
            padding: 0.7rem 1rem;
            border-radius: 8px;
            transition: all 0.3s;
            border-left: 4px solid transparent;
        }

        .sidebar nav a:hover {
            background: rgba(255, 255, 255, 0.2);
            border-left-color: #ffffff;
            padding-left: 1.5rem;
        }

        .sidebar-footer {
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 2px solid rgba(255, 255, 255, 0.3);
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: #c8e6c9;
            text-decoration: none;
            margin: 0.8rem 0;
            font-size: 0.9rem;
            transition: color 0.3s;
        }

        .contact-link:hover {
            color: #ffffff;
        }

        .main-content {
            margin-left: 280px;
            min-height: 100vh;
        }

        .hero {
            background: linear-gradient(135deg, #2e7d32 0%, #43a047 100%);
            color: #ffffff;
            padding: 4rem 3rem;
            text-align: center;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }

        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto;
            line-height: 1.8;
        }

        .content-wrapper {
            max-width: 1000px;
            margin: 0 auto;
            padding: 3rem 2rem;
        }

        .section {
            background: #ffffff;
            margin: 2.5rem 0;
            padding: 2.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
            border-top: 5px solid #2e7d32;
        }

        .section h2 {
            color: #1b5e20;
            font-size: 2rem;
            margin-bottom: 1.5rem;
            font-weight: 700;
        }

        .section p {
            color: #424242;
            margin-bottom: 1.2rem;
            text-align: justify;
        }

        .timeline {
            position: relative;
            padding-left: 2rem;
            border-left: 3px solid #81c784;
            margin: 2rem 0;
        }

        .timeline-item {
            position: relative;
            margin-bottom: 2.5rem;
            padding-left: 2rem;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -2.6rem;
            top: 0;
            width: 20px;
            height: 20px;
            background: #2e7d32;
            border: 4px solid #ffffff;
            border-radius: 50%;
            box-shadow: 0 0 0 4px #81c784;
        }

        .timeline-item h3 {
            color: #2e7d32;
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
        }

        .timeline-item .meta {
            color: #757575;
            font-size: 0.95rem;
            margin-bottom: 0.8rem;
            font-style: italic;
        }

        .timeline-item p {
            color: #424242;
        }

        .research-cards {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .card {
            background: linear-gradient(135deg, #f1f8e9 0%, #ffffff 100%);
            padding: 2rem;
            border-radius: 8px;
            border-left: 5px solid #2e7d32;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.08);
            transition: all 0.3s;
        }

        .card:hover {
            transform: translateX(10px);
            box-shadow: 0 5px 20px rgba(46, 125, 50, 0.2);
        }

        .card h3 {
            color: #1b5e20;
            font-size: 1.3rem;
            margin-bottom: 1rem;
        }

        .card p {
            color: #424242;
            text-align: left;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            gap: 1rem;
            margin-top: 1.5rem;
        }

        .skill-item {
            background: #2e7d32;
            color: #ffffff;
            padding: 1rem;
            text-align: center;
            border-radius: 8px;
            font-weight: 600;
            box-shadow: 0 3px 10px rgba(46, 125, 50, 0.3);
            transition: all 0.3s;
        }

        .skill-item:hover {
            background: #1b5e20;
            transform: scale(1.05);
        }

        footer {
            background: #1b5e20;
            color: #c8e6c9;
            text-align: center;
            padding: 2rem;
            margin-left: 280px;
        }

        @media (max-width: 968px) {
            .sidebar {
                position: relative;
                width: 100%;
                height: auto;
            }

            .main-content {
                margin-left: 0;
            }

            footer {
                margin-left: 0;
            }

            .content-wrapper {
                padding: 2rem 1.5rem;
            }
        }
    </style>
</head>
<body>
    <aside class="sidebar">
        <div class="sidebar-header">
            <img src="CHANGE ME (URL to your headshot image)" alt="Professional Headshot" class="profile-img">
            <h1>CHANGE ME (Your Name)</h1>
            <p class="subtitle">Forensic Psychology Student</p>
        </div>

        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#research">Research</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#skills">Skills</a></li>
            </ul>
        </nav>

        <div class="sidebar-footer">
            <a href="mailto:CHANGE ME (Email)" class="contact-link">📧 CHANGE ME (Email)</a>
            <a href="tel:CHANGE ME (Phone)" class="contact-link">📱 CHANGE ME (Phone)</a>
            <a href="CHANGE ME (LinkedIn URL)" target="_blank" class="contact-link">💼 LinkedIn</a>
            <a href="CHANGE ME (GitHub URL)" target="_blank" class="contact-link">💻 GitHub</a>
            <p class="contact-link" style="cursor: default;">🎓 CHANGE ME (University)</p>
        </div>
    </aside>

    <main class="main-content">
        <section class="hero">
            <h2>Understanding the Mind and the Law</h2>
            <p>Exploring the intersection of psychology and the justice system through research, analysis, and a commitment to evidence-based practice.</p>
        </section>

        <div class="content-wrapper">
            <section id="about" class="section">
                <h2>About Me</h2>
                <p>CHANGE ME (About Me Paragraph 1) - Write about your background, what drew you to forensic psychology, and your academic interests in the intersection of psychology and law.</p>
                <p>CHANGE ME (About Me Paragraph 2) - Describe your career goals, what areas of forensic psychology interest you most, and what you hope to achieve in this field.</p>
            </section>

            <section id="research" class="section">
                <h2>Research Interests</h2>
                <div class="research-cards">
                    <div class="card">
                        <h3>CHANGE ME (Research Interest 1 Title)</h3>
                        <p>CHANGE ME (Research Interest 1 Description)</p>
                    </div>
                    <div class="card">
                        <h3>CHANGE ME (Research Interest 2 Title)</h3>
                        <p>CHANGE ME (Research Interest 2 Description)</p>
                    </div>
                    <div class="card">
                        <h3>CHANGE ME (Research Interest 3 Title)</h3>
                        <p>CHANGE ME (Research Interest 3 Description)</p>
                    </div>
                    <div class="card">
                        <h3>CHANGE ME (Research Interest 4 Title)</h3>
                        <p>CHANGE ME (Research Interest 4 Description)</p>
                    </div>
                </div>
            </section>

            <section id="experience" class="section">
                <h2>Experience & Involvement</h2>
                <div class="timeline">
                    <div class="timeline-item">
                        <h3>CHANGE ME (Experience 1 Title/Organization)</h3>
                        <p class="meta">CHANGE ME (Your Role) | CHANGE ME (Dates)</p>
                        <p>CHANGE ME (Description of responsibilities and accomplishments)</p>
                    </div>
                    <div class="timeline-item">
                        <h3>CHANGE ME (Experience 2 Title/Organization)</h3>
                        <p class="meta">CHANGE ME (Your Role) | CHANGE ME (Dates)</p>
                        <p>CHANGE ME (Description of responsibilities and accomplishments)</p>
                    </div>
                    <div class="timeline-item">
                        <h3>CHANGE ME (Experience 3 Title/Organization)</h3>
                        <p class="meta">CHANGE ME (Your Role) | CHANGE ME (Dates)</p>
                        <p>CHANGE ME (Description of responsibilities and accomplishments)</p>
                    </div>
                </div>
            </section>

            <section id="projects" class="section">
                <h2>Projects</h2>
                <div class="timeline">
                    <div class="timeline-item">
                        <h3><a href="CHANGE ME (GitHub Repository URL for Project 1)" target="_blank" style="color: #2e7d32; text-decoration: none; border-bottom: 2px solid #2e7d32;">CHANGE ME (Project 1 Title)</a></h3>
                        <p class="meta">CHANGE ME (Project Type) | CHANGE ME (Date)</p>
                        <p>CHANGE ME (Description of the project, methods used, and key findings or outcomes)</p>
                    </div>
                    <div class="timeline-item">
                        <h3><a href="CHANGE ME (GitHub Repository URL for Project 2)" target="_blank" style="color: #2e7d32; text-decoration: none; border-bottom: 2px solid #2e7d32;">CHANGE ME (Project 2 Title)</a></h3>
                        <p class="meta">CHANGE ME (Project Type) | CHANGE ME (Date)</p>
                        <p>CHANGE ME (Description of the project, methods used, and key findings or outcomes)</p>
                    </div>
                    <div class="timeline-item">
                        <h3><a href="CHANGE ME (GitHub Repository URL for Project 3)" target="_blank" style="color: #2e7d32; text-decoration: none; border-bottom: 2px solid #2e7d32;">CHANGE ME (Project 3 Title)</a></h3>
                        <p class="meta">CHANGE ME (Project Type) | CHANGE ME (Date)</p>
                        <p>CHANGE ME (Description of the project, methods used, and key findings or outcomes)</p>
                    </div>
                </div>
            </section>

            <section id="skills" class="section">
                <h2>Skills & Competencies</h2>
                <div class="skills-grid">
                    <div class="skill-item">CHANGE ME (Skill 1)</div>
                    <div class="skill-item">CHANGE ME (Skill 2)</div>
                    <div class="skill-item">CHANGE ME (Skill 3)</div>
                    <div class="skill-item">CHANGE ME (Skill 4)</div>
                    <div class="skill-item">CHANGE ME (Skill 5)</div>
                    <div class="skill-item">CHANGE ME (Skill 6)</div>
                    <div class="skill-item">CHANGE ME (Skill 7)</div>
                    <div class="skill-item">CHANGE ME (Skill 8)</div>
                    <div class="skill-item">CHANGE ME (Skill 9)</div>
                    <div class="skill-item">CHANGE ME (Skill 10)</div>
                </div>
            </section>
        </div>

        <footer>
            <p>&copy; 2025 CHANGE ME (Your Name) | Forensic Psychology Student | Understanding the Mind and the Law</p>
        </footer>
    </main>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('.sidebar nav a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            });
        });
    </script>
</body>
</html>
