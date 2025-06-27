<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      body {
        background-color: #e9e9e9;
        margin: 0;
        font-family: "Clash Grotesk", sans-serif;
      }

      .navbar {
        font-size: 14px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #060029;
        padding: 0 20px;
        height: 40px;
      }

      .nav-left,
      .nav-right {
        display: flex;
        gap: 20px;
      }

      .navbar a {
        color: white;
        font-weight: bold;
        text-decoration: none;
        padding: 14px 0;
        transition: color 0.3s;
      }

      .navbar a:hover {
        color: #ff4f6c;
      }

      .search-section {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 15px 20px;
        background-color: #060029;
        border-top: 1px solid #ddd;
      }

      .logo img {
        width: 70px;
        height: 70px;
      }

      .logo {
        display: flex;
        font-size: 40px;
        font-weight: bold;
        color: #ffffff;
        align-items: center;
      }

      .search-bar {
        flex: 1;
        width: 50%;
        margin: 0 20px;
        position: relative;
      }

      .search-bar input {
        margin-left: 200px;
        width: 50%;
        padding: 10px;
        font-size: 16px;
        align-self: center;
        border: 1px solid #ccc;
        border-radius: 4px;
        border-radius: 20px;
      }

      .cart {
        font-size: 18px;
        color: white;
        padding: 10px 16px;
        margin-left: 10px;
        border-radius: 4px;
        text-decoration: none;
      }

      .cart:hover {
        background-color: #ff4f6c;
      }

      .category-account-section {
        height: 30px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #ff4f6c;
        padding: 10px 20px;
        border-bottom: 1px solid #ddd;
      }

      .category-left,
      .account-right {
        display: flex;
        gap: 15px;
      }

      .category-account-section a {
        text-decoration: none;
        font-weight: bold;
        color: #ffffff;
        transition: color 0.3s;
      }

      .category-account-section a:hover {
        color: #060029;
      }

      .slideshow-container {
        height: 600px;
        margin: 20px;
        border-radius: 20px;
        width: 40%;
        position: relative;
        overflow: hidden;
      }

      .slide {
        display: none;
        width: 100%;
        height: 100vh;
      }

      .slide img {
        width: 100%;
        height: 100vh;
        object-fit: cover;
      }

      /* Navigation arrows */
      .prev,
      .next {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        color: rgb(0, 0, 0);
        padding: 10px;
        cursor: pointer;
        font-size: 18px;
        user-select: none;
      }

      .prev { 
        left: 10px;
      }
      .next {
        right: 10px;
      }

      .main-section {
        display: flex;
      }

      .offer-box-wrapper {
        width: 23%;
        border-radius: 20px;
        margin: 20px;
        margin-left: 10px;
        display: flex;
        justify-content: center;
        height: 350px;
        overflow: hidden;
      }
      .offer-box {
        text-align: center;
        background: linear-gradient(#043927, rgb(3, 10, 0));
        padding: 10px;
        border-radius: 12px;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        max-width: 320px;
        width: 100%;
      }
      .offer-box img {
        width: 180px;
        height: 250px;
        border-radius: 10px;
      }

      .offer-box img:hover {
        transform: scale(1.1);
        transition: transform 0.9s;
        transition-duration: 0.5s;
      }
      .offer-box h2 {
        color: #f3ffde;
        margin-bottom: 10px;
      }

      .offer-box p {
        font-size: 16px;
        color: #f3ffde;
      }

      .hot-categories-grid {
        margin: 10px;
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 20px;
        height: 350px;
      }

      .category-item {
        background-color: #ffffff;
        padding: 10px;
        text-align: center;
        border-radius: 50%;
        font-weight: bold;
        transition: background-color 0.3s, transform 0.3s;
        cursor: pointer;
        width: 100px;
        height: 100px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin: auto;
      }

      .category-item img {
        width: 100px;
        height: 80px;
        object-fit: contain;
      }

      .category-item span {
        color: #000000;
        font-size: 12px;
      }

      .category-item img:hover {
        transform: scale(1.2);
        transition: transform 0.9s;
        transition-duration: 0.5s;
      }

      .best-pick-wrapper {
        width: calc(100% -40px); /* account for main-section margin */
        margin: 0 20px 30px 20px;
      }

      .best-pick-box {
        display: flex;
        justify-content: space-around;
        background-color: #060029;
        color: white;
        padding: 10px;
        height: 70px;
        border-radius: 20px;
        text-align: center;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
      }

      .best-pick-box img {
        width: 30px;
        height: auto;
        margin-top: 0px;
        border-radius: 10px;
        transition: transform 0.5s ease;
      }

      .best-pick-box #items:hover {
        transform: scale(1.1);
      }

      .best-pick-box #items {
        display: flex;
        gap: 10px;
        align-items: center;
      }
    </style>
  </head>
  <body>
    <nav class="navbar">
      <div class="nav-left">
        <a href="#about">About Us</a>
        <hr style="height: 20px; align-self: center" />
        <a href="#contact">Contact Us</a>
        <hr style="height: 20px; align-self: center" />
        <a href="#work">Work With Us</a>
      </div>
      <div class="nav-right">
        <a href="#track">Track Your Order</a>
        <hr style="height: 20px; align-self: center" />
        <a href="#partners">Our Partners</a>
        <hr style="height: 20px; align-self: center" />
        <a href="#faqs">FAQs</a>
      </div>
    </nav>
    <section class="search-section">
      <div class="logo">
        <img src="mart.png" alt="" />
        woodmart
      </div>
      <div class="search-bar">
        <input
          type="text"
          placeholder="🔍 Search products, brands, categories..."
        />
      </div>
      <a href="#cart" class="cart" onclick="myfun()">🛒Cart</a>
    </section>
    <section class="category-account-section">
      <div class="category-left">
        <a href="#electronics">Electronics</a>
        <a href="#appliances">Appliances</a>
        <a href="#home-garden">Home & Garden</a>
        <a href="#baby-kids">Baby & Kids</a>
        <a href="#beauty-care">Beauty & Care</a>
      </div>

      <div class="account-right">
        <a href="#login">Login</a>
        <a href="#signup">Sign Up</a>
        <a href="#watchlist">Watchlist</a>
      </div>
    </section>
    <div class="main-section">
      <div class="slideshow-container">
        <div class="slide">
          <img src="s24.jpg" alt="Slide 1" />
        </div>
        <div class="slide">
          <img src="buds.jpeg" alt="Slide 2" />
        </div>
        <div class="slide">
          <img src="chair.jpg" alt="Slide 3" />
        </div>

        <!-- Arrows -->
        <a class="prev" onclick="changeSlide(-1)">❮</a>
        <a class="next" onclick="changeSlide(1)">❯</a>
      </div>

      <script>
        let slideIndex = 0;
        const slides = document.getElementsByClassName("slide");

        function showSlide(index) {
          for (let i = 0; i < slides.length; i++) {
            slides[i].style.display = "none";
          }
          slideIndex = (index + slides.length) % slides.length;
          slides[slideIndex].style.display = "block";
        }

        function changeSlide(n) {
          showSlide(slideIndex + n);
        }

        function myfun() {
          alert("your cart is empty...!");
        }

        /*setInterval(() => {
          changeSlide(1);
        }, 5000);*/

        // Auto show first slide on load
        showSlide(slideIndex);
      </script>
      <div class="offer-box-wrapper">
        <div class="offer-box">
          <h2>Special Offer!</h2>
          <p>Save up to 30% on Washing Machines Limited Time Only!</p>
          <p>$799 Special Offer</p>
          <img src="washing machine.png" alt="Washing Machine" />
        </div>
      </div>

      <div class="hot-categories-grid">
        <div class="category-item">
          <img src="phones.png" alt="Phones" />
          <span>Phones</span>
        </div>
        <div class="category-item">
          <img src="Laptop-PNG.png" alt="Laptops" />
          <span>Laptops</span>
        </div>
        <div class="category-item">
          <img src="furniture.png" alt="Furniture" />
          <span>Furniture</span>
        </div>
        <div class="category-item">
          <img src="watches.png" alt="Watches" />
          <span>Watches</span>
        </div>
        <div class="category-item">
          <img src="shoes.png" alt="Shoes" />
          <span>Shoes</span>
        </div>
        <div class="category-item">
          <img src="camera1.png" alt="Cameras" />
          <span>Cameras</span>
        </div>
        <div class="category-item">
          <img src="books.png" alt="Books" />
          <span>Books</span>
        </div>
        <div class="category-item">
          <img src="headphones.png" alt="Headphones" />
          <span>Headphones</span>
        </div>
      </div>
    </div>
    <div class="best-pick-wrapper">
  <div class="best-pick-box">
    <div id="items">
      <span>
      <img src="https://woodmart.xtemos.com/marketplace2/wp-content/uploads/sites/21/2024/03/mp2-infobox-map-pointer.svg" alt="" /></span>
      <p>Fast, Free Shipping</p>
    </div>
    <div id="items">
      <img src="https://woodmart.xtemos.com/marketplace2/wp-content/uploads/sites/21/2024/03/mp2-infobox-bundle.svg" alt="" />
      <p>Next Day Delivery</p>
    </div>
    <div id="items">
      <img src="https://woodmart.xtemos.com/marketplace2/wp-content/uploads/sites/21/2024/03/mp2-infobox-like.svg" alt="" />
      <p>60 Days Free Return</p>
    </div>
    <div id="items">
      <img src="https://woodmart.xtemos.com/marketplace2/wp-content/uploads/sites/21/2024/03/mp2-infobox-phone-clrd.svg" alt="" />
      <p>Expert Customer Service</p>
    </div>
    <div id="items">
      <img src="https://woodmart.xtemos.com/marketplace2/wp-content/uploads/sites/21/2024/03/mp2-infobox-heart.svg" alt="" />
      <p>Exculsive Brands</p>
    </div>
  </div>
</div>

    </div>
  </body>
</html>
# Wood-Mart-Project
online wood mart for shopping
