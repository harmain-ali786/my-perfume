# my-perfume
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Perfume - Luxury Fragrances</title>
    <style>
        /* CSS Styles */
        :root {
            --primary-color: #2c1810;
            --secondary-color: #d4af37;
            --light-color: #f8f5f2;
            --dark-color: #1a1a1a;
            --text-color: #333;
            --white: #ffffff;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Playfair Display', serif;
        }
        
        body {
            background-color: var(--light-color);
            color: var(--text-color);
            line-height: 1.6;
        }
        
        /* Header Styles */
        header {
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .top-bar {
            background-color: var(--primary-color);
            color: var(--white);
            padding: 10px 0;
            text-align: center;
            font-size: 14px;
        }
        
        .main-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 5%;
        }
        
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
        }
        
        .logo span {
            color: var(--secondary-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 30px;
        }
        
        nav ul li a {
            text-decoration: none;
            color: var(--dark-color);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--secondary-color);
        }
        
        .header-icons {
            display: flex;
            align-items: center;
        }
        
        .header-icons a {
            margin-left: 20px;
            color: var(--dark-color);
            font-size: 20px;
            position: relative;
        }
        
        .cart-count {
            position: absolute;
            top: -10px;
            right: -10px;
            background-color: var(--secondary-color);
            color: var(--white);
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 12px;
        }
        
        /* Hero Section */
        .hero {
            background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1592945403244-b3fbafd7f539');
            background-size: cover;
            background-position: center;
            height: 80vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
        }
        
        .hero-content {
            max-width: 800px;
            padding: 0 20px;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--secondary-color);
            color: var(--white);
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .btn:hover {
            background-color: var(--primary-color);
            transform: translateY(-3px);
        }
        
        /* Featured Products */
        .featured {
            padding: 80px 5%;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 36px;
            color: var(--primary-color);
            position: relative;
            display: inline-block;
            padding-bottom: 15px;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background-color: var(--secondary-color);
        }
        
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background-color: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
        }
        
        .product-img {
            height: 300px;
            overflow: hidden;
        }
        
        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .product-card:hover .product-img img {
            transform: scale(1.1);
        }
        
        .product-info {
            padding: 20px;
        }
        
        .product-category {
            color: var(--secondary-color);
            font-size: 14px;
            margin-bottom: 5px;
        }
        
        .product-title {
            font-size: 18px;
            margin-bottom: 10px;
            color: var(--dark-color);
        }
        
        .product-price {
            font-weight: 700;
            color: var(--primary-color);
            font-size: 20px;
            margin-bottom: 15px;
        }
        
        .add-to-cart {
            width: 100%;
            background-color: var(--primary-color);
            color: var(--white);
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .add-to-cart:hover {
            background-color: var(--secondary-color);
        }
        
        /* Newsletter */
        .newsletter {
            background-color: var(--primary-color);
            color: var(--white);
            padding: 60px 5%;
            text-align: center;
        }
        
        .newsletter h3 {
            font-size: 28px;
            margin-bottom: 20px;
        }
        
        .newsletter p {
            max-width: 600px;
            margin: 0 auto 30px;
        }
        
        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }
        
        .newsletter-form input {
            flex: 1;
            padding: 15px;
            border: none;
            border-radius: 30px 0 0 30px;
        }
        
        .newsletter-form button {
            background-color: var(--secondary-color);
            color: var(--white);
            border: none;
            padding: 0 30px;
            border-radius: 0 30px 30px 0;
            cursor: pointer;
            font-weight: 600;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: var(--white);
            padding: 60px 5% 30px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h4 {
            font-size: 18px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h4::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background-color: var(--secondary-color);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column ul li a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: var(--secondary-color);
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            color: var(--white);
            font-size: 20px;
            transition: color 0.3s;
        }
        
        .social-links a:hover {
            color: var(--secondary-color);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #ccc;
            font-size: 14px;
        }
        
        /* Responsive Styles */
        @media (max-width: 768px) {
            .main-header {
                flex-direction: column;
                padding: 20px;
            }
            
            nav ul {
                margin: 20px 0;
            }
            
            nav ul li {
                margin-left: 15px;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .newsletter-form {
                flex-direction: column;
            }
            
            .newsletter-form input {
                border-radius: 30px;
                margin-bottom: 10px;
            }
            
            .newsletter-form button {
                border-radius: 30px;
                padding: 15px;
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Header -->
    <header>
        <div class="top-bar">
            Free shipping on orders over $50 | Use code PERFUME10 for 10% off
        </div>
        <div class="main-header">
            <a href="index.html" class="logo">My<span>Perfume</span></a>
            <nav>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Shop</a></li>
                    <li><a href="#">Brands</a></li>
                    <li><a href="#">Collections</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </nav>
            <div class="header-icons">
                <a href="#"><i class="fas fa-search"></i></a>
                <a href="#"><i class="fas fa-user"></i></a>
                <a href="#">
                    <i class="fas fa-shopping-bag"></i>
                    <span class="cart-count">0</span>
                </a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Discover Your Signature Scent</h1>
            <p>Luxury fragrances crafted with the finest ingredients from around the world</p>
            <a href="#" class="btn">Shop Now</a>
        </div>
    </section>

    <!-- Featured Products -->
    <section class="featured">
        <div class="section-title">
            <h2>Our Best Sellers</h2>
        </div>
        <div class="products-grid" id="products-container">
            <!-- Products will be added dynamically with JavaScript -->
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter">
        <h3>Join Our Fragrance Community</h3>
        <p>Subscribe to receive updates on new arrivals, special offers and perfume tips from our experts.</p>
        <form class="newsletter-form">
            <input type="email" placeholder="Your email address" required>
            <button type="submit">Subscribe</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h4>My Perfume</h4>
                <p>Luxury fragrances that tell your story. Crafted with passion and the finest ingredients from around the world.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-pinterest-p"></i></a>
                </div>
            </div>
            <div class="footer-column">
                <h4>Shop</h4>
                <ul>
                    <li><a href="#">All Products</a></li>
                    <li><a href="#">New Arrivals</a></li>
                    <li><a href="#">Best Sellers</a></li>
                    <li><a href="#">Special Offers</a></li>
                    <li><a href="#">Gift Sets</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h4>Customer Service</h4>
                <ul>
                    <li><a href="#">Contact Us</a></li>
                    <li><a href="#">FAQs</a></li>
                    <li><a href="#">Shipping Policy</a></li>
                    <li><a href="#">Returns & Exchanges</a></li>
                    <li><a href="#">Track Order</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h4>About</h4>
                <ul>
                    <li><a href="#">Our Story</a></li>
                    <li><a href="#">Ingredients</a></li>
                    <li><a href="#">Sustainability</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Store Locator</a></li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2023 My Perfume. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        // JavaScript for the perfume website
        document.addEventListener('DOMContentLoaded', function() {
            // Sample product data
            const products = [
                {
                    id: 1,
                    name: "Eternal Essence",
                    category: "Women",
                    price: 89.99,
                    image: "https://images.unsplash.com/photo-1615634262417-98ba4b315b02"
                },
                {
                    id: 2,
                    name: "Noir Mystique",
                    category: "Men",
                    price: 79.99,
                    image: "https://images.unsplash.com/photo-1594035910387-fea47794261f"
                },
                {
                    id: 3,
                    name: "Golden Oud",
                    category: "Unisex",
                    price: 109.99,
                    image: "https://images.unsplash.com/photo-1615368144592-6b8f6a22b2a6"
                },
                {
                    id: 4,
                    name: "Jasmine Serenade",
                    category: "Women",
                    price: 69.99,
                    image: "https://images.unsplash.com/photo-1615368144592-6b8f6a22b2a6"
                },
                {
                    id: 5,
                    name: "Tobacco Vanille",
                    category: "Men",
                    price: 99.99,
                    image: "https://images.unsplash.com/photo-1594035910387-fea47794261f"
                },
                {
                    id: 6,
                    name: "Citrus Splash",
                    category: "Unisex",
                    price: 59.99,
                    image: "https://images.unsplash.com/photo-1615634262417-98ba4b315b02"
                }
            ];

            // Display products
            const productsContainer = document.getElementById('products-container');
            
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    <div class="product-img">
                        <img src="${product.image}" alt="${product.name}">
                    </div>
                    <div class="product-info">
                        <p class="product-category">${product.category}</p>
                        <h3 class="product-title">${product.name}</h3>
                        <p class="product-price">$${product.price.toFixed(2)}</p>
                        <button class="add-to-cart" data-id="${product.id}">Add to Cart</button>
                    </div>
                `;
                productsContainer.appendChild(productCard);
            });

            // Cart functionality
            let cartCount = 0;
            const cartCountElement = document.querySelector('.cart-count');
            const addToCartButtons = document.querySelectorAll('.add-to-cart');
            
            addToCartButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const productId = this.getAttribute('data-id');
                    addToCart(productId);
                });
            });
            
            function addToCart(productId) {
                cartCount++;
                cartCountElement.textContent = cartCount;
                
                // Animation for cart addition
                cartCountElement.style.transform = 'scale(1.5)';
                setTimeout(() => {
                    cartCountElement.style.transform = 'scale(1)';
                }, 300);
                
                // In a real application, you would add the product to a cart array
                console.log(`Product ${productId} added to cart`);
            }
            
            // Newsletter form submission
            const newsletterForm = document.querySelector('.newsletter-form');
            newsletterForm.addEventListener('submit', function(e) {
                e.preventDefault();
                const email = this.querySelector('input').value;
                alert(`Thank you for subscribing with ${email}! You'll receive our latest updates soon.`);
                this.reset();
            });
            
            // Smooth scrolling for navigation
            document.querySelectorAll('nav a').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    if(targetId !== '#') {
                        document.querySelector(targetId).scrollIntoView({
                            behavior: 'smooth'
                        });
                    }
                });
            });
        });
    </script>
</body>
</html>
