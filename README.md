<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TechStore - Your Tech Hub</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; background: #f5f5f5; }
    header { background: #0d1b2a; color: white; padding: 15px 40px; display: flex; justify-content: space-between; align-items: center; position: sticky; top: 0; z-index: 1000; }
    header h1 { margin: 0; font-size: 24px; }
    nav { display: flex; gap: 15px; }
    nav a { color: white; text-decoration: none; }
    nav a:hover { text-decoration: underline; }
    
    /* Mobile Menu */
    .menu-toggle { display: none; cursor: pointer; font-size: 24px; }
    @media (max-width: 600px) {
      nav { display: none; flex-direction: column; background: #0d1b2a; position: absolute; top: 60px; right: 0; padding: 20px; }
      nav.active { display: flex; }
      .menu-toggle { display: block; }
    }

    .hero { background: url('https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=1400&q=80') no-repeat center/cover; color: white; text-align: center; padding: 100px 20px; }
    .hero h2 { font-size: 40px; }
    .products { padding: 40px; display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; }
    .product { background: white; padding: 20px; border-radius: 8px; text-align: center; box-shadow: 0 2px 6px rgba(0,0,0,0.1); transition: transform 0.2s, box-shadow 0.2s; }
    .product:hover { transform: translateY(-5px); box-shadow: 0 6px 12px rgba(0,0,0,0.15); }
    .product img { width: 100%; max-height: 200px; object-fit: contain; margin-bottom: 15px; }
    .product h3 { margin: 10px 0; }
    .product p { color: #555; }
    .btn { background: #1b263b; color: white; padding: 10px 15px; border: none; cursor: pointer; border-radius: 4px; transition: background 0.3s; }
    .btn:hover { background: #415a77; }
    .contact { background: #e0e1dd; padding: 40px; text-align: center; }
    .contact input, .contact textarea { width: 90%; max-width: 400px; padding: 10px; margin: 10px 0; border: 1px solid #aaa; border-radius: 4px; }
    footer { background: #0d1b2a; color: white; text-align: center; padding: 15px; }
  </style>
</head>
<body>
  <header>
    <h1>TechStore</h1>
    <span class="menu-toggle">☰</span>
    <nav>
      <a href="#">Home</a>
      <a href="#products">Products</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section class="hero">
    <h2>Latest Tech at Your Fingertips</h2>
    <p>Find the best gadgets, laptops, and accessories here!</p>
    <button class="btn" id="shopNowBtn">Shop Now</button>
  </section>

  <section id="products" class="products">
    <div class="product">
      <img src="https://images.unsplash.com/photo-1517336714731-489689fd1ca8?auto=format&fit=crop&w=600&q=80" alt="Laptop">
      <h3>High-Performance Laptop</h3>
      <p>$999</p>
      <button class="btn buyBtn">Buy Now</button>
    </div>
    <div class="product">
      <img src="https://images.unsplash.com/photo-1581291519195-ef11498d1cf5?auto=format&fit=crop&w=600&q=80" alt="Headphones">
      <h3>Noise-Cancelling Headphones</h3>
      <p>$199</p>
      <button class="btn buyBtn">Buy Now</button>
    </div>
    <div class="product">
      <img src="https://images.unsplash.com/photo-1603791440384-56cd371ee9a7?auto=format&fit=crop&w=600&q=80" alt="Smartphone">
      <h3>Latest Smartphone</h3>
      <p>$799</p>
      <button class="btn buyBtn">Buy Now</button>
    </div>
  </section>

  <section id="contact" class="contact">
    <h2>Contact Us</h2>
    <p>Have questions? Send us a message!</p>
    <form id="contactForm">
      <input type="text" placeholder="Your Name" required><br>
      <input type="email" placeholder="Your Email" required><br>
      <textarea rows="4" placeholder="Your Message" required></textarea><br>
      <button type="submit" class="btn">Send</button>
    </form>
    <p id="formMessage" style="color:green; font-weight:bold; display:none;">✅ Your message has been sent!</p>
  </section>

  <footer>
    <p>&copy; 2025 TechStore. All rights reserved.</p>
  </footer>

  <script>
    // Shop Now Button Scroll
    document.getElementById("shopNowBtn").addEventListener("click", function() {
      document.getElementById("products").scrollIntoView({ behavior: "smooth" });
    });

    // Buy Now Buttons Action
    document.querySelectorAll(".buyBtn").forEach(button => {
      button.addEventListener("click", function() {
        alert("🛒 Added to cart!");
      });
    });

    // Contact Form Submit
    document.getElementById("contactForm").addEventListener("submit", function(e) {
      e.preventDefault();
      document.getElementById("formMessage").style.display = "block";
      this.reset();
    });

    // Mobile Menu Toggle
    document.querySelector(".menu-toggle").addEventListener("click", function() {
      document.querySelector("nav").classList.toggle("active");
    });
  </script>
</body>
</html>

