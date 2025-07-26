# Handyhub-<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HandyConnect - Find Local Service Providers</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #2c6fbb;
            --secondary: #ff6b35;
            --dark: #333;
            --light: #f8f9fa;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
        }
        
        .logo i {
            color: var(--secondary);
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: var(--primary);
        }
        
        .auth-buttons {
            display: flex;
            gap: 15px;
        }
        
        .btn {
            padding: 10px 20px;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
            font-size: 16px;
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: white;
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        
        .btn-primary:hover {
            background-color: #1a5a9e;
        }
        
        .btn-outline:hover {
            background-color: var(--primary);
            color: white;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary) 0%, #1a5a9e 100%);
            color: white;
            padding: 80px 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
        }
        
        .search-box {
            background: white;
            border-radius: 50px;
            padding: 10px;
            display: flex;
            max-width: 700px;
            margin: 0 auto;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .search-box input {
            flex: 1;
            border: none;
            padding: 15px 20px;
            border-radius: 50px 0 0 50px;
            font-size: 16px;
        }
        
        .search-box button {
            background: var(--secondary);
            color: white;
            border: none;
            padding: 0 30px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
        }
        
        /* Services Section */
        .section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--dark);
            margin-bottom: 15px;
        }
        
        .section-title p {
            color: #666;
            max-width: 700px;
            margin: 0 auto;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s, box-shadow 0.3s;
            text-align: center;
            padding: 30px 20px;
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .service-icon {
            width: 80px;
            height: 80px;
            background: rgba(44, 111, 187, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 30px;
            color: var(--primary);
        }
        
        .service-card h3 {
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        /* How It Works */
        .how-it-works {
            background-color: var(--light);
        }
        
        .steps {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .step {
            flex: 1;
            min-width: 250px;
            text-align: center;
            padding: 30px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .step-number {
            width: 50px;
            height: 50px;
            background: var(--primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            font-weight: bold;
            margin: 0 auto 20px;
        }
        
        /* Providers Section */
        .providers-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .provider-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }
        
        .provider-card:hover {
            transform: translateY(-5px);
        }
        
        .provider-header {
            padding: 20px;
            background: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .provider-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            font-weight: bold;
        }
        
        .provider-info h3 {
            margin-bottom: 5px;
        }
        
        .provider-info p {
            opacity: 0.9;
            font-size: 14px;
        }
        
        .provider-body {
            padding: 20px;
        }
        
        .provider-services {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 15px 0;
        }
        
        .service-tag {
            background: rgba(44, 111, 187, 0.1);
            color: var(--primary);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 14px;
        }
        
        .provider-rating {
            color: var(--warning);
            margin: 10px 0;
        }
        
        .provider-footer {
            padding: 15px 20px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: space-between;
        }
        
        /* Testimonials */
        .testimonials {
            background: linear-gradient(135deg, var(--primary) 0%, #1a5a9e 100%);
            color: white;
        }
        
        .testimonials .section-title h2 {
            color: white;
        }
        
        .testimonials .section-title p {
            color: rgba(255,255,255,0.8);
        }
        
        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .testimonial-card {
            background: rgba(255,255,255,0.1);
            border-radius: 10px;
            padding: 30px;
            backdrop-filter: blur(10px);
        }
        
        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
            position: relative;
        }
        
        .testimonial-text::before {
            content: """;
            font-size: 60px;
            position: absolute;
            top: -20px;
            left: -15px;
            opacity: 0.2;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }
        
        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background: var(--secondary);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #bbb;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255,255,255,0.1);
            color: white;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background: var(--secondary);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #bbb;
            font-size: 14px;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                gap: 20px;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .search-box {
                flex-direction: column;
                border-radius: 10px;
                padding: 0;
            }
            
            .search-box input {
                border-radius: 10px 10px 0 0;
                padding: 15px;
            }
            
            .search-box button {
                border-radius: 0 0 10px 10px;
                padding: 15px;
            }
            
            .steps {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo">
                    <i class="fas fa-tools"></i>
                    <span>HandyConnect</span>
                </div>
                <div class="nav-links">
                    <a href="#">Home</a>
                    <a href="#">Services</a>
                    <a href="#">Providers</a>
                    <a href="#">How It Works</a>
                    <a href="#">Contact</a>
                </div>
                <div class="auth-buttons">
                    <button class="btn btn-outline">Login</button>
                    <button class="btn btn-primary">Sign Up</button>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Find Trusted Local Service Providers</h1>
            <p>Connect with skilled plumbers, electricians, cleaners, and more. Book services in minutes with verified professionals.</p>
            <div class="search-box">
                <input type="text" placeholder="What service do you need? (e.g. plumber, cleaner, electrician)">
                <button><i class="fas fa-search"></i> Find Services</button>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="section">
        <div class="container">
            <div class="section-title">
                <h2>Popular Services</h2>
                <p>Find trusted professionals for all your home and office needs</p>
            </div>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-faucet"></i>
                    </div>
                    <h3>Plumbing</h3>
                    <p>Leaky pipes, clogged drains, faucet repairs and installations</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <h3>Electrical</h3>
                    <p>Wiring, outlet repairs, lighting installation and electrical safety</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-broom"></i>
                    </div>
                    <h3>Cleaning</h3>
                    <p>Regular cleaning, deep cleaning, move-in/out cleaning</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-paint-roller"></i>
                    </div>
                    <h3>Painting</h3>
                    <p>Interior and exterior painting, touch-ups, and color consultation</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-hammer"></i>
                    </div>
                    <h3>Handyman</h3>
                    <p>Furniture assembly, minor repairs, mounting and installations</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-tree"></i>
                    </div>
                    <h3>Gardening</h3>
                    <p>Lawn care, tree trimming, garden design and maintenance</p>
                </div>
            </div>
        </div>
    </section>

    <!-- How It Works -->
    <section class="section how-it-works">
        <div class="container">
            <div class="section-title">
                <h2>How It Works</h2>
                <p>Getting quality service has never been easier</p>
            </div>
            <div class="steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Search for Service</h3>
                    <p>Enter your location and the service you need. Browse verified professionals.</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Compare & Choose</h3>
                    <p>Review profiles, ratings, and pricing. Select the best provider for your needs.</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Book & Confirm</h3>
                    <p>Schedule a time that works for you. Receive confirmation and reminders.</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Get Service Done</h3>
                    <p>Professional arrives on time and completes the job to your satisfaction.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Top Providers -->
    <section class="section">
        <div class="container">
            <div class="section-title">
                <h2>Top Rated Providers</h2>
                <p>Meet our most trusted service professionals</p>
            </div>
            <div class="providers-grid">
                <div class="provider-card">
                    <div class="provider-header">
                        <div class="provider-avatar">JD</div>
                        <div class="provider-info">
                            <h3>John Davis</h3>
                            <p>Licensed Plumber</p>
                        </div>
                    </div>
                    <div class="provider-body">
                        <p>Specializing in residential plumbing with 15+ years experience. Emergency services available.</p>
                        <div class="provider-services">
                            <span class="service-tag">Plumbing</span>
                            <span class="service-tag">Emergency</span>
                            <span class="service-tag">Installations</span>
                        </div>
                        <div class="provider-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                            <span>(127 reviews)</span>
                        </div>
                    </div>
                    <div class="provider-footer">
                        <span>$45/hr</span>
                        <button class="btn btn-primary">Book Now</button>
                    </div>
                </div>
                
                <div class="provider-card">
                    <div class="provider-header">
                        <div class="provider-avatar">SR</div>
                        <div class=