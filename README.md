<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clear Sky - Your One-Stop Shop</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #1a1a1a;
            color: #e0e0e0;
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, #2a2a2a 0%, #0a0a0a 100%);
            padding: 1.5rem 5%;
            box-shadow: 0 4px 20px rgba(0,0,0,0.5);
        }

        .header-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .logo {
            font-size: 2rem;
            font-weight: 700;
            color: white;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo img {
            height: 60px;
            width: auto;
        }

        .phone {
            font-size: 1.2rem;
            font-weight: 600;
            color: white;
        }

        nav {
            background: #0a0a0a;
            padding: 1rem 5%;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        .nav-links {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            gap: 3rem;
            list-style: none;
            flex-wrap: wrap;
        }

        .nav-links li {
            color: #e0e0e0;
            font-weight: 600;
            cursor: pointer;
            transition: color 0.3s;
        }

        .nav-links li:hover {
            color: #fbbf24;
        }

        .hero {
            background: linear-gradient(135deg, #2a2a2a 0%, #0a0a0a 100%);
            padding: 6rem 5%;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '🛒';
            position: absolute;
            font-size: 20rem;
            opacity: 0.05;
            top: -50px;
            right: -50px;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            color: white;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            color: #cbd5e1;
        }

        .cta-button {
            display: inline-block;
            padding: 1.2rem 3rem;
            background: #fbbf24;
            color: #0a0a0a;
            text-decoration: none;
            font-weight: 700;
            border-radius: 50px;
            font-size: 1.1rem;
            transition: all 0.3s;
            box-shadow: 0 8px 25px rgba(251, 191, 36, 0.4);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 35px rgba(251, 191, 36, 0.6);
            background: #f59e0b;
        }

        .categories {
            padding: 5rem 5%;
            background: #1a1a1a;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #e0e0e0;
            font-weight: 700;
            position: relative;
            padding-bottom: 1rem;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, #fbbf24, #f59e0b);
            border-radius: 2px;
        }

        .category-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .category-card {
            background: #2a2a2a;
            border: 2px solid #3a3a3a;
            border-radius: 20px;
            padding: 3rem 2rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: block;
        }

        .category-card:hover {
            transform: translateY(-10px);
            border-color: #fbbf24;
            box-shadow: 0 10px 30px rgba(251, 191, 36, 0.3);
        }

        .category-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        .category-name {
            font-size: 1.3rem;
            font-weight: 600;
            color: #e0e0e0;
        }

        .products {
            padding: 5rem 5%;
            background: #1a1a1a;
        }

        .product-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: #2a2a2a;
            border: 2px solid #3a3a3a;
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.3s;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-10px);
            border-color: #fbbf24;
            box-shadow: 0 10px 30px rgba(251, 191, 36, 0.3);
        }

        .product-image {
            width: 100%;
            height: 350px;
            object-fit: cover;
            background: #3a3a3a;
        }

        .product-image.tissue {
            height: 350px;
            object-fit: contain;
        }

        .product-image.water {
            height: 350px;
            object-fit: contain;
        }

        .product-info {
            padding: 1.5rem;
            text-align: center;
        }

        .product-name {
            font-size: 1.2rem;
            font-weight: 600;
            color: #e0e0e0;
            margin-bottom: 0.5rem;
        }

        .product-price {
            font-size: 1.5rem;
            color: #fbbf24;
            font-weight: 700;
        }

        .call-for-price {
            display: inline-block;
            margin-top: 0.5rem;
            padding: 0.5rem 1rem;
            background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
            color: #0a0a0a;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 600;
            animation: pulse 2s infinite;
            text-decoration: none;
        }

        @keyframes pulse {
            0%, 100% {
                box-shadow: 0 0 0 0 rgba(251, 191, 36, 0.7);
            }
            50% {
                box-shadow: 0 0 0 10px rgba(251, 191, 36, 0);
            }
        }

        .deals {
            background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
            padding: 5rem 5%;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .deals::before {
            content: '💎';
            position: absolute;
            font-size: 15rem;
            opacity: 0.1;
            top: -30px;
            left: -30px;
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .deals h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #0a0a0a;
        }

        .features {
            padding: 5rem 5%;
            background: #1a1a1a;
        }

        .feature-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            text-align: center;
        }

        .feature-item {
            padding: 2rem;
        }

        .feature-icon {
            font-size: 3.5rem;
            margin-bottom: 1rem;
        }

        .feature-title {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: #fbbf24;
        }

        .feature-text {
            color: #9ca3af;
        }

        footer {
            background: #0a0a0a;
            padding: 3rem 5%;
            border-top: 1px solid #fbbf24;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #fbbf24;
            font-size: 1.2rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section li {
            margin-bottom: 0.5rem;
            color: #9ca3af;
            cursor: pointer;
            transition: color 0.3s;
        }

        .footer-section li:hover {
            color: #fbbf24;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            margin-top: 2rem;
            border-top: 1px solid #3a3a3a;
            color: #9ca3af;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }

            .header-content {
                justify-content: center;
                text-align: center;
            }

            .nav-links {
                gap: 1.5rem;
            }

            .category-grid, .product-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="header-content">
            <div class="logo">
                <img src="images/logo.png" alt="Clear Sky Logo">
                Clear Sky
            </div>
            <div class="phone">📞 +971 56 218 0707</div>
        </div>
    </header>

    <nav>
        <ul class="nav-links">
            <li>Tissues</li>
            <li>Bottled Water</li>
            <li>T-Shirts</li>
            <li>Hot Deals</li>
        </ul>
    </nav>

    <section class="hero">
        <div class="hero-content">
            <h1>Everything You Need, All in One Place</h1>
            <p>Quality Products at Unbeatable Prices</p>
            <a href="tel:+971562180707" class="cta-button">📞 Call Now: +971 56 218 0707</a>
        </div>
    </section>

    <section class="categories">
        <h2 class="section-title">Shop by Category</h2>
        <div class="category-grid">
            <a href="#tissues" class="category-card">
                <div class="category-icon">🧻</div>
                <div class="category-name">Tissues</div>
            </a>
            <a href="#water" class="category-card">
                <div class="category-icon">💧</div>
                <div class="category-name">Bottled Water</div>
            </a>
            <a href="#tshirts" class="category-card">
                <div class="category-icon">👕</div>
                <div class="category-name">T-Shirts</div>
            </a>
        </div>
    </section>

    <section class="products" id="tissues">
        <h2 class="section-title">Tissues Collection</h2>
        <div class="product-grid">
            <div class="product-card">
                <img src="images/tissue1.jpg" alt="Premium Tissue Box" class="product-image tissue">
                <div class="product-info">
                    <div class="product-name">Premium Tissue Box</div>
                    <div class="product-price">
                        <a href="tel:+971562180707" class="call-for-price">📞 Call for Current Price</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="products" id="water">
        <h2 class="section-title">Bottled Water Collection</h2>
        <div class="product-grid">
            <div class="product-card">
                <img src="images/water1.jpg" alt="Bottled Water" class="product-image water">
                <div class="product-info">
                    <div class="product-name">Premium Bottled Water</div>
                    <div class="product-price">
                        <a href="tel:+971562180707" class="call-for-price">📞 Call for Current Price</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="products" id="tshirts">
        <h2 class="section-title">T-Shirts Collection</h2>
        <div class="product-grid">
            <div class="product-card">
                <img src="images/tshirt1.jpg" alt="Halloween Pattern T-Shirt" class="product-image">
                <div class="product-info">
                    <div class="product-name">Halloween Pattern T-Shirt</div>
                    <div class="product-price">
                        <a href="tel:+971562180707" class="call-for-price">📞 Call for Current Price</a>
                    </div>
                </div>
            </div>
            <div class="product-card">
                <img src="images/tshirt2.jpg" alt="Peanuts Comic T-Shirt" class="product-image">
                <div class="product-info">
                    <div class="product-name">Peanuts Comic T-Shirt</div>
                    <div class="product-price">
                        <a href="tel:+971562180707" class="call-for-price">📞 Call for Current Price</a>
                    </div>
                </div>
            </div>
            <div class="product-card">
                <img src="images/tshirt3.jpg" alt="Tropical Floral T-Shirt" class="product-image">
                <div class="product-info">
                    <div class="product-name">Tropical Floral T-Shirt</div>
                    <div class="product-price">
                        <a href="tel:+971562180707" class="call-for-price">📞 Call for Current Price</a>
                    </div>
                </div>
            </div>
            <div class="product-card">
                <img src="images/tshirt4.jpg" alt="Pink Tie-Dye T-Shirt" class="product-image">
                <div class="product-info">
                    <div class="product-name">Pink Tie-Dye T-Shirt</div>
                    <div class="product-price">
                        <a href="tel:+971562180707" class="call-for-price">📞 Call for Current Price</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="deals">
        <h2>Daily Hot Deals!</h2>
    </section>

    <section class="features">
        <div class="feature-grid">
            <div class="feature-item">
                <div class="feature-icon">💵</div>
                <div class="feature-title">Cash on Delivery</div>
                <p class="feature-text">Pay when you receive your order</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">🚚</div>
                <div class="feature-title">Free Shipping</div>
                <p class="feature-text">On all orders</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">💯</div>
                <div class="feature-title">Quality Guaranteed</div>
                <p class="feature-text">100% authentic products</p>
            </div>
        </div>
    </section>

    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>About Us</h3>
                <ul>
                    <li>Our Story</li>
                    <li>Careers</li>
                    <li>Press</li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Customer Service</h3>
                <ul>
                    <li>Contact Us</li>
                    <li>Shipping Info</li>
                    <li>FAQ</li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul>
                    <li>Hot Deals</li>
                    <li>New Arrivals</li>
                    <li>Trending</li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Follow Us</h3>
                <ul>
                    <li>Facebook</li>
                    <li>Instagram</li>
                    <li>Twitter</li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2025 Clear Sky. All rights reserved.</p>
        </div>
    </footer>


</body>
</html>
