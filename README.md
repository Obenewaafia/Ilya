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
            font-family: 'Helvetica Neue', 'Arial', sans-serif;
            line-height: 1.5;
            color: #333;
            background: #fefefe;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: rgba(255, 255, 255, 0.98);
            backdrop-filter: blur(10px);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
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
            padding: 1.2rem 2rem;
        }

        .logo {
            font-size: 1.4rem;
            font-weight: 500;
            color: #000;
            text-decoration: none;
            letter-spacing: -0.5px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2.5rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #555;
            font-weight: 400;
            font-size: 0.95rem;
            transition: color 0.3s ease;
            letter-spacing: 0.3px;
        }

        .nav-links a:hover {
            color: #000;
        }

        main {
            margin-top: 80px;
        }

        .hero {
            padding: 120px 0 80px;
            text-align: center;
            background: #fff;
            margin-bottom: 0;
        }

        .hero h1 {
            font-size: 2.8rem;
            color: #000;
            margin-bottom: 1rem;
            font-weight: 300;
            letter-spacing: -1px;
        }

        .hero .subtitle {
            font-size: 1.1rem;
            color: #666;
            margin-bottom: 2rem;
            font-weight: 300;
            letter-spacing: 0.5px;
        }

        .hero .description {
            font-size: 1rem;
            color: #777;
            max-width: 500px;
            margin: 0 auto;
            line-height: 1.6;
            font-weight: 300;
        }

        .section {
            padding: 80px 0;
            margin-bottom: 0;
        }

        .section h2 {
            font-size: 2rem;
            color: #000;
            text-align: center;
            margin-bottom: 3rem;
            font-weight: 300;
            letter-spacing: -0.5px;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .card {
            background: #fff;
            padding: 2.5rem;
            border-radius: 0;
            box-shadow: none;
            border: 1px solid #f0f0f0;
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: none;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
        }

        .card h3 {
            color: #000;
            margin-bottom: 1rem;
            font-size: 1.1rem;
            font-weight: 400;
            letter-spacing: 0.3px;
        }

        .card p {
            color: #666;
            line-height: 1.6;
            font-weight: 300;
        }

        .sports-section {
            background: #fafafa;
            border-radius: 0;
            padding: 3rem;
            margin: 3rem 0;
        }

        .sport-item {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
            padding: 2rem;
            background: #fff;
            border-radius: 0;
            transition: all 0.3s ease;
            border: 1px solid #f0f0f0;
        }

        .sport-item:hover {
            background: #fff;
            transform: none;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
        }

        .sport-icon {
            font-size: 2rem;
            margin-right: 2rem;
            color: #333;
        }

        .achievements {
            background: #f9f9f9;
            border-left: 3px solid #000;
            padding: 2rem;
            margin: 2rem 0;
            border-radius: 0;
        }

        .achievements h4 {
            color: #000;
            margin-bottom: 1rem;
            font-size: 1.1rem;
            font-weight: 400;
        }

        .achievements ul {
            list-style: none;
            padding-left: 0;
        }

        .achievements li {
            color: #666;
            margin-bottom: 0.8rem;
            padding-left: 1.5rem;
            position: relative;
            font-weight: 300;
        }

        .achievements li::before {
            content: '•';
            color: #000;
            position: absolute;
            left: 0;
            font-weight: 400;
        }

        .interests-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .interest-card {
            text-align: center;
            padding: 2.5rem 2rem;
            background: #fff;
            border-radius: 0;
            transition: all 0.3s ease;
            border: 1px solid #f0f0f0;
        }

        .interest-card:hover {
            border-color: #ddd;
            background: #fff;
            transform: none;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
        }

        .interest-icon {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: #333;
        }

        .contact-section {
            background: #000;
            color: white;
            text-align: center;
            padding: 4rem 2rem;
            border-radius: 0;
            margin: 4rem 0 0;
        }

        .contact-section h2 {
            color: white;
            margin-bottom: 2rem;
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
                    Dedicated high school student balancing excellence in athletics and academics while pursuing passions in reading, writing, and exploring diverse cultures.
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
                        Whether I'm scoring goals on the soccer field, crossing finish lines on the track, or diving into a great book, 
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
                        <div class="interest-icon">📚</div>
                        <h3>Reading & Writing</h3>
                        <p>Passionate about literature and creative writing. 
                        Always exploring new authors and working on personal writing projects.</p>
                    </div>
                    <div class="interest-card fade-in">
                        <div class="interest-icon">🎵</div>
                        <h3>Music</h3>
                        <p>Passionate about various music genres and learning instruments. 
                        Music serves as both inspiration and relaxation between training and studies.</p>
                    </div>
                    <div class="interest-card fade-in">
                        <div class="interest-icon">🌍</div>
                        <h3>Cultural Cuisine</h3>
                        <p>Love exploring and trying new foods from different cultures around the world. 
                        Food is a wonderful way to experience and appreciate diverse traditions.</p>
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
                header.style.background = 'rgba(255, 255, 255, 1)';
                header.style.boxShadow = '0 2px 8px rgba(0, 0, 0, 0.12)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 1px 3px rgba(0, 0, 0, 0.1)';
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
