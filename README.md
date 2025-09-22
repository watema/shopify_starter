# shopify_starter

 Shopify Starter Theme – WeRetail Global

Welcome to the **WeRetail Shopify Starter Theme**, a clean and responsive Shopify theme built using **Liquid**, **HTML**, **CSS**, and **JavaScript**. This project was developed as part of my front-end developer portfolio and demonstrates my ability to build and customize Shopify stores from scratch.


 Features

Dynamic Product Display** – Uses Liquid to loop through the `frontpage` collection and display product details.
Pixel-Perfect Layout** – Clean, minimalist layout styled with custom CSS.
Add to Cart** – Includes functional add-to-cart form using `variant.id`.
Responsive Design** – Optimized for mobile, tablet, and desktop.
Customizable** – Built to be extended with Shopify apps and APIs.

Tech Stack

Shopify Liquid
HTML5 + CSS3
avaScript (Vanilla)
Theme Sections & Templates
Responsive Grid Design


Getting Started

 1. Clone or Download
```bash
git clone https://github.com/yourusername/shopify-starter-theme.git


<!-- Shopify Starter Theme Template by Watema Emmanuel -->

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Starter Shopify Theme</title>
  <link rel="stylesheet" href="styles.css" />
  <script defer src="script.js"></script>
</head>
<body>
  <header class="site-header">
    <h1>WeRetail</h1>
    <nav>
      <a href="#home">Home</a>
      <a href="#products">Products</a>
      <a href="#cart">Cart</a>
    </nav>
  </header>

  <section id="home" class="hero">
    <h2>Premium Products. Powerful Style.</h2>
    <p>Shop electronics, fashion, and wellness items today.</p>
    <a href="#products" class="cta-button">Shop Now</a>
  </section>

  <section id="products" class="product-grid">
    {% for product in collections.frontpage.products %}
    <article class="product">
      <img src="{{ product.featured_image | img_url: 'medium' }}" alt="{{ product.title }}" />
      <h3>{{ product.title }}</h3>
      <p>{{ product.price | money }}</p>
      <form method="post" action="/cart/add">
        <input type="hidden" name="id" value="{{ product.variants.first.id }}">
        <button type="submit">Add to Cart</button>
      </form>
    </article>
    {% endfor %}
  </section>

  <section id="cart" class="cart">
    <h2>Your Cart</h2>
    <p>No items yet. (Dynamic cart content will be rendered via Liquid or JS)</p>
  </section>

  <footer>
    <p>&copy; 2025 WeRetail Global LLC</p>
  </footer>
</body>
</html>


/* styles.css – Shopify Starter Theme */
body {
  font-family: sans-serif;
  margin: 0;
  padding: 0;
  background: #f9f9f9;
  color: #333;
}

.site-header {
  background: #fff;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #ddd;
}

nav a {
  margin-left: 1rem;
  text-decoration: none;
  color: #0077cc;
}

.hero {
  background: #e5f3ff;
  padding: 2rem;
  text-align: center;
}

.cta-button {
  display: inline-block;
  margin-top: 1rem;
  padding: 0.75rem 1.5rem;
  background: #0077cc;
  color: white;
  text-decoration: none;
  border-radius: 4px;
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 1.5rem;
  padding: 2rem;
}

.product {
  background: #fff;
  padding: 1rem;
  border: 1px solid #ddd;
  text-align: center;
}

footer {
  background: #f0f0f0;
  padding: 1rem;
  text-align: center;
  font-size: 0.9rem;
}


