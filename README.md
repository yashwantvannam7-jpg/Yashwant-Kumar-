<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Local Shop</title>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

/* Hero Section */
.hero {
  background: url('https://i.ibb.co/bR8R0BvV/IMG-0895.jpg') center/cover no-repeat;
  height: 100vh;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.hero h1 {
  font-size: 40px;
}
.hero button {
  padding: 12px 25px;
  font-size: 18px;
  border: none;
  background: orange;
  color: white;
  cursor: pointer;
  margin-top: 15px;
}

/* Product Section */
.products {
  padding: 20px;
}
.carousel {
  display: flex;
  overflow-x: auto;
  gap: 15px;
}
.product {
  min-width: 200px;
  border: 1px solid #ddd;
  padding: 10px;
  text-align: center;
}
.product img {
  width: 100%;
  height: 150px;
  object-fit: cover;
}
.product button {
  margin-top: 10px;
  padding: 8px;
  background: green;
  color: white;
  border: none;
}

/* Cart Form */
.cart {
  padding: 20px;
  background: #f9f9f9;
}
input, textarea {
  width: 100%;
  padding: 10px;
  margin: 5px 0;
}

/* WhatsApp Button */
.whatsapp {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: green;
  color: white;
  padding: 15px;
  border-radius: 50%;
  text-decoration: none;
  font-size: 20px;
}
</style>

</head>

<body>

<!-- Hero -->
<div class="hero">
  <h1>The Local Shop</h1>
  <p>Fresh Finds, Best Prices</p>
  <button onclick="scrollToProducts()">Shop Now</button>
</div>

<!-- Products -->
<div id="products" class="products">
  <h2>Products</h2>
  <div class="carousel">
    
    <div class="product">
      <img src="https://i.ibb.co/tMNL6ktp">
      <h4>Product 1</h4>
      <button onclick="addToCart('Product 1')">Add</button>
    </div>

    <div class="product">
      <img src="https://i.ibb.co/tMNL6ktp">
      <h4>Product 2</h4>
      <button onclick="addToCart('Product 2')">Add</button>
    </div>

  </div>
</div>

<!-- Cart Form -->
<div class="cart">
  <h2>Place Order</h2>
  <form onsubmit="sendOrder(event)">
    <input type="text" id="name" placeholder="Your Name" required>
    <input type="tel" id="phone" placeholder="Phone Number" required>
    <textarea id="items" placeholder="Items will appear here" readonly></textarea>
    <button type="submit">Place Order</button>
  </form>
</div>

<!-- WhatsApp -->
<a class="whatsapp" href="https://wa.me/9226880569" target="_blank">💬</a>

<script>
let cart = [];

function scrollToProducts() {
  document.getElementById("products").scrollIntoView({ behavior: "smooth" });
}

function addToCart(item) {
  cart.push(item);
  document.getElementById("items").value = cart.join(", ");
}

function sendOrder(e) {
  e.preventDefault();

  let name = document.getElementById("name").value;
  let phone = document.getElementById("phone").value;
  let items = document.getElementById("items").value;

  let email = "mailto:yashwantvannam7@gmail.com"
    + "?subject=New Order"
    + "&body=Name: " + name
    + "%0APhone: " + phone
    + "%0AItems: " + items;

  window.location.href = email;
}
</script>

</body>
</html>
