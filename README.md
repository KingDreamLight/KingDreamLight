<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CulturEats - Taste the World, One Box at a Time</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
    <script src="https://kit.fontawesome.com/your-fontawesome-kit.js" crossorigin="anonymous"></script>
    <style>
        :root {
            --primary-color: #ff6b6b;
            --secondary-color: #4ecdc4;
            --text-color: #2d3436;
            --background-color: #f9f9f9;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Roboto', sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--background-color);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background-color: #fff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary-color);
        }

        .nav-links {
            list-style: none;
            display: flex;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://source.unsplash.com/1600x900/?food,culture') no-repeat center center/cover;
            color: #fff;
            text-align: center;
        }

        .hero-content {
            max-width: 800px;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4rem;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease-out both;
        }

        .hero .slogan {
            font-size: 1.5rem;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .btn {
            display: inline-block;
            background-color: var(--primary-color);
            color: #fff;
            padding: 12px 30px;
            text-decoration: none;
            border-radius: 30px;
            transition: background-color 0.3s ease;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .btn:hover {
            background-color: #ff4757;
        }

        section {
            padding: 100px 0;
        }

        h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            margin-bottom: 50px;
            text-align: center;
            color: var(--primary-color);
        }

        .features {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }

        .feature-card {
            flex-basis: calc(33.333% - 30px);
            background-color: #fff;
            border-radius: 10px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-card i {
            font-size: 3rem;
            color: var(--secondary-color);
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary-color);
        }

        #how-it-works {
            background-color: var(--secondary-color);
            color: #fff;
        }

        .steps {
            display: flex;
            justify-content: space-between;
            counter-reset: step;
        }

        .step {
            flex-basis: calc(25% - 30px);
            text-align: center;
            position: relative;
        }

        .step::before {
            counter-increment: step;
            content: counter(step);
            display: block;
            width: 50px;
            height: 50px;
            background-color: #fff;
            color: var(--secondary-color);
            border-radius: 50%;
            line-height: 50px;
            font-size: 1.5rem;
            font-weight: 700;
            margin: 0 auto 20px;
        }

        .step::after {
            content: '';
            position: absolute;
            top: 25px;
            right: -50%;
            width: 100%;
            height: 2px;
            background-color: #fff;
            z-index: -1;
        }

        .step:last-child::after {
            display: none;
        }

        .testimonials {
            text-align: center;
        }

        .testimonial-slider {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }

        .testimonial {
            background-color: #fff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            margin: 20px;
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        .testimonial.active {
            opacity: 1;
        }

        .testimonial img {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            margin-bottom: 20px;
        }

        .testimonial-author {
            font-weight: 700;
            color: var(--primary-color);
        }

        .slider-nav {
            margin-top: 20px;
        }

        .slider-nav button {
            background-color: var(--primary-color);
            color: #fff;
            border: none;
            padding: 10px 20px;
            margin: 0 10px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .slider-nav button:hover {
            background-color: #ff4757;
        }

        footer {
            background-color: var(--text-color);
            color: #fff;
            text-align: center;
            padding: 40px 0;
        }

        .social-links {
            margin-bottom: 20px;
        }

        .social-links a {
            color: #fff;
            font-size: 1.5rem;
            margin: 0 10px;
            transition: color 0.3s ease;
        }

        .social-links a:hover {
            color: var(--primary-color);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media screen and (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 3rem;
            }

            .feature-card, .step {
                flex-basis: 100%;
            }

            .step::after {
                display: none;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <div class="logo">CulturEats</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#how-it-works">How It Works</a></li>
                <li><a href="#testimonials">Testimonials</a></li>
                <li><a href="#" class="btn">Subscribe Now</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>CulturEats</h1>
            <p class="slogan">Taste the World, One Box at a Time</p>
            <a href="#" class="btn">Start Your Culinary Journey</a>
        </div>
    </section>

    <section id="features">
        <div class="container">
            <h2>Why Choose CulturEats?</h2>
            <div class="features">
                <div class="feature-card">
                    <i class="fas fa-globe-americas"></i>
                    <h3>Global Flavors</h3>
                    <p>Experience authentic cuisines from around the world, delivered right to your doorstep.</p>
                </div>
                <div class="feature-card">
                    <i class="fas fa-utensils"></i>
                    <h3>Premium Ingredients</h3>
                    <p>We source the finest, freshest ingredients to ensure restaurant-quality meals at home.</p>
                </div>
                <div class="feature-card">
                    <i class="fas fa-book-open"></i>
                    <h3>Cultural Education</h3>
                    <p>Learn about different cultures through food, with detailed recipe cards and fun facts.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="how-it-works">
        <div class="container">
            <h2>How It Works</h2>
            <div class="steps">
                <div class="step">
                    <h3>Choose Your Plan</h3>
                    <p>Select from our flexible subscription options.</p>
                </div>
                <div class="step">
                    <h3>Receive Your Box</h3>
                    <p>Get a curated box of ingredients and recipes monthly.</p>
                </div>
                <div class="step">
                    <h3>Cook & Enjoy</h3>
                    <p>Follow our easy recipes to create delicious meals.</p>
                </div>
                <div class="step">
                    <h3>Share & Repeat</h3>
                    <p>Share your experience and get ready for next month's adventure!</p>
                </div>
            </div>
        </div>
    </section>

    <section id="testimonials">
        <div class="container">
            <h2>What Our Customers Say</h2>
            <div class="testimonial-slider">
                <div class="testimonial active">
                    <img src="https://i.pravatar.cc/150?img=1" alt="Customer 1">
                    <p>"CulturEats has transformed our family dinners. We've learned so much about different cultures through food!"</p>
                    <p class="testimonial-author">- Sarah J.</p>
                </div>
                <div class="testimonial">
                    <img src="https://i.pravatar.cc/150?img=2" alt="Customer 2">
                    <p>"The quality of ingredients is outstanding. I feel like a world-class chef in my own kitchen!"</p>
                    <p class="testimonial-author">- Michael T.</p>
                </div>
                <div class="testimonial">
                    <img src="https://i.pravatar.cc/150?img=3" alt="Customer 3">
                    <p>"I love the cultural insights that come with each recipe. It's like traveling the world without leaving home."</p>
                    <p class="testimonial-author">- Emma L.</p>
                </div>
            </div>
            <div class="slider-nav">
                <button id="prevBtn">Previous</button>
                <button id="nextBtn">Next</button>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#"><i class="fab fa-facebook"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-youtube"></i></a>
            </div>
            <p>&copy; 2023 CulturEats. All rights reserved.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const testimonials = document.querySelectorAll('.testimonial');
            const prevBtn = document.getElementById('prevBtn');
            const nextBtn = document.getElementById('nextBtn');
            let currentTestimonial = 0;

            function showTestimonial(index) {
                testimonials.forEach(testimonial => testimonial.classList.remove('active'));
                testimonials[index].classList.add('active');
            }

            prevBtn.addEventListener('click', () => {
                currentTestimonial = (currentTestimonial - 1 + testimonials.length) % testimonials.length;
                showTestimonial(currentTestimonial);
            });

            nextBtn.addEventListener('click', () => {
                currentTestimonial = (currentTestimonial + 1) % testimonials.length;
                showTestimonial(currentTestimonial);
            });

            // Smooth scrolling for navigation links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });

            // Parallax effect for hero section
            window.addEventListener('scroll', () => {
                const scrollPosition = window.pageYOffset;
                document.querySelector('.hero').style.backgroundPositionY = scrollPosition * 0.7 + 'px';
            });

            // Animate elements on scroll
            const animateOnScroll = () => {
                const elements = document.querySelectorAll('.feature-card, .step, .testimonial');
                elements.forEach(element => {
                    const elementPosition = element.getBoundingClientRect().top;
                    const screenPosition = window.innerHeight / 1.3;
                    if (elementPosition < screenPosition) {
                        element.style.opacity = '1';
                        element.style.transform = 'translateY(0)';
                    }
                });
            };

            window.addEventListener('scroll', animateOnScroll);
            animateOnScroll(); // Initial check on page load
        });
    </script>
</body>
</html>
