<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Firdaus Mart</title>
<style>
:root {
  --primary: #ff6b00;
  --secondary: #333;
}
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: 'Poppins', sans-serif; background: #fff; color: var(--secondary); }

/* Header */
header {
  background: var(--primary);
  color: white;
  padding: 15px 20px;
  text-align: center;
  position: sticky; top: 0; z-index: 1000;
}
header h1 { font-size: 28px; margin-bottom: 8px; letter-spacing: 1px; }
nav { display: flex; justify-content: center; gap: 25px; flex-wrap: wrap; }
nav a { color: white; font-weight: 600; text-decoration: none; transition: 0.3s; }
nav a:hover { opacity: 0.8; }
.cart-icon {
  cursor: pointer; position: relative; font-size: 20px;
}
.cart-icon span {
  background: white; color: var(--primary);
  font-size: 12px; font-weight: bold;
  border-radius: 50%; padding: 2px 6px;
  position: absolute; top: -8px; right: -10px;
}

/* Hero */
.hero {
  background: url('https://via.placeholder.com/1200x500/ff6b00/fff?text=Firdaus+Mart+Promo') center/cover no-repeat;
  height: 400px;
  display: flex; justify-content: center; align-items: center;
  color: white; text-align: center; flex-direction: column;
}
.hero h2 { font-size: 36px; margin-bottom: 15px; }
.hero button {
  background: white; color: var(--primary);
  padding: 12px 25px; border: none; border-radius: 6px;
  font-size: 16px; cursor: pointer; font-weight: bold;
  transition: .3s;
}
.hero button:hover { background: #f2f2f2; }

/* Produk */
.products {
  padding: 50px 20px;
  display: grid; grid-template-columns: repeat(auto-fit,minmax(220px,1fr));
  gap: 20px;
}
.product {
  background: white; border-radius: 12px; padding: 15px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.08);
  text-align: center; transition: .3s;
}
.product:hover { transform: translateY(-5px); }
.product img { width: 100%; border-radius: 10px; margin-bottom: 10px; }
.product h3 { font-size: 18px; margin-bottom: 6px; }
.product p { font-weight: bold; color: var(--primary); margin-bottom: 12px; }
.product button {
  background: var(--primary); color: white; border: none;
  padding: 10px 15px; border-radius: 6px; cursor: pointer;
  transition: .3s; font-weight: bold;
}
.product button:hover { background: #e65c00; }

/* Cart Drawer */
.cart-drawer {
  position: fixed; top: 0; right: -100%;
  width: 340px; height: 100%;
  background: white; box-shadow: -2px 0 8px rgba(0,0,0,.2);
  padding: 20px; transition: right .3s ease;
  z-index: 2000; overflow-y: auto;
}
.cart-drawer.active { right: 0; }
.cart-drawer h3 { text-align: center; margin-bottom: 15px; }
.cart-item { display: flex; justify-content: space-between; margin-bottom: 10px; font-size: 14px; }
.cart-item button {
  background: red; color: white; border: none;
  font-size: 12px; border-radius: 4px; cursor: pointer; padding: 2px 6px;
}
.cart-total { margin-top: 15px; font-weight: bold; text-align: right; }
.checkout-btn {
  margin-top: 15px; width: 100%; background: var(--primary); color: white;
  border: none; padding: 12px; border-radius: 6px; cursor: pointer; font-size: 16px;
}
.checkout-btn:hover { background: #e65c00; }

/* Sections */
section { padding: 40px 20px; }
#tentang, #kontak {
  background: #fafafa; border-radius: 10px; margin: 20px auto;
  max-width: 800px; box-shadow: 0 2px 6px rgba(0,0,0,0.05);
  padding: 30px;
}

/* Footer */
footer { background: #333; color: white; text-align: center; padding: 20px; font-size: 14px; margin-top: 20px; }
footer a { color: var(--primary); }
</style>
</head>
<body>

<header>
  <h1>Firdaus Mart</h1>
  <nav>
    <a href="#home">Home</a>
    <a href="#produk">Produk</a>
    <a href="#tentang">Tentang Kami</a>
    <a href="#kontak">Kontak</a>
    <div class="cart-icon" onclick="toggleCart()"><span id="cart-count">0</span></div>
  </nav>
</header>

<section class="hero" id="home">
  <h2>Belanja Mudah, Cepat, dan Murah di Firdaus Mart!</h2>
  <button onclick="document.getElementById('produk').scrollIntoView({behavior:'smooth'})">Belanja Sekarang</button>
</section>

<section class="products" id="produk">
  <div class="product">
    <img src="https://via.placeholder.com/250x300" alt="Produk 1">
    <h3>Kemeja Putih</h3>
    <p>Rp150.000</p>
    <button onclick="addToCart('Kemeja Putih',150000)">Tambah ke Keranjang</button>
  </div>
  <div class="product">
    <img src="https://via.placeholder.com/250x300" alt="Produk 2">
    <h3>T-Shirt Hitam</h3>
    <p>Rp100.000</p>
    <button onclick="addToCart('T-Shirt Hitam',100000)">Tambah ke Keranjang</button>
  </div>
  <div class="product">
    <img src="https://via.placeholder.com/250x300" alt="Produk 3">
    <h3>Jaket Denim</h3>
    <p>Rp250.000</p>
    <button onclick="addToCart('Jaket Denim',250000)">Tambah ke Keranjang</button>
  </div>
</section>

<section id="tentang">
  <h2>Tentang Kami</h2>
  <p>Firdaus Mart adalah e-commerce latihan yang meniru gaya modern marketplace. Semua produk hanya placeholder.</p>
</section>

<section id="kontak">
  <h2>Kontak</h2>
  <p>Hubungi kami via WhatsApp: <a href="https://wa.me/6281234567890">Klik di sini</a></p>
</section>

<!-- Cart Drawer -->
<div class="cart-drawer" id="cart">
  <h3>Keranjang Belanja</h3>
  <div id="cart-items"></div>
  <div class="cart-total">Total: Rp<span id="cart-total">0</span></div>
  <button class="checkout-btn" onclick="checkout()">Checkout via WhatsApp</button>
</div>

<footer>
  <p>© 2025 Firdaus Mart. All rights reserved. | <a href="#">Instagram</a> | <a href="#">WhatsApp</a></p>
</footer>

<script>
let cart = [];

function addToCart(name, price){
  const existing = cart.find(item => item.name === name);
  if(existing){ existing.qty += 1; }
  else { cart.push({name, price, qty: 1}); }
  renderCart();
}

function removeFromCart(name){
  cart = cart.filter(item => item.name !== name);
  renderCart();
}

function renderCart(){
  const cartItems = document.getElementById('cart-items');
  const cartTotal = document.getElementById('cart-total');
  const cartCount = document.getElementById('cart-count');
  cartItems.innerHTML = '';
  let total = 0, count = 0;
  cart.forEach(item => {
    total += item.price * item.qty;
    count += item.qty;
    const div = document.createElement('div');
    div.className = 'cart-item';
    div.innerHTML = `${item.name} x${item.qty} <span>Rp${item.price*item.qty}</span> <button onclick="removeFromCart('${item.name}')">Hapus</button>`;
    cartItems.appendChild(div);
  });
  cartTotal.innerText = total;
  cartCount.innerText = count;
}

function toggleCart(){
  document.getElementById('cart').classList.toggle('active');
}

function checkout(){
  if(cart.length === 0){ alert('Keranjang kosong!'); return; }
  let items = cart.map(item => `${item.name} x${item.qty}`).join('%0A');
  let total = document.getElementById('cart-total').innerText;
  let waUrl = `https://wa.me/6281234567890?text=Halo%20saya%20ingin%20checkout:%0A${items}%0ATotal:%20Rp${total}`;
  window.open(waUrl, '_blank');
  cart = [];
  renderCart();
  toggleCart();
}
</script>

</body>
</html>