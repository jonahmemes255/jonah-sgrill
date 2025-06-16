# jonah-sgrill
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jonah's Grill - Premium Grill & Fast Food</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #e67e22;
            --primary-dark: #d35400;
            --secondary: #2c3e50;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --accent: #e74c3c;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f9f9f9;
            color: #333;
            overflow-x: hidden;
        }
        
        /* Animated Navigation */
        header {
            background-color: var(--secondary);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            transform: translateY(0);
            transition: transform 0.3s ease;
        }
        
        header.hide {
            transform: translateY(-100%);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 5%;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .logo {
            color: var(--light);
            font-size: 1.8rem;
            font-weight: 700;
            text-decoration: none;
            display: flex;
            align-items: center;
        }
        
        .logo span {
            color: var(--primary);
        }
        
        .logo i {
            margin-right: 10px;
            color: var(--primary);
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 2rem;
            position: relative;
        }
        
        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: color 0.3s;
            position: relative;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background-color: var(--primary);
            bottom: -5px;
            left: 0;
            transition: width 0.3s;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        .nav-links a:hover {
            color: var(--primary);
        }
        
        .hamburger {
            display: none;
            cursor: pointer;
        }
        
        .hamburger div {
            width: 25px;
            height: 3px;
            background-color: var(--light);
            margin: 5px;
            transition: all 0.3s ease;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1600891964599-f61ba0e24092?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80') no-repeat center center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding: 0 2rem;
        }
        
        .hero-content {
            max-width: 800px;
            animation: fadeIn 1.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            line-height: 1.6;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--primary);
            color: white;
            padding: 0.8rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }
        
        .btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            margin-left: 1rem;
        }
        
        .btn-outline:hover {
            background-color: var(--primary);
        }
        
        /* About Section */
        .section {
            padding: 6rem 5%;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--secondary);
            display: inline-block;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background-color: var(--primary);
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .about-content {
            display: flex;
            align-items: center;
            gap: 4rem;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--secondary);
        }
        
        .about-text p {
            margin-bottom: 1.5rem;
            line-height: 1.8;
            color: #555;
        }
        
        .about-image {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            transition: transform 0.5s;
        }
        
        .about-image:hover {
            transform: scale(1.03);
        }
        
        .about-image img {
            width: 100%;
            height: auto;
            display: block;
        }
        
        /* Menu Section */
        .menu {
            background-color: #f5f5f5;
        }
        
        .menu-items {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .menu-item {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
            position: relative;
        }
        
        .menu-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        
        .menu-item-img {
            height: 200px;
            overflow: hidden;
        }
        
        .menu-item-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .menu-item:hover .menu-item-img img {
            transform: scale(1.1);
        }
        
        .menu-item-content {
            padding: 1.5rem;
        }
        
        .menu-item-title {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
        }
        
        .menu-item-title h3 {
            font-size: 1.3rem;
            color: var(--secondary);
        }
        
        .menu-item-title span {
            color: var(--primary);
            font-weight: 700;
        }
        
        .menu-item p {
            color: #666;
            line-height: 1.6;
            margin-bottom: 1.5rem;
        }
        
        .menu-item-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: var(--accent);
            color: white;
            padding: 0.3rem 1rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        /* Contact Section */
        .contact {
            background-color: var(--secondary);
            color: white;
        }
        
        .contact .section-title h2 {
            color: white;
        }
        
        .contact-content {
            display: flex;
            gap: 4rem;
        }
        
        .contact-info {
            flex: 1;
        }
        
        .contact-info h3 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
        }
        
        .contact-info p {
            margin-bottom: 2rem;
            line-height: 1.8;
        }
        
        .contact-details {
            margin-top: 2rem;
        }
        
        .contact-detail {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .contact-detail i {
            font-size: 1.5rem;
            color: var(--primary);
            margin-right: 1.5rem;
            width: 30px;
            text-align: center;
        }
        
        .contact-form {
            flex: 1;
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--secondary);
            font-weight: 500;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border 0.3s;
        }
        
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
        }
        
        .form-group textarea {
            height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            text-align: center;
            padding: 3rem 0;
        }
        
        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 5%;
        }
        
        .social-links {
            margin: 2rem 0;
        }
        
        .social-links a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            margin: 0 0.5rem;
            color: white;
            line-height: 40px;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background-color: var(--primary);
            transform: translateY(-5px);
        }
        
        .copyright {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
        }
        
        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background-color: var(--primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
            z-index: 999;
        }
        
        .back-to-top.active {
            opacity: 1;
            visibility: visible;
        }
        
        .back-to-top:hover {
            background-color: var(--primary-dark);
            transform: translateY(-5px);
        }
        
        /* Responsive Design */
        @media (max-width: 992px) {
            .about-content, .contact-content {
                flex-direction: column;
            }
            
            .about-image, .about-text, .contact-info, .contact-form {
                width: 100%;
            }
            
            .btn-outline {
                margin-left: 0;
                margin-top: 1rem;
            }
        }
        
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .nav-links {
                position: absolute;
                right: 0;
                top: 80px;
                background-color: var(--secondary);
                width: 100%;
                flex-direction: column;
                align-items: center;
                padding: 2rem 0;
                clip-path: circle(0px at 90% -10%);
                transition: all 0.5s ease-out;
                pointer-events: none;
            }
            
            .nav-links.active {
                clip-path: circle(1000px at 90% -10%);
                pointer-events: all;
            }
            
            .nav-links li {
                margin: 1rem 0;
            }
            
            .hamburger {
                display: block;
            }
            
            .hamburger.active div:nth-child(1) {
                transform: rotate(-45deg) translate(-5px, 6px);
            }
            
            .hamburger.active div:nth-child(2) {
                opacity: 0;
            }
            
            .hamburger.active div:nth-child(3) {
                transform: rotate(45deg) translate(-5px, -6px);
            }
        }
        
        @media (max-width: 576px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
            
            .btn {
                padding: 0.6rem 1.5rem;
            }
        }
        
        /* Animation Classes */
        .fade-in {
            animation: fadeIn 1s ease forwards;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .delay-1 {
            animation-delay: 0.2s;
        }
        
        .delay-2 {
            animation-delay: 0.4s;
        }
        
        .delay-3 {
            animation-delay: 0.6s;
        }
    </style>
</head>
<body>
    <!-- Header with Animated Navigation -->
    <header id="header">
        <nav>
            <a href="#" class="logo"><i class="fas fa-fire"></i>Jonah's <span>Grill</span></a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="hamburger">
                <div></div>
                <div></div>
                <div></div>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Premium Grill & Fast Food</h1>
            <p>Experience the taste of perfection with our expertly grilled dishes made from the freshest ingredients. From juicy chicken to crispy gizzards, we've got your cravings covered.</p>
            <div>
                <a href="#menu" class="btn">View Menu</a>
                <a href="https://wa.me/256747337540?text=Send%20me%20the%20menu%20%F0%9F%98%8B" class="btn btn-outline">Order Now</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section" id="about">
        <div class="section-title">
            <h2>About Us</h2>
        </div>
        <div class="about-content">
            <div class="about-text">
                <h3>Bringing Flavor to Beer O'clock</h3>
                <p>Welcome to Jonah's Grill, where passion meets flavor. Located at Beer O'clock, we specialize in serving mouth-watering grilled dishes and fast food that will leave you craving for more.</p>
                <p>Our secret lies in the perfect blend of spices, fresh ingredients, and the art of grilling that has been perfected over time. Every dish is prepared with care and attention to detail.</p>
                <p>Whether you're looking for a quick bite or a satisfying meal, Jonah's Grill is your go-to spot for delicious food in a welcoming atmosphere.</p>
            </div>
            <div class="about-image">
                <img src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1374&q=80" alt="Jonah's Grill Interior">
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section class="section menu" id="menu">
        <div class="section-title">
            <h2>Our Menu</h2>
        </div>
        <div class="menu-items">
            <!-- Chips and Chicken -->
            <div class="menu-item fade-in">
                <div class="menu-item-img">
                    <img src="https://images.unsplash.com/photo-1518492104633-130d0cc84637">
                </div>
                <div class="menu-item-content">
                    <div class="menu-item-title">
                        <h3>Whole Grilled Chicken</h3>
                        <span>UGX 25,000</span>
                    </div>
                    <p>Crispy golden fries served with our signature grilled chicken, marinated in special spices and cooked to perfection.</p>
                    <a href="https://wa.me/256747337540?text=Send%20me%20the%20menu%20%F0%9F%98%8B" class="btn">Order Now</a>
                </div>
            </div>
            
            <!-- Chips and Gizzards -->
            <div class="menu-item fade-in delay-1">
                <div class="menu-item-badge">Popular</div>
                <div class="menu-item-img">
                    <img src="https://images.unsplash.com/photo-1603360946369-dc9bb6258143">
                </div>
                <div class="menu-item-content">
                    <div class="menu-item-title">
                        <h3>Chips and Gizzards</h3>
                        <span>UGX 12,000</span>
                    </div>
                    <p>Perfectly seasoned and crispy gizzards paired with our golden fries. A crunchy delight you won't forget!</p>
                    <a href="https://wa.me/256747337540?text=Send%20me%20the%20menu%20%F0%9F%98%8B" class="btn">Order Now</a>
                </div>
            </div>
            
            <!-- Plain Chips -->
            <div class="menu-item fade-in delay-2">
                <div class="menu-item-img">
                    <img src="https://images.unsplash.com/photo-1576107232684-1279f390859f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1336&q=80" alt="Plain Chips">
                </div>
                <div class="menu-item-content">
                    <div class="menu-item-title">
                        <h3>Plain Chips</h3>
                        <span>UGX 8,000</span>
                    </div>
                    <p>Classic golden fries, crispy on the outside and fluffy on the inside, served with your choice of dipping sauce.</p>
                    <a href="https://wa.me/256747337540?text=Send%20me%20the%20menu%20%F0%9F%98%8B" class="btn">Order Now</a>
                </div>
            </div>
            
            <!-- Grilled Chicken -->
            <div class="menu-item fade-in">
                <div class="menu-item-badge">New</div>
                <div class="menu-item-img">
                    <img src="https://images.unsplash.com/photo-1603360946369-dc9bb6258143?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Grilled Chicken">
                </div>
                <div class="menu-item-content">
                    <div class="menu-item-title">
                        <h3>Grilled Chicken</h3>
                        <span>UGX 18,000</span>
                    </div>
                    <p>Juicy, tender chicken marinated in our secret spice blend and grilled to perfection. Served with your choice of sides.</p>
                    <a href="https://wa.me/256747337540?text=Send%20me%20the%20menu%20%F0%9F%98%8B" class="btn">Order Now</a>
                </div>
            </div>
            
            <!-- Beef Skewers -->
            <div class="menu-item fade-in delay-1">
                <div class="menu-item-img">
                    <img src="https://images.unsplash.com/photo-1551504734-5ee1c4a1479b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Beef Skewers">
                </div>
                <div class="menu-item-content">
                    <div class="menu-item-title">
                        <h3>Beef Skewers</h3>
                        <span>UGX 20,000</span>
                    </div>
                    <p>Tender beef cubes marinated in special spices, skewered and grilled to smoky perfection. Served with grilled vegetables.</p>
                    <a href="https://wa.me/256747337540?text=Send%20me%20the%20menu%20%F0%9F%98%8B" class="btn">Order Now</a>
                </div>
            </div>
            
            <!-- Pork Ribs -->
            <div class="menu-item fade-in delay-2">
                <div class="menu-item-badge">Chef's Special</div>
                <div class="menu-item-img">
                    <img src="https://images.unsplash.com/photo-1544025162-d76694265947?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1469&q=80" alt="Pork Ribs">
                </div>
                <div class="menu-item-content">
                    <div class="menu-item-title">
                        <h3>Pork Ribs</h3>
                        <span>UGX 22,000</span>
                    </div>
                    <p>Fall-off-the-bone tender pork ribs glazed with our signature BBQ sauce. A must-try for meat lovers!</p>
                    <a href="https://wa.me/256747337540?text=Send%20me%20the%20menu%20%F0%9F%98%8B" class="btn">Order Now</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section contact" id="contact">
        <div class="section-title">
            <h2>Contact Us</h2>
        </div>
        <div class="contact-content">
            <div class="contact-info">
                <h3>Get In Touch</h3>
                <p>Have questions or want to place an order? Reach out to us through any of the following channels or fill out the form and we'll get back to you as soon as possible.</p>
                
                <div class="contact-details">
                    <div class="contact-detail">
                        <i class="fas fa-map-marker-alt"></i>
                        <div>
                            <h4>Location</h4>
                            <p>Beer O'clock, Kampala, Uganda</p>
                        </div>
                    </div>
                    <div class="contact-detail">
                        <i class="fas fa-phone-alt"></i>
                        <div>
                            <h4>Call Us</h4>
                            <p>+256 747 337 540</p>
                        </div>
                    </div>
                    <div class="contact-detail">
                        <i class="fas fa-envelope"></i>
                        <div>
                            <h4>Email Us</h4>
                            <p>jonahmonrider@gmail.com</p>
                        </div>
                    </div>
                    <div class="contact-detail">
                        <i class="fas fa-clock"></i>
                        <div>
                            <h4>Opening Hours</h4>
                            <p>Monday - Sunday: 10:00 AM - 10:00 PM</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="contact-form">
                <form id="orderForm">
                    <div class="form-group">
                        <label for="name">Your Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Your Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="phone">Phone Number</label>
                        <input type="tel" id="phone" name="phone" required>
                    </div>
                    <div class="form-group">
                        <label for="order">Your Order</label>
                        <textarea id="order" name="order" placeholder="Please specify what you'd like to order and any special instructions..." required></textarea>
                    </div>
                    <button type="submit" class="btn">Place Order</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <a href="#" class="logo"><i class="fas fa-fire"></i>Jonah's <span>Grill</span></a>
            <p>Premium Grill & Fast Food at Beer O'clock</p>
            <div class="social-links">
                <a href="https://www.facebook.com/jonah.monrider"><i class="fab fa-facebook-f"></i></a>
                <a href="https://www.tiktok.com/@jonah_memes_1?_t=ZM-8xAxL7lBSbe&_r=1"><i class="fab fa-twitter"></i></a>
                <a href="https://www.instagram.com/memesjonah?igsh=YzljYTk1ODg3Zg=="><i class="fab fa-instagram"></i></a>
                <a href="https://wa.me/+256747337540"><i class="fab fa-whatsapp"></i></a>
            </div>
            <p class="copyright">&copy; 2023 Jonah's Grill. All Rights Reserved.</p>
        </div>
    </footer>

    <!-- Back to Top Button -->
    <div class="back-to-top" id="backToTop">
        <i class="fas fa-arrow-up"></i>
    </div>

    <!-- JavaScript -->
    <script>
        // Mobile Navigation
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');
        const links = document.querySelectorAll('.nav-links li');
        
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
        });
        
        links.forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.classList.remove('active');
            });
        });
        
        // Hide Header on Scroll Down
        let lastScroll = 0;
        const header = document.getElementById('header');
        
        window.addEventListener('scroll', () => {
            const currentScroll = window.pageYOffset;
            
            if (currentScroll <= 0) {
                header.classList.remove('hide');
                return;
            }
            
            if (currentScroll > lastScroll && !header.classList.contains('hide')) {
                header.classList.add('hide');
            } else if (currentScroll < lastScroll && header.classList.contains('hide')) {
                header.classList.remove('hide');
            }
            
            lastScroll = currentScroll;
        });
        
        // Back to Top Button
        const backToTopBtn = document.getElementById('backToTop');
        
        window.addEventListener('scroll', () => {
            if (window.pageYOffset > 300) {
                backToTopBtn.classList.add('active');
            } else {
                backToTopBtn.classList.remove('active');
            }
        });
        
        backToTopBtn.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // Form Submission
        const orderForm = document.getElementById('orderForm');
        
        orderForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const phone = document.getElementById('phone').value;
            const order = document.getElementById('order').value;
            
            // Here you would typically send this data to your server
            // For demonstration, we'll just show an alert
            alert(`Thank you, ${name}! Your order has been received. We'll contact you shortly at ${phone} or ${email} to confirm.`);
            
            // Reset form
            orderForm.reset();
        });
        
        // Animate menu items on scroll
        const menuItems = document.querySelectorAll('.menu-item');
        
        const animateOnScroll = () => {
            menuItems.forEach(item => {
                const itemPosition = item.getBoundingClientRect().top;
                const screenPosition = window.innerHeight / 1.3;
                
                if (itemPosition < screenPosition) {
                    item.classList.add('fade-in');
                }
            });
        };
        
        window.addEventListener('scroll', animateOnScroll);
        window.addEventListener('load', animateOnScroll);
    </script>
</body>
</html>
