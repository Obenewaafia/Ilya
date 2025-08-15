<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Student Athlete</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #2d4a3e;
            background: linear-gradient(135deg, #f8fffe 0%, #f0f8f5 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 20px rgba(72, 139, 96, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
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
            color: #488b60;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #2d4a3e;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #488b60;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: #6bb77b;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        main {
            margin-top: 80px;
        }

        .hero {
            padding: 80px 0;
            text-align: center;
            background: linear-gradient(135deg, rgba(104, 183, 123, 0.1) 0%, rgba(72, 139, 96, 0.05) 100%);
            margin-bottom: 2rem;
        }

        .hero h1 {
            font-size: 3rem;
            color: #2d4a3e;
            margin-bottom: 1rem;
            font-weight: 300;
        }

        .hero .subtitle {
            font-size: 1.3rem;
            color: #488b60;
            margin-bottom: 2rem;
            font-weight: 400;
        }

        .hero .description {
            font-size: 1.1rem;
            color: #5a6c5d;
            max-width: 600px;
            margin: 0 auto;
            line-height: 1.8;
        }

        .section {
            padding: 60px 0;
            margin-bottom: 2rem;
        }

        .section h2 {
            font-size: 2.5rem;
            color: #2d4a3e;
            text-align: center;
            margin-bottom: 3rem;
            font-weight: 300;
            position: relative;
        }

        .section h2::after {
            content: '';
            position: absolute;
            width: 60px;
            height: 3px;
            background: linear-gradient(90deg, #6bb77b, #488b60);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .card {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 8px 32px rgba(72, 139, 96, 0.1);
            border: 1px solid rgba(104, 183, 123, 0.2);
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(72, 139, 96, 0.15);
        }

        .card h3 {
            color: #488b60;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .card p {
            color: #5a6c5d;
            line-height: 1.7;
        }

        .sports-section {
            background: rgba(104, 183, 123, 0.05);
            border-radius: 20px;
            padding: 3rem;
            margin: 3rem 0;
        }

        .sport-item {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
            padding: 1.5rem;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 12px;
            transition: all 0.3s ease;
        }

        .sport-item:hover {
            background: rgba(255, 255, 255, 0.9);
            transform: translateX(10px);
        }

        .sport-icon {
            font-size: 2.5rem;
            margin-right: 1.5rem;
            color: #6bb77b;
        }

        .achievements {
            background: rgba(72, 139, 96, 0.05);
            border-left: 4px solid #6bb77b;
            padding: 2rem;
            margin: 2rem 0;
            border-radius: 0 10px 10px 0;
        }

        .achievements h4 {
            color: #488b60;
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }

        .achievements ul {
            list-style: none;
            padding-left: 0;
        }

        .achievements li {
            color: #5a6c5d;
            margin-bottom: 0.5rem;
            padding-left: 1.5rem;
            position: relative;
        }

        .achievements li::before {
            content: '●';
            color: #6bb77b;
            position: absolute;
            left: 0;
        }

        .interests-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .interest-card {
            text-align: center;
            padding: 2rem 1rem;
            background: rgba(255, 255, 255, 0.6);
            border-radius: 15px;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .interest-card:hover {
            border-color: rgba(104, 183, 123, 0.3);
            background: rgba(255, 255, 255, 0.8);
            transform: scale(1.05);
        }

        .interest-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #6bb77b;
        }

        .contact-section {
            background: linear-gradient(135deg, #488b60, #6bb77b);
            color: white;
            text-align: center;
            padding: 4rem 2rem;
            border-radius: 20px;
            margin: 3rem 0;
        }

        .contact-section h2 {
            color: white;
            margin-bottom: 2rem;
        }

        .contact-section h2::after {
            background: white;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 3rem;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        @media (max-width: 768px) {
            .nav-links {
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero .subtitle {
                font-size: 1.1rem;
            }

            .grid {
                grid-template-columns: 1fr;
            }

            .contact-info {
                flex-direction: column;
                align-items: center;
                gap: 1rem;
            }

            .sport-item {
                flex-direction: column;
                text-align: center;
            }

            .sport-icon {
                margin-right: 0;
                margin-bottom: 1rem;
            }
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <a href="#" class="logo">Portfolio</a>
            <ul class="nav-links">
                <li><a href="#about">About</a></li>
                <li><a href="#athletics">Athletics</a></li>
                <li><a href="#academics">Academics</a></li>
                <li><a href="#contact">Contact</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="hero">
            <div class="container">
                <h1 class="fade-in">Ilya Cuevas</h1>
                <p class="subtitle fade-in">Student-Athlete & Scholar</p>
                <p class="description fade-in">
                    Dedicated high school student balancing excellence in athletics and academics while pursuing creative passions in poetry and music.
                </p>
            </div>
        </section>

        <section id="about" class="section">
            <div class="container">
                <h2 class="fade-in">About Me</h2>
                <div class="card fade-in">
                    <p>
                        I'm a passionate student-athlete who believes in pursuing excellence both on and off the field. 
                        My journey combines the discipline of competitive sports with academic achievement and creative expression. 
                        Whether I'm scoring goals on the soccer field, crossing finish lines on the track, or crafting verses in poetry, 
                        I approach every challenge with dedication and enthusiasm.
                    </p>
                </div>
            </div>
        </section>

        <section id="athletics" class="section">
            <div class="container">
                <h2 class="fade-in">Athletic Achievements</h2>
                <div class="sports-section fade-in">
                    <div class="sport-item">
                        <div class="sport-icon">⚽</div>
                        <div>
                            <h3>Soccer - Striker (6 years)</h3>
                            <p>Varsity team striker with exceptional finishing ability and goal-scoring instincts. 
                            Known for speed, precision, and clinical finishing in crucial moments.</p>
                        </div>
                    </div>
                    <div class="sport-item">
                        <div class="sport-icon">🏃‍♀️</div>
                        <div>
                            <h3>Track & Field - Sprints (1 year)</h3>
                            <p>Explosive sprinter specializing in 100m and 200m events. New to the sport but 
                            showing rapid improvement and natural speed with tremendous potential.</p>
                        </div>
                    </div>
                </div>

                <div class="achievements fade-in">
                    <h4>Notable Accomplishments</h4>
                    <ul>
                        <li>6 Years Soccer Experience - Striker Position</li>
                        <li>Varsity Soccer Team Leading Goal Scorer</li>
                        <li>Track & Field Sprinter - 100m & 200m Specialist</li>
                        <li>Rapid Improvement in First Year of Track</li>
                        <li>All-District Honorable Mention - Soccer</li>
                        <li>Student-Athlete Academic Excellence Award</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="academics" class="section">
            <div class="container">
                <h2 class="fade-in">Academic Excellence</h2>
                <div class="grid">
                    <div class="card fade-in">
                        <h3>Grade Point Average</h3>
                        <p>Maintaining a strong GPA while balancing demanding athletic commitments. 
                        Consistently on Honor Roll and recognized for academic achievement.</p>
                    </div>
                    <div class="card fade-in">
                        <h3>Favorite Subjects</h3>
                        <p>Excelling in English Literature, Creative Writing, Biology, and History. 
                        Particularly drawn to courses that combine analytical thinking with creative expression.</p>
                    </div>
                    <div class="card fade-in">
                        <h3>Study Approach</h3>
                        <p>Developed effective time management skills to balance rigorous training schedules 
                        with academic responsibilities. Believer in collaborative learning and peer support.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="section">
            <div class="container">
                <h2 class="fade-in">Personal Interests</h2>
                <div class="interests-grid">
                    <div class="interest-card fade-in">
                        <div class="interest-icon">📝</div>
                        <h3>Poetry</h3>
                        <p>Writing original poetry and participating in spoken word events. 
                        Poetry provides a creative outlet for expressing emotions and experiences.</p>
                    </div>
                    <div class="interest-card fade-in">
                        <div class="interest-icon">🎵</div>
                        <h3>Music</h3>
                        <p>Passionate about various music genres and learning instruments. 
                        Music serves as both inspiration and relaxation between training and studies.</p>
                    </div>
                    <div class="interest-card fade-in">
                        <div class="interest-icon">🍽️</div>
                        <h3>Culinary Arts</h3>
                        <p>Enthusiastic about cooking and exploring different cuisines. 
                        Understanding nutrition is essential for athletic performance and overall well-being.</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <script>
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

        // Intersection Observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        // Observe all fade-in elements
        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 4px 30px rgba(72, 139, 96, 0.15)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = '0 2px 20px rgba(72, 139, 96, 0.1)';
            }
        });

        // Add interactive hover effects
        document.querySelectorAll('.card, .interest-card, .sport-item').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = this.classList.contains('interest-card') ? 'scale(1.05)' : 'translateY(-5px)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = this.classList.contains('sport-item') ? 'translateX(0)' : 
                                     this.classList.contains('interest-card') ? 'scale(1)' : 'translateY(0)';
            });
        });
    </script>
</body>
</html>
