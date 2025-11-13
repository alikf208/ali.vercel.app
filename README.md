<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ALI MUNTHASIR | Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-dark: #0a192f;
            --primary-blue: #112240;
            --accent-blue: #64ffda;
            --accent-green: #00d4aa;
            --text-light: #ccd6f6;
            --text-white: #e6f1ff;
        }

        body {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary-blue), #0d2b4e, #0a3d62);
            background-size: 400% 400%;
            animation: gradientBG 20s ease infinite;
            color: var(--text-light);
            min-height: 100vh;
            overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Password Screen */
        .password-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            background: rgba(10, 25, 47, 0.95);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            transition: opacity 0.5s ease;
        }

        .password-box {
            background: rgba(17, 34, 64, 0.8);
            border-radius: 20px;
            padding: 50px;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(100, 255, 218, 0.2);
            max-width: 500px;
            width: 90%;
        }

        .password-box h1 {
            color: var(--accent-blue);
            margin-bottom: 15px;
            font-size: 2.8rem;
            text-shadow: 0 0 10px rgba(100, 255, 218, 0.5);
        }

        .ai-badge {
            display: inline-block;
            background: linear-gradient(45deg, var(--accent-blue), var(--accent-green));
            padding: 8px 20px;
            border-radius: 30px;
            font-size: 0.9rem;
            margin-bottom: 25px;
            color: var(--primary-dark);
            font-weight: bold;
            box-shadow: 0 4px 15px rgba(100, 255, 218, 0.4);
        }

        .password-form {
            margin: 30px 0;
        }

        input[type="password"] {
            width: 100%;
            padding: 18px;
            border: none;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--text-white);
            font-size: 1.1rem;
            margin-bottom: 20px;
            text-align: center;
            outline: none;
            transition: all 0.3s ease;
            border: 1px solid rgba(100, 255, 218, 0.3);
        }

        input[type="password"]:focus {
            background: rgba(255, 255, 255, 0.15);
            box-shadow: 0 0 20px rgba(100, 255, 218, 0.3);
            border-color: var(--accent-blue);
        }

        input[type="password"]::placeholder {
            color: rgba(255, 255, 255, 0.5);
        }

        button {
            background: linear-gradient(45deg, var(--accent-blue), var(--accent-green));
            color: var(--primary-dark);
            border: none;
            padding: 18px 35px;
            border-radius: 10px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
            box-shadow: 0 4px 15px rgba(100, 255, 218, 0.4);
            width: 100%;
        }

        button:hover {
            transform: translateY(-5px);
            box-shadow: 0 7px 20px rgba(100, 255, 218, 0.6);
        }

        .error-message {
            color: #ff6b6b;
            margin-top: 15px;
            font-weight: bold;
            display: none;
        }

        /* Portfolio Content */
        .portfolio-content {
            display: none;
            opacity: 0;
            transition: opacity 1s ease;
        }

        .portfolio-header {
            text-align: center;
            padding: 60px 0 40px;
        }

        .portfolio-header h1 {
            font-size: 4rem;
            color: var(--text-white);
            margin-bottom: 15px;
            text-shadow: 0 0 15px rgba(100, 255, 218, 0.3);
        }

        .portfolio-header .tagline {
            font-size: 1.5rem;
            color: var(--accent-blue);
            margin-bottom: 30px;
        }

        /* Navigation */
        .navbar {
            display: flex;
            justify-content: center;
            margin-bottom: 40px;
            background: rgba(17, 34, 64, 0.7);
            border-radius: 15px;
            padding: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(100, 255, 218, 0.1);
        }

        .nav-link {
            color: var(--text-light);
            text-decoration: none;
            padding: 12px 25px;
            margin: 0 10px;
            border-radius: 8px;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .nav-link:hover, .nav-link.active {
            background: rgba(100, 255, 218, 0.1);
            color: var(--accent-blue);
        }

        /* Hero Section */
        .hero-section {
            display: flex;
            align-items: center;
            gap: 50px;
            margin-bottom: 80px;
            flex-wrap: wrap;
        }

        .profile-img {
            flex: 1;
            min-width: 300px;
            display: flex;
            justify-content: center;
        }

        .profile-img-placeholder {
            width: 350px;
            height: 350px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--accent-blue), var(--accent-green));
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 6rem;
            color: var(--primary-dark);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            border: 5px solid rgba(100, 255, 218, 0.3);
        }

        .hero-content {
            flex: 2;
            min-width: 300px;
        }

        .hero-content h2 {
            font-size: 3rem;
            color: var(--text-white);
            margin-bottom: 20px;
        }

        .hero-content .name {
            color: var(--accent-blue);
            text-shadow: 0 0 10px rgba(100, 255, 218, 0.3);
        }

        .hero-content p {
            font-size: 1.2rem;
            line-height: 1.8;
            margin-bottom: 30px;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 15px 30px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--accent-blue), var(--accent-green));
            color: var(--primary-dark);
            box-shadow: 0 4px 15px rgba(100, 255, 218, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 7px 20px rgba(100, 255, 218, 0.6);
        }

        .btn-secondary {
            background: transparent;
            color: var(--accent-blue);
            border: 2px solid var(--accent-blue);
        }

        .btn-secondary:hover {
            background: rgba(100, 255, 218, 0.1);
            transform: translateY(-5px);
        }

        /* Skills Section */
        .section {
            margin-bottom: 100px;
        }

        .section-title {
            font-size: 2.5rem;
            color: var(--text-white);
            margin-bottom: 50px;
            text-align: center;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(45deg, var(--accent-blue), var(--accent-green));
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .skill-card {
            background: rgba(17, 34, 64, 0.7);
            border-radius: 15px;
            padding: 30px;
            transition: all 0.3s ease;
            border: 1px solid rgba(100, 255, 218, 0.1);
            backdrop-filter: blur(10px);
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            border-color: rgba(100, 255, 218, 0.3);
        }

        .skill-icon {
            font-size: 3rem;
            color: var(--accent-blue);
            margin-bottom: 20px;
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--text-white);
        }

        .skill-card p {
            line-height: 1.6;
            color: var(--text-light);
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: rgba(17, 34, 64, 0.7);
            border-radius: 15px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(100, 255, 218, 0.1);
            backdrop-filter: blur(10px);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            border-color: rgba(100, 255, 218, 0.3);
        }

        .project-img {
            height: 220px;
            background: linear-gradient(45deg, var(--accent-blue), var(--accent-green));
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--primary-dark);
            font-size: 1.8rem;
            font-weight: bold;
        }

        .project-info {
            padding: 25px;
        }

        .project-info h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--text-white);
        }

        .project-info p {
            line-height: 1.6;
            margin-bottom: 20px;
            color: var(--text-light);
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tag {
            background: rgba(100, 255, 218, 0.1);
            color: var(--accent-blue);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.9rem;
        }

        /* Contact Section */
        .contact-section {
            text-align: center;
            padding: 60px 0;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 40px;
            margin: 50px 0;
        }

        .contact-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
        }

        .contact-icon {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: rgba(100, 255, 218, 0.1);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.8rem;
            color: var(--accent-blue);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-top: 40px;
        }

        .social-link {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(17, 34, 64, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--accent-blue);
            text-decoration: none;
            font-size: 1.5rem;
            transition: all 0.3s ease;
            border: 1px solid rgba(100, 255, 218, 0.1);
        }

        .social-link:hover {
            background: rgba(100, 255, 218, 0.1);
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(100, 255, 218, 0.3);
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 60px;
            border-top: 1px solid rgba(100, 255, 218, 0.1);
            color: var(--text-light);
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .hero-section {
                flex-direction: column;
                text-align: center;
            }
            
            .cta-buttons {
                justify-content: center;
            }
            
            .navbar {
                flex-wrap: wrap;
            }
        }

        @media (max-width: 768px) {
            .portfolio-header h1 {
                font-size: 2.8rem;
            }
            
            .hero-content h2 {
                font-size: 2.2rem;
            }
            
            .password-box {
                padding: 30px 20px;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Password Screen -->
    <div class="password-screen" id="passwordScreen">
        <div class="password-box">
            <h1>ALI MUNTHASIR</h1>
            <div class="ai-badge">AI-ENHANCED CREATIVE PORTFOLIO</div>
            <p>This portfolio is protected. Please enter the password to continue.</p>
            
            <div class="password-form">
                <input type="password" id="passwordInput" placeholder="Enter Password">
                <button onclick="checkPassword()">ACCESS PORTFOLIO</button>
                <div class="error-message" id="errorMessage">Incorrect password. Please try again.</div>
            </div>
            
            <p>Hint: The password is a 5-digit number</p>
        </div>
    </div>
    
    <!-- Portfolio Content -->
    <div class="portfolio-content" id="portfolioContent">
        <div class="container">
            <header class="portfolio-header">
                <h1>ALI MUNTHASIR</h1>
                <div class="ai-badge">AI-ENHANCED CREATIVE PORTFOLIO</div>
                <p class="tagline">Creative Designer & Digital Artist</p>
                
                <nav class="navbar">
                    <a href="#about" class="nav-link active">About</a>
                    <a href="#skills" class="nav-link">Skills</a>
                    <a href="#projects" class="nav-link">Projects</a>
                    <a href="#contact" class="nav-link">Contact</a>
                </nav>
            </header>
            
            <section class="hero-section" id="about">
                <div class="profile-img">
                    <div class="profile-img-placeholder">
                        <i class="fas fa-user"></i>
                    </div>
                </div>
                <div class="hero-content">
                    <h2>Hi, I'm <span class="name">ALI MUNTHASIR</span></h2>
                    <p>I'm a passionate creative professional specializing in poster design, graphic design, web design, product advertisement, and product mockups. With a keen eye for detail and a love for innovative design, I create visually stunning and effective solutions for businesses and brands.</p>
                    <p>My work combines artistic vision with technical expertise to deliver designs that not only look great but also drive results.</p>
                    
                    <div class="cta-buttons">
                        <a href="#projects" class="btn btn-primary">View My Work</a>
                        <a href="#contact" class="btn btn-secondary">Get In Touch</a>
                    </div>
                </div>
            </section>
            
            <section class="section" id="skills">
                <h2 class="section-title">My Skills</h2>
                <div class="skills-grid">
                    <div class="skill-card">
                        <div class="skill-icon">
                            <i class="fas fa-palette"></i>
                        </div>
                        <h3>Poster Design</h3>
                        <p>Creating eye-catching posters for events, promotions, and campaigns with strong visual impact and clear messaging.</p>
                    </div>
                    
                    <div class="skill-card">
                        <div class="skill-icon">
                            <i class="fas fa-pencil-alt"></i>
                        </div>
                        <h3>Graphic Design</h3>
                        <p>Designing logos, branding materials, and visual content that communicates brand identity effectively.</p>
                    </div>
                    
                    <div class="skill-card">
                        <div class="skill-icon">
                            <i class="fas fa-laptop-code"></i>
                        </div>
                        <h3>Web Design</h3>
                        <p>Creating responsive, user-friendly websites with modern design principles and optimal user experience.</p>
                    </div>
                    
                    <div class="skill-card">
                        <div class="skill-icon">
                            <i class="fas fa-bullhorn"></i>
                        </div>
                        <h3>Product Advertisement</h3>
                        <p>Developing compelling ad campaigns and marketing materials that drive engagement and conversions.</p>
                    </div>
                    
                    <div class="skill-card">
                        <div class="skill-icon">
                            <i class="fas fa-cube"></i>
                        </div>
                        <h3>Product Mockup</h3>
                        <p>Creating realistic product mockups that showcase designs in context and help visualize final products.</p>
                    </div>
                    
                    <div class="skill-card">
                        <div class="skill-icon">
                            <i class="fas fa-robot"></i>
                        </div>
                        <h3>AI-Enhanced Design</h3>
                        <p>Leveraging AI tools to enhance creativity, streamline workflows, and generate innovative design concepts.</p>
                    </div>
                </div>
            </section>
            
            <section class="section" id="projects">
                <h2 class="section-title">Featured Projects</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-img">CONCERT POSTER SERIES</div>
                        <div class="project-info">
                            <h3>Music Festival Posters</h3>
                            <p>A series of vibrant posters for a summer music festival, featuring bold typography and dynamic illustrations.</p>
                            <div class="project-tags">
                                <span class="tag">Poster Design</span>
                                <span class="tag">Illustration</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-img">ECO BRAND IDENTITY</div>
                        <div class="project-info">
                            <h3>Sustainable Brand Package</h3>
                            <p>Complete branding for an eco-friendly product line, including logo, packaging, and marketing materials.</p>
                            <div class="project-tags">
                                <span class="tag">Branding</span>
                                <span class="tag">Graphic Design</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-img">TECH WEBSITE UI/UX</div>
                        <div class="project-info">
                            <h3>Innovation Tech Portal</h3>
                            <p>Modern website design for a technology company with intuitive navigation and engaging user interface.</p>
                            <div class="project-tags">
                                <span class="tag">Web Design</span>
                                <span class="tag">UI/UX</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-img">PRODUCT AD CAMPAIGN</div>
                        <div class="project-info">
                            <h3>Smartwatch Launch</h3>
                            <p>Complete advertising campaign for a new smartwatch, including digital ads, print materials, and social media content.</p>
                            <div class="project-tags">
                                <span class="tag">Advertising</span>
                                <span class="tag">Campaign</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-img">APPAREL MOCKUPS</div>
                        <div class="project-info">
                            <h3>Fashion Line Presentation</h3>
                            <p>Realistic product mockups for a clothing brand, showcasing designs on various models and in different settings.</p>
                            <div class="project-tags">
                                <span class="tag">Mockup</span>
                                <span class="tag">Fashion</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-img">AI ART COLLECTION</div>
                        <div class="project-info">
                            <h3>Generative Art Series</h3>
                            <p>Exploring the intersection of AI and creativity through a series of algorithmically generated artworks.</p>
                            <div class="project-tags">
                                <span class="tag">AI Art</span>
                                <span class="tag">Digital</span>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            
            <section class="contact-section" id="contact">
                <h2 class="section-title">Get In Touch</h2>
                <p>Interested in working together? Feel free to contact me for any project or collaboration.</p>
                
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div>
                            <h3>Email</h3>
                            <p>ali.munthasir@example.com</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div>
                            <h3>Phone</h3>
                            <p>+1 (555) 123-4567</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div>
                            <h3>Location</h3>
                            <p>Creative District, Design City</p>
                        </div>
                    </div>
                </div>
                
                <div class="social-links">
                    <a href="#" class="social-link">
                        <i class="fab fa-behance"></i>
                    </a>
                    <a href="#" class="social-link">
                        <i class="fab fa-dribbble"></i>
                    </a>
                    <a href="#" class="social-link">
                        <i class="fab fa-instagram"></i>
                    </a>
                    <a href="#" class="social-link">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                </div>
            </section>
            
            <footer class="footer">
                <p>&copy; 2023 ALI MUNTHASIR. All Rights Reserved. | AI-Enhanced Creative Portfolio</p>
            </footer>
        </div>
    </div>

    <script>
        function checkPassword() {
            const password = document.getElementById('passwordInput').value;
            const errorMessage = document.getElementById('errorMessage');
            const passwordScreen = document.getElementById('passwordScreen');
            const portfolioContent = document.getElementById('portfolioContent');
            
            if (password === '97780') {
                // Correct password
                passwordScreen.style.opacity = '0';
                setTimeout(() => {
                    passwordScreen.style.display = 'none';
                    portfolioContent.style.display = 'block';
                    setTimeout(() => {
                        portfolioContent.style.opacity = '1';
                    }, 100);
                }, 500);
            } else {
                // Incorrect password
                errorMessage.style.display = 'block';
                document.getElementById('passwordInput').value = '';
                
                // Shake animation for wrong password
                passwordScreen.style.animation = 'shake 0.5s';
                setTimeout(() => {
                    passwordScreen.style.animation = '';
                }, 500);
            }
        }
        
        // Allow pressing Enter to submit password
        document.getElementById('passwordInput').addEventListener('keyup', function(event) {
            if (event.key === 'Enter') {
                checkPassword();
            }
        });
        
        // Smooth scrolling for navigation links
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                
                // Remove active class from all links
                document.querySelectorAll('.nav-link').forEach(item => {
                    item.classList.remove('active');
                });
                
                // Add active class to clicked link
                this.classList.add('active');
                
                const targetId = this.getAttribute('href');
                const targetSection = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetSection.offsetTop - 100,
                    behavior: 'smooth'
                });
            });
        });
        
        // Add shake animation for wrong password
        const style = document.createElement('style');
        style.textContent = `
            @keyframes shake {
                0%, 100% { transform: translateX(0); }
                10%, 30%, 50%, 70%, 90% { transform: translateX(-10px); }
                20%, 40%, 60%, 80% { transform: translateX(10px); }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
