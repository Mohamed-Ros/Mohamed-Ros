<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mohamed Eid - Backend Developer & Instructor</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: white;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #ffd700;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            opacity: 0.8;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            color: white;
            max-width: 800px;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.5s forwards;
        }

        .hero .subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeInUp 1s ease 1s forwards;
        }

        .hero .description {
            font-size: 1.1rem;
            margin-bottom: 3rem;
            opacity: 0;
            animation: fadeInUp 1s ease 1.5s forwards;
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

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            opacity: 0;
            animation: fadeInUp 1s ease 2s forwards;
        }

        .btn {
            padding: 12px 30px;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            color: white;
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        /* Stats Section */
        .stats {
            background: rgba(255, 255, 255, 0.95);
            padding: 4rem 0;
            margin-top: -100px;
            position: relative;
            z-index: 3;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .stat-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1.1rem;
            color: #666;
        }

        /* About Section */
        .about {
            padding: 6rem 0;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            color: #333;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #555;
        }

        .about-image {
            text-align: center;
        }

        .code-block {
            background: #1a1a1a;
            color: #00ff00;
            padding: 2rem;
            border-radius: 10px;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
            overflow: auto;
            margin-top: 2rem;
        }

        /* Skills Section */
        .skills {
            padding: 6rem 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }

        .skill-category {
            background: rgba(255, 255, 255, 0.1);
            padding: 2rem;
            border-radius: 15px;
            backdrop-filter: blur(10px);
        }

        .skill-category h3 {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: #ffd700;
        }

        .skill-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
            padding: 0.5rem 0;
        }

        .skill-name {
            font-weight: bold;
        }

        .skill-level {
            background: rgba(255, 255, 255, 0.2);
            width: 100px;
            height: 6px;
            border-radius: 3px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, #ffd700, #ff6b6b);
            border-radius: 3px;
            transition: width 2s ease;
        }

        /* Projects Section */
        .projects {
            padding: 6rem 0;
            background: #f8f9fa;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
        }

        .project-content {
            padding: 2rem;
        }

        .project-title {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #333;
        }

        .project-description {
            color: #666;
            line-height: 1.6;
            margin-bottom: 1.5rem;
        }

        .tech-tags {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background: #e9ecef;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            color: #495057;
        }

        /* Contact Section */
        .contact {
            padding: 6rem 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin-top: 3rem;
            flex-wrap: wrap;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        /* Footer */
        footer {
            background: #1a1a1a;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero .subtitle {
                font-size: 1.2rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .nav-links {
                display: none;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }
        }

        /* Scroll Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Floating Elements */
        .floating {
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <a href="#" class="logo">Mohamed Eid</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Mohamed Eid</h1>
            <p class="subtitle">Senior Backend Developer & Udemy Instructor</p>
            <p class="description">
                Specialized in Laravel & Django development with 2,300+ students learning from my courses.
                Building scalable SaaS platforms and e-commerce solutions that transform businesses.
            </p>
            <div class="cta-buttons">
                <a href="#projects" class="btn btn-primary">View My Work</a>
                <a href="#contact" class="btn btn-secondary">Get In Touch</a>
            </div>
        </div>
    </section>

    <section class="stats">
        <div class="container">
            <div class="stats-grid">
                <div class="stat-card floating">
                    <div class="stat-number">5+</div>
                    <div class="stat-label">Years Experience</div>
                </div>
                <div class="stat-card floating">
                    <div class="stat-number">2,300+</div>
                    <div class="stat-label">Udemy Students</div>
                </div>
                <div class="stat-card floating">
                    <div class="stat-number">50+</div>
                    <div class="stat-label">Projects Completed</div>
                </div>
                <div class="stat-card floating">
                    <div class="stat-number">98%</div>
                    <div class="stat-label">Client Satisfaction</div>
                </div>
            </div>
        </div>
    </section>

    <section class="about" id="about">
        <div class="container">
            <h2 class="section-title fade-in">About Me</h2>
            <div class="about-content">
                <div class="about-text fade-in">
                    <p>I'm a passionate Backend Developer from Egypt with expertise in Laravel and Django frameworks. Currently working on SaaS platforms, APIs, and e-commerce solutions that solve real-world problems.</p>
                    
                    <p>As a Udemy instructor, I've helped over 2,300 students master backend development, sharing my knowledge and experience in building scalable, maintainable systems.</p>
                    
                    <p>I'm always learning and exploring new technologies like DevOps, Docker, and System Security to stay at the forefront of backend development.</p>
                </div>
                <div class="about-image fade-in">
                    <div class="code-block">
                        <pre>
class Mohamed extends Developer {
    
    public function skills() {
        return [
            'backend' => ['Laravel', 'Django', 'PHP', 'Python'],
            'database' => ['MySQL', 'PostgreSQL', 'Redis'],
            'tools' => ['Git', 'Docker', 'Linux', 'AWS'],
            'teaching' => ['Udemy Instructor', '2300+ Students']
        ];
    }
    
    public function currentFocus() {
        return 'Building scalable SaaS platforms';
    }
}
                        </pre>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="skills" id="skills">
        <div class="container">
            <h2 class="section-title fade-in">Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-category fade-in">
                    <h3>🚀 Backend Frameworks</h3>
                    <div class="skill-item">
                        <span class="skill-name">Laravel</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">Django</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">PHP</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">Python</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category fade-in">
                    <h3>🗄️ Database & Tools</h3>
                    <div class="skill-item">
                        <span class="skill-name">MySQL</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">PostgreSQL</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">Redis</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">Git</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category fade-in">
                    <h3>🔧 DevOps & Deployment</h3>
                    <div class="skill-item">
                        <span class="skill-name">Docker</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 75%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">Linux</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">AWS</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 70%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <span class="skill-name">CI/CD</span>
                        <div class="skill-level">
                            <div class="skill-progress" style="width: 75%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="projects" id="projects">
        <div class="container">
            <h2 class="section-title fade-in">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <div class="project-image">🏪</div>
                    <div class="project-content">
                        <h3 class="project-title">E-commerce Platform</h3>
                        <p class="project-description">
                            Full-featured e-commerce solution with payment integration, inventory management, and admin dashboard.
                        </p>
                        <div class="tech-tags">
                            <span class="tech-tag">Laravel</span>
                            <span class="tech-tag">MySQL</span>
                            <span class="tech-tag">Payment Gateway</span>
                            <span class="tech-tag">Admin Panel</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card fade-in">
                    <div class="project-image">🚀</div>
                    <div class="project-content">
                        <h3 class="project-title">SaaS Management System</h3>
                        <p class="project-description">
                            Multi-tenant SaaS platform with subscription management, API integrations, and real-time analytics.
                        </p>
                        <div class="tech-tags">
                            <span class="tech-tag">Django</span>
                            <span class="tech-tag">PostgreSQL</span>
                            <span class="tech-tag">Redis</span>
                            <span class="tech-tag">Celery</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card fade-in">
                    <div class="project-image">📚</div>
                    <div class="project-content">
                        <h3 class="project-title">Udemy Course Platform</h3>
                        <p class="project-description">
                            Teaching backend development to 2,300+ students with comprehensive Laravel and Django courses.
                        </p>
                        <div class="tech-tags">
                            <span class="tech-tag">Teaching</span>
                            <span class="tech-tag">Laravel</span>
                            <span class="tech-tag">Django</span>
                            <span class="tech-tag">Course Creation</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <div class="container">
            <h2 class="section-title fade-in">Let's Work Together</h2>
            <p class="fade-in">Ready to bring your ideas to life? Let's discuss your next project!</p>
            
            <div class="contact-info fade-in">
                <div class="contact-item">
                    <div class="contact-icon">📧</div>
                    <div>
                        <h3>Email</h3>
                        <p>mohamed_eid_hussin@hotmail.com</p>
                    </div>
                </div>
                
                <div class="contact-item">
                    <div class="contact-icon">🌍</div>
                    <div>
                        <h3>Location</h3>
                        <p>Benisuef, Egypt</p>
                    </div>
                </div>
                
                <div class="contact-item">
                    <div class="contact-icon">💼</div>
                    <div>
                        <h3>LinkedIn</h3>
                        <p>Connect with me</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2024 Mohamed Eid. Turning ideas into scalable solutions.</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Animate skill progress bars
        const skillObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const progressBars = entry.target.querySelectorAll('.skill-progress');
                    progressBars.forEach(bar => {
                        const width = bar.style.width;
                        bar.style.width = '0%';
                        setTimeout(() => {
                            bar.style.width = width;
                        }, 500);
                    });
                }
            });
        }, { threshold: 0.5 });

        document.querySelectorAll('.skill-category').forEach(category => {
            skillObserver.observe(category);
        });

        // Header background change on scroll
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(0, 0, 0, 0.9)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.1)';
            }
        });
    </script>
</body>
</html>
