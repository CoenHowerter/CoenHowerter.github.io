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
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #2a2a2a;
            background: linear-gradient(135deg, #0d3d2d 0%, #1a4d3a 50%, #0a2618 100%);
            min-height: 100vh;
        }

        .background-pattern {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.03;
            z-index: 0;
            background-image: 
                repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(255,255,255,.05) 2px, rgba(255,255,255,.05) 4px),
                repeating-linear-gradient(90deg, transparent, transparent 2px, rgba(255,255,255,.05) 2px, rgba(255,255,255,.05) 4px);
            pointer-events: none;
        }

        header {
            background: linear-gradient(135deg, rgba(34, 139, 34, 0.9) 0%, rgba(46, 125, 50, 0.9) 100%);
            backdrop-filter: blur(10px);
            padding: 3rem 0;
            text-align: center;
            border-bottom: 3px solid rgba(34, 139, 34, 0.5);
            position: relative;
            z-index: 1;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
        }

        header h1 {
            font-size: 2.8rem;
            color: #ffffff;
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            font-weight: 700;
        }

        header p {
            font-size: 1.3rem;
            color: #f8f9fa;
            font-weight: 300;
        }

        nav {
            background: rgba(26, 26, 46, 0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            position: relative;
            z-index: 100;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.4);
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 2rem;
        }

        nav a {
            color: #4caf50;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 1px;
        }

        nav a:hover {
            background: rgba(76, 175, 80, 0.2);
            transform: translateY(-2px);
            color: #81c784;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
            z-index: 1;
        }

        section {
            background: rgba(248, 249, 250, 0.95);
            backdrop-filter: blur(10px);
            margin: 2rem 0;
            padding: 2.5rem;
            border-radius: 12px;
            border-left: 5px solid #2e7d32;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
        }

        h2 {
            color: #2e7d32;
            margin-bottom: 1.5rem;
            font-size: 2.2rem;
            font-weight: 700;
            border-bottom: 3px solid rgba(46, 125, 50, 0.3);
            padding-bottom: 0.5rem;
        }

        h3 {
            color: #495057;
            margin-top: 1.5rem;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        p {
            color: #495057;
            margin-bottom: 1rem;
        }

        .research-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .research-card {
            background: linear-gradient(135deg, rgba(76, 175, 80, 0.05) 0%, rgba(46, 125, 50, 0.05) 100%);
            padding: 1.8rem;
            border-radius: 10px;
            border: 2px solid rgba(76, 175, 80, 0.2);
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }

        .research-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 35px rgba(76, 175, 80, 0.3);
            border-color: #4caf50;
        }

        .research-card h3 {
            color: #2e7d32;
            margin-top: 0;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 1rem;
        }

        .skill-tag {
            background: linear-gradient(135deg, #2e7d32 0%, #1b5e20 100%);
            color: #ffffff;
            padding: 0.6rem 1.2rem;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 600;
            box-shadow: 0 4px 10px rgba(46, 125, 50, 0.3);
            transition: all 0.3s;
        }

        .skill-tag:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(46, 125, 50, 0.4);
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 1.2rem;
            margin-top: 1rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background: rgba(76, 175, 80, 0.05);
            border-radius: 8px;
            border-left: 4px solid #2e7d32;
        }

        .contact-item strong {
            color: #2e7d32;
            min-width: 100px;
        }

        .contact-item a {
            color: #495057;
            text-decoration: none;
            transition: color 0.3s;
        }

        .contact-item a:hover {
            color: #2e7d32;
        }

        footer {
            background: linear-gradient(135deg, rgba(26, 26, 46, 0.95) 0%, rgba(22, 33, 62, 0.95) 100%);
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
            border-top: 3px solid rgba(46, 125, 50, 0.5);
            position: relative;
            z-index: 1;
        }

        footer p {
            color: #f8f9fa;
            margin: 0;
        }

        ul {
            margin-left: 2rem;
            margin-top: 1rem;
        }

        li {
            margin: 0.8rem 0;
            color: #495057;
            line-height: 1.6;
        }

        @media (max-width: 768px) {
            header h1 {
                font-size: 2rem;
            }
            
            nav ul {
                flex-direction: column;
                gap: 0.5rem;
            }
            
            .container {
                padding: 1rem;
            }

            section {
                padding: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <div class="background-pattern"></div>

    <header>
        <h1>Saiya Bonnett</h1>
        <p>Forensic Psychology Undergraduate Student</p>
    </header>

    <nav>
        <ul>
            <li><a href="#about">About</a></li>
            <li><a href="#research">Research</a></li>
            <li><a href="#experience">Experience</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <div class="container">
        <section id="about">
            <h2>About Me</h2>
            <p>about you background, what drew you to forensic psychology, and your academic interests in the intersection of psychology and law.</p>
            <p>Describe your career goals, what areas of forensic psychology interest you most, and what you hope to achieve in this field.</p>
        </section>

        <section id="research">
            <h2>Research</h2>
            <div class="research-grid">
                <div class="research-card">
                    <h3>CHANGE ME (Research Interest 1 Title)</h3>
                    <p>CHANGE ME (Research Interest 1 Description)</p>
                </div>
                <div class="research-card">
                    <h3>CHANGE ME (Research Interest 2 Title)</h3>
                    <p>CHANGE ME (Research Interest 2 Description)</p>
                </div>
                <div class="research-card">
                    <h3>CHANGE ME (Research Interest 3 Title)</h3>
                    <p>CHANGE ME (Research Interest 3 Description)</p>
                </div>
                <div class="research-card">
                    <h3>CHANGE ME (Research Interest 4 Title)</h3>
                    <p>CHANGE ME (Research Interest 4 Description)</p>
                </div>
            </div>
        </section>

        <section id="experience">
            <h2>Experience & Involvement</h2>
            <h3>CHANGE ME (Experience 1 Title/Organization)</h3>
            <p><strong>Role:</strong> CHANGE ME (Your Role)</p>
            <p><strong>Duration:</strong> CHANGE ME (Dates)</p>
            <p>CHANGE ME (Description of responsibilities and accomplishments)</p>

            <h3>CHANGE ME (Experience 2 Title/Organization)</h3>
            <p><strong>Role:</strong> CHANGE ME (Your Role)</p>
            <p><strong>Duration:</strong> CHANGE ME (Dates)</p>
            <p>CHANGE ME (Description of responsibilities and accomplishments)</p>

            <h3>CHANGE ME (Experience 3 Title/Organization)</h3>
            <p><strong>Role:</strong> CHANGE ME (Your Role)</p>
            <p><strong>Duration:</strong> CHANGE ME (Dates)</p>
            <p>CHANGE ME (Description of responsibilities and accomplishments)</p>
        </section>

        <section id="projects">
            <h2>Projects</h2>
            <h3>CHANGE ME (Project 1 Title)</h3>
            <p><strong>Type:</strong> CHANGE ME (Project Type - e.g., Research Project, Case Study, etc.)</p>
            <p><strong>Date:</strong> CHANGE ME (Completion Date or Duration)</p>
            <p>CHANGE ME (Description of the project, methods used, and key findings or outcomes)</p>

            <h3>CHANGE ME (Project 2 Title)</h3>
            <p><strong>Type:</strong> CHANGE ME (Project Type)</p>
            <p><strong>Date:</strong> CHANGE ME (Completion Date or Duration)</p>
            <p>CHANGE ME (Description of the project, methods used, and key findings or outcomes)</p>

            <h3>CHANGE ME (Project 3 Title)</h3>
            <p><strong>Type:</strong> CHANGE ME (Project Type)</p>
            <p><strong>Date:</strong> CHANGE ME (Completion Date or Duration)</p>
            <p>CHANGE ME (Description of the project, methods used, and key findings or outcomes)</p>
        </section>

        <section id="skills">
            <h2>Skills & Competencies</h2>
            <div class="skills">
                <span class="skill-tag">CHANGE ME (Skill 1)</span>
                <span class="skill-tag">CHANGE ME (Skill 2)</span>
                <span class="skill-tag">CHANGE ME (Skill 3)</span>
                <span class="skill-tag">CHANGE ME (Skill 4)</span>
                <span class="skill-tag">CHANGE ME (Skill 5)</span>
                <span class="skill-tag">CHANGE ME (Skill 6)</span>
                <span class="skill-tag">CHANGE ME (Skill 7)</span>
                <span class="skill-tag">CHANGE ME (Skill 8)</span>
                <span class="skill-tag">CHANGE ME (Skill 9)</span>
                <span class="skill-tag">CHANGE ME (Skill 10)</span>
            </div>
        </section>

        <section id="contact">
            <h2>Contact</h2>
            <div class="contact-info">
                <div class="contact-item">
                    <strong>Email:</strong>
                    <a href="mailto:Yoshibonnett@gmail.com ">Saiya Bonnett</a>
                </div>
                <div class="contact-item">
                    <strong>LinkedIn:</strong>
                    <a href="https://linkedin.com/in/yourprofile" target="_blank">LinkedIn</a>
                </div>
                <div class="contact-item">
                    <strong>Phone Number:</strong>
                    <a href="https://github.com/yourusername" target="_blank">(321)-917-8521</a>
                </div>
                <div class="contact-item">
                    <strong>University:</strong>
                    <span>Florida Institute of Technology</span>
                </div>
            </div>
        </section>
    </div>

    <footer>
        <p>&copy; 2025 Saiya Bonnett | Forensic Psychology | Understanding the Mind</p>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            });
        });

        // Add subtle hover effect to sections
        const sections = document.querySelectorAll('section');
        sections.forEach(section => {
            section.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-2px)';
                this.style.transition = 'transform 0.3s ease';
            });
            section.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0)';
            });
        });
    </script>
</body>
</html>
