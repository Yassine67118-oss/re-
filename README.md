<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bags Collection — Paris</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,300;0,400;0,700;1,300;1,400&family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=Montserrat:wght@100;200;300;400&display=swap" rel="stylesheet">
<style>
:root {
  --cream: #f2ede4;
  --cream-dark: #e8e0d0;
  --black: #0f0f0f;
  --black-soft: #1a1a1a;
  --grey: #8a8a8a;
  --grey-light: #d4cfc7;
  --white: #ffffff;
}

* { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
  background: var(--cream);
  color: var(--black);
  font-family: 'Montserrat', sans-serif;
  overflow-x: hidden;
  cursor: none;
}

/* ── CUSTOM CURSOR ── */
.cursor {
  width: 10px; height: 10px;
  background: var(--black);
  border-radius: 50%;
  position: fixed;
  top: 0; left: 0;
  pointer-events: none;
  z-index: 9999;
  transition: transform 0.15s ease;
  mix-blend-mode: difference;
}
.cursor-ring {
  width: 36px; height: 36px;
  border: 1px solid var(--black);
  border-radius: 50%;
  position: fixed;
  top: 0; left: 0;
  pointer-events: none;
  z-index: 9998;
  transition: transform 0.4s ease, width 0.3s ease, height 0.3s ease;
  mix-blend-mode: difference;
}
.cursor.hover { transform: translate(-50%,-50%) scale(3); }
.cursor-ring.hover { width: 60px; height: 60px; }

/* ── NAV ── */
nav {
  position: fixed; top: 0; left: 0; right: 0;
  z-index: 100;
  display: flex; align-items: center; justify-content: space-between;
  padding: 24px 60px;
  background: rgba(242, 237, 228, 0.9);
  backdrop-filter: blur(12px);
  border-bottom: 0.5px solid var(--grey-light);
  animation: slideDown 0.8s ease forwards;
}

@keyframes slideDown {
  from { transform: translateY(-100%); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}

.nav-logo {
  display: flex; flex-direction: column; align-items: flex-start; gap: 0px;
}
.nav-logo .bags {
  font-family: 'Cormorant Garamond', serif;
  font-weight: 300;
  font-size: 11px;
  letter-spacing: 10px;
  text-transform: uppercase;
  color: var(--black);
}
.nav-logo .collection {
  font-family: 'Playfair Display', serif;
  font-weight: 700;
  font-size: 18px;
  letter-spacing: 4px;
  text-transform: uppercase;
  line-height: 1;
}
.nav-logo .paris-tag {
  font-family: 'Cormorant Garamond', serif;
  font-style: italic;
  font-size: 10px;
  letter-spacing: 2px;
  color: var(--grey);
}

.nav-links {
  display: flex; gap: 40px; list-style: none;
}
.nav-links a {
  font-size: 9px;
  letter-spacing: 3px;
  text-transform: uppercase;
  text-decoration: none;
  color: var(--black);
  font-weight: 300;
  transition: opacity 0.2s;
}
.nav-links a:hover { opacity: 0.5; }

.nav-right {
  display: flex; align-items: center; gap: 24px;
}
.cart-btn {
  position: relative;
  background: var(--black);
  color: var(--cream);
  border: none;
  padding: 10px 22px;
  font-family: 'Montserrat', sans-serif;
  font-size: 8px;
  letter-spacing: 3px;
  text-transform: uppercase;
  cursor: none;
  transition: background 0.3s;
}
.cart-btn:hover { background: var(--black-soft); }
.cart-count {
  position: absolute; top: -6px; right: -6px;
  background: #c9a96e;
  color: white;
  border-radius: 50%;
  width: 16px; height: 16px;
  font-size: 8px;
  display: flex; align-items: center; justify-content: center;
  font-weight: 400;
}

/* ── HERO ── */
.hero {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding-top: 90px;
}

.hero-left {
  display: flex; flex-direction: column; justify-content: center;
  padding: 80px 60px;
  gap: 32px;
  animation: fadeLeft 1s 0.3s ease forwards; opacity: 0;
}

@keyframes fadeLeft {
  from { opacity: 0; transform: translateX(-30px); }
  to { opacity: 1; transform: translateX(0); }
}

.hero-tag {
  font-size: 8px; letter-spacing: 5px; text-transform: uppercase;
  color: var(--grey); font-weight: 200;
  display: flex; align-items: center; gap: 12px;
}
.hero-tag::before {
  content: ''; width: 30px; height: 0.5px; background: var(--grey);
}

.hero-title {
  font-family: 'Playfair Display', serif;
  font-weight: 300;
  font-size: clamp(48px, 6vw, 80px);
  line-height: 1.05;
  letter-spacing: -1px;
}
.hero-title em {
  font-style: italic;
  color: var(--grey);
}

.hero-desc {
  font-size: 11px; letter-spacing: 1px; line-height: 2;
  color: var(--grey); font-weight: 200; max-width: 380px;
}

.hero-cta {
  display: flex; gap: 16px; align-items: center;
}

.btn-primary {
  background: var(--black); color: var(--cream);
  border: none; padding: 16px 36px;
  font-family: 'Montserrat', sans-serif;
  font-size: 8px; letter-spacing: 4px; text-transform: uppercase;
  cursor: none; transition: all 0.3s;
  text-decoration: none; display: inline-block;
}
.btn-primary:hover { background: var(--black-soft); letter-spacing: 6px; }

.btn-secondary {
  background: transparent; color: var(--black);
  border: 0.5px solid var(--black); padding: 16px 36px;
  font-family: 'Montserrat', sans-serif;
  font-size: 8px; letter-spacing: 4px; text-transform: uppercase;
  cursor: none; transition: all 0.3s; text-decoration: none; display: inline-block;
}
.btn-secondary:hover { background: var(--black); color: var(--cream); }

.hero-right {
  background: var(--black);
  display: flex; align-items: center; justify-content: center;
  position: relative; overflow: hidden;
  animation: fadeRight 1s 0.5s ease forwards; opacity: 0;
}

@keyframes fadeRight {
  from { opacity: 0; transform: translateX(30px); }
  to { opacity: 1; transform: translateX(0); }
}

.hero-image-placeholder {
  width: 100%; height: 100%;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center; gap: 20px;
  background: linear-gradient(135deg, #1a1a1a 0%, #0a0a0a 100%);
}

.hero-bag-svg {
  opacity: 0.15;
}

.hero-overlay-text {
  position: absolute; bottom: 40px; left: 40px;
  font-family: 'Cormorant Garamond', serif;
  font-style: italic; font-size: 13px;
  letter-spacing: 3px; color: rgba(255,255,255,0.3);
}

.floating-badge {
  position: absolute; top: 40px; right: 40px;
  border: 0.5px solid rgba(255,255,255,0.2);
  padding: 16px;
  display: flex; flex-direction: column; align-items: center; gap: 4px;
}
.floating-badge span:first-child {
  font-size: 22px; font-weight: 300; color: white;
  font-family: 'Playfair Display', serif;
}
.floating-badge span:last-child {
  font-size: 7px; letter-spacing: 3px; color: rgba(255,255,255,0.5);
  text-transform: uppercase;
}

/* ── MARQUEE ── */
.marquee-wrap {
  background: var(--black);
  padding: 16px 0; overflow: hidden;
  border-top: 0.5px solid #333; border-bottom: 0.5px solid #333;
}
.marquee-track {
  display: flex; gap: 60px; animation: marquee 20s linear infinite; width: max-content;
}
.marquee-item {
  font-size: 9px; letter-spacing: 5px; text-transform: uppercase;
  color: rgba(255,255,255,0.4); font-weight: 200; white-space: nowrap;
  display: flex; align-items: center; gap: 60px;
}
.marquee-item::after { content: '✦'; color: #c9a96e; font-size: 8px; }
@keyframes marquee {
  from { transform: translateX(0); }
  to { transform: translateX(-50%); }
}

/* ── SECTION TITRE ── */
.section-header {
  text-align: center; padding: 80px 60px 48px;
}
.section-tag {
  font-size: 8px; letter-spacing: 6px; text-transform: uppercase;
  color: var(--grey); font-weight: 200; margin-bottom: 16px;
  display: flex; align-items: center; justify-content: center; gap: 16px;
}
.section-tag::before, .section-tag::after {
  content: ''; width: 40px; height: 0.5px; background: var(--grey-light);
}
.section-title {
  font-family: 'Playfair Display', serif;
  font-weight: 300; font-size: clamp(32px, 4vw, 52px);
  letter-spacing: -0.5px; line-height: 1.1;
}
.section-title em { font-style: italic; color: var(--grey); }

/* ── PRODUITS ── */
.products-section { padding: 0 40px 80px; }

.products-filter {
  display: flex; gap: 4px; justify-content: center; margin-bottom: 48px;
}
.filter-btn {
  background: transparent; border: 0.5px solid var(--grey-light);
  padding: 10px 24px; font-family: 'Montserrat', sans-serif;
  font-size: 8px; letter-spacing: 3px; text-transform: uppercase;
  cursor: none; transition: all 0.3s; color: var(--grey);
}
.filter-btn.active, .filter-btn:hover {
  background: var(--black); color: var(--cream); border-color: var(--black);
}

.products-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2px;
}

.product-card {
  background: var(--cream-dark);
  cursor: none;
  position: relative; overflow: hidden;
  animation: fadeUp 0.7s ease forwards; opacity: 0;
}
.product-card:nth-child(1) { animation-delay: 0.1s; }
.product-card:nth-child(2) { animation-delay: 0.2s; }
.product-card:nth-child(3) { animation-delay: 0.3s; }
.product-card:nth-child(4) { animation-delay: 0.4s; }
.product-card:nth-child(5) { animation-delay: 0.5s; }
.product-card:nth-child(6) { animation-delay: 0.6s; }
.product-card:nth-child(7) { animation-delay: 0.7s; }
.product-card:nth-child(8) { animation-delay: 0.8s; }

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.product-image {
  aspect-ratio: 3/4;
  background: var(--black);
  display: flex; align-items: center; justify-content: center;
  position: relative; overflow: hidden;
}

.product-image-inner {
  width: 100%; height: 100%;
  display: flex; align-items: center; justify-content: center;
  transition: transform 0.6s ease;
}
.product-card:hover .product-image-inner { transform: scale(1.05); }

.product-overlay {
  position: absolute; inset: 0;
  background: rgba(0,0,0,0.4);
  display: flex; align-items: center; justify-content: center;
  opacity: 0; transition: opacity 0.3s;
}
.product-card:hover .product-overlay { opacity: 1; }
.overlay-btn {
  background: var(--cream); color: var(--black);
  border: none; padding: 12px 28px;
  font-family: 'Montserrat', sans-serif;
  font-size: 8px; letter-spacing: 3px; text-transform: uppercase;
  cursor: none; transform: translateY(10px);
  transition: transform 0.3s ease;
}
.product-card:hover .overlay-btn { transform: translateY(0); }

.product-badge {
  position: absolute; top: 16px; left: 16px;
  background: var(--black); color: var(--cream);
  font-size: 7px; letter-spacing: 2px; text-transform: uppercase;
  padding: 4px 10px; font-weight: 300;
}
.product-badge.new { background: #c9a96e; }

.product-info {
  padding: 20px;
}
.product-category {
  font-size: 7px; letter-spacing: 3px; text-transform: uppercase;
  color: var(--grey); font-weight: 200; margin-bottom: 6px;
}
.product-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 18px; font-weight: 400; margin-bottom: 4px;
  letter-spacing: 0.5px;
}
.product-colors {
  display: flex; gap: 6px; margin-bottom: 12px;
}
.color-dot {
  width: 12px; height: 12px; border-radius: 50%;
  border: 0.5px solid var(--grey-light); cursor: none;
  transition: transform 0.2s;
}
.color-dot:hover { transform: scale(1.3); }
.product-footer {
  display: flex; align-items: center; justify-content: space-between;
}
.product-price {
  font-family: 'Playfair Display', serif;
  font-size: 18px; font-weight: 300;
}
.add-to-cart {
  background: transparent; border: 0.5px solid var(--black);
  width: 32px; height: 32px;
  display: flex; align-items: center; justify-content: center;
  cursor: none; transition: all 0.3s; font-size: 16px;
}
.add-to-cart:hover { background: var(--black); color: var(--cream); }

/* ── PANIER SIDEBAR ── */
.cart-sidebar {
  position: fixed; top: 0; right: -420px; width: 420px; height: 100vh;
  background: var(--cream); z-index: 200;
  display: flex; flex-direction: column;
  border-left: 0.5px solid var(--grey-light);
  transition: right 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: -20px 0 60px rgba(0,0,0,0.1);
}
.cart-sidebar.open { right: 0; }
.cart-overlay-bg {
  position: fixed; inset: 0; background: rgba(0,0,0,0.3);
  z-index: 199; opacity: 0; pointer-events: none;
  transition: opacity 0.4s;
}
.cart-overlay-bg.open { opacity: 1; pointer-events: all; }

.cart-header {
  padding: 32px 32px 24px;
  border-bottom: 0.5px solid var(--grey-light);
  display: flex; align-items: center; justify-content: space-between;
}
.cart-title {
  font-family: 'Playfair Display', serif;
  font-size: 22px; font-weight: 300;
}
.cart-close {
  background: none; border: none; cursor: none;
  font-size: 20px; color: var(--grey);
  transition: color 0.2s;
}
.cart-close:hover { color: var(--black); }

.cart-items {
  flex: 1; overflow-y: auto; padding: 24px 32px;
  display: flex; flex-direction: column; gap: 24px;
}
.cart-empty {
  text-align: center; padding: 60px 0;
  color: var(--grey); font-size: 11px; letter-spacing: 2px;
  text-transform: uppercase; font-weight: 200;
}
.cart-item {
  display: flex; gap: 16px; align-items: center;
}
.cart-item-img {
  width: 70px; height: 90px; background: var(--black-soft);
  flex-shrink: 0; display: flex; align-items: center; justify-content: center;
}
.cart-item-info { flex: 1; }
.cart-item-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 16px; margin-bottom: 4px;
}
.cart-item-color {
  font-size: 8px; letter-spacing: 2px; color: var(--grey);
  text-transform: uppercase; margin-bottom: 8px;
}
.cart-item-qty {
  display: flex; align-items: center; gap: 12px;
}
.qty-btn {
  background: none; border: 0.5px solid var(--grey-light);
  width: 24px; height: 24px; cursor: none;
  display: flex; align-items: center; justify-content: center;
  font-size: 14px; transition: all 0.2s;
}
.qty-btn:hover { background: var(--black); color: var(--cream); border-color: var(--black); }
.qty-num { font-size: 12px; font-weight: 300; min-width: 20px; text-align: center; }
.cart-item-price {
  font-family: 'Playfair Display', serif;
  font-size: 16px; font-weight: 300; margin-left: auto;
}
.remove-btn {
  background: none; border: none; cursor: none;
  color: var(--grey); font-size: 12px; transition: color 0.2s;
}
.remove-btn:hover { color: var(--black); }

.cart-footer {
  padding: 24px 32px; border-top: 0.5px solid var(--grey-light);
}
.cart-subtotal {
  display: flex; justify-content: space-between;
  margin-bottom: 8px;
}
.cart-subtotal span:first-child {
  font-size: 9px; letter-spacing: 3px; text-transform: uppercase;
  color: var(--grey); font-weight: 200;
}
.cart-subtotal span:last-child {
  font-family: 'Playfair Display', serif; font-size: 22px; font-weight: 300;
}
.cart-shipping {
  font-size: 8px; letter-spacing: 2px; text-transform: uppercase;
  color: var(--grey); font-weight: 200; margin-bottom: 24px;
}
.checkout-btn {
  width: 100%; background: var(--black); color: var(--cream);
  border: none; padding: 18px;
  font-family: 'Montserrat', sans-serif;
  font-size: 9px; letter-spacing: 4px; text-transform: uppercase;
  cursor: none; transition: all 0.3s;
}
.checkout-btn:hover { background: var(--black-soft); letter-spacing: 6px; }

/* ── ABOUT ── */
.about-section {
  display: grid; grid-template-columns: 1fr 1fr;
  min-height: 70vh;
}
.about-left {
  background: var(--black);
  display: flex; align-items: center; justify-content: center;
  padding: 80px;
}
.about-right {
  padding: 80px 60px;
  display: flex; flex-direction: column; justify-content: center; gap: 28px;
}
.about-number {
  font-family: 'Playfair Display', serif;
  font-size: 80px; font-weight: 300; color: var(--grey-light);
  line-height: 1;
}
.about-title {
  font-family: 'Playfair Display', serif;
  font-size: 36px; font-weight: 300; line-height: 1.2;
}
.about-title em { font-style: italic; color: var(--grey); }
.about-text {
  font-size: 11px; line-height: 2.2; color: var(--grey);
  font-weight: 200; max-width: 440px;
}
.about-stats {
  display: flex; gap: 40px; padding-top: 16px;
  border-top: 0.5px solid var(--grey-light);
}
.stat { display: flex; flex-direction: column; gap: 4px; }
.stat-num {
  font-family: 'Playfair Display', serif;
  font-size: 28px; font-weight: 300;
}
.stat-label {
  font-size: 7px; letter-spacing: 3px; text-transform: uppercase;
  color: var(--grey); font-weight: 200;
}

/* ── NEWSLETTER ── */
.newsletter {
  background: var(--black); padding: 80px 60px;
  text-align: center;
  display: flex; flex-direction: column; align-items: center; gap: 32px;
}
.newsletter-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(28px, 4vw, 48px); font-weight: 300;
  color: var(--cream); line-height: 1.1;
}
.newsletter-title em { font-style: italic; color: rgba(242,237,228,0.4); }
.newsletter-form {
  display: flex; gap: 0; max-width: 480px; width: 100%;
}
.newsletter-input {
  flex: 1; background: transparent;
  border: 0.5px solid rgba(255,255,255,0.2); border-right: none;
  padding: 16px 24px; color: var(--cream);
  font-family: 'Montserrat', sans-serif; font-size: 11px;
  letter-spacing: 1px; outline: none;
}
.newsletter-input::placeholder { color: rgba(255,255,255,0.3); }
.newsletter-btn {
  background: var(--cream); color: var(--black);
  border: none; padding: 16px 28px;
  font-family: 'Montserrat', sans-serif; font-size: 8px;
  letter-spacing: 3px; text-transform: uppercase; cursor: none;
  transition: all 0.3s;
}
.newsletter-btn:hover { background: #c9a96e; color: white; }

/* ── FOOTER ── */
footer {
  background: var(--cream-dark);
  padding: 60px;
  display: grid; grid-template-columns: 2fr 1fr 1fr 1fr;
  gap: 60px; border-top: 0.5px solid var(--grey-light);
}
.footer-brand { display: flex; flex-direction: column; gap: 16px; }
.footer-brand-name {
  font-family: 'Playfair Display', serif;
  font-size: 20px; font-weight: 400; letter-spacing: 3px;
  text-transform: uppercase;
}
.footer-brand-desc {
  font-size: 10px; line-height: 2; color: var(--grey);
  font-weight: 200; max-width: 260px;
}
.footer-col h4 {
  font-size: 8px; letter-spacing: 4px; text-transform: uppercase;
  font-weight: 300; margin-bottom: 20px; color: var(--black);
}
.footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
.footer-col a {
  font-size: 10px; color: var(--grey); text-decoration: none;
  font-weight: 200; letter-spacing: 1px; transition: color 0.2s;
}
.footer-col a:hover { color: var(--black); }
.footer-bottom {
  padding: 20px 60px;
  display: flex; align-items: center; justify-content: space-between;
  border-top: 0.5px solid var(--grey-light);
  background: var(--cream-dark);
}
.footer-bottom p {
  font-size: 8px; letter-spacing: 2px; color: var(--grey);
  text-transform: uppercase; font-weight: 200;
}

/* ── TOAST ── */
.toast {
  position: fixed; bottom: 40px; left: 50%; transform: translateX(-50%) translateY(100px);
  background: var(--black); color: var(--cream);
  padding: 14px 32px; font-size: 9px; letter-spacing: 3px; text-transform: uppercase;
  z-index: 300; transition: transform 0.4s cubic-bezier(0.4,0,0.2,1);
  pointer-events: none;
}
.toast.show { transform: translateX(-50%) translateY(0); }

/* ── RESPONSIVE ── */
@media (max-width: 768px) {
  nav { padding: 16px 24px; }
  .nav-links { display: none; }
  .hero { grid-template-columns: 1fr; }
  .hero-right { height: 300px; }
  .hero-left { padding: 40px 24px; }
  .products-grid { grid-template-columns: repeat(2, 1fr); }
  .about-section { grid-template-columns: 1fr; }
  .about-left { display: none; }
  footer { grid-template-columns: 1fr 1fr; padding: 40px 24px; gap: 40px; }
  .cart-sidebar { width: 100%; right: -100%; }
}
</style>
</head>
<body>

<!-- Cursor -->
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- Cart Overlay -->
<div class="cart-overlay-bg" id="cartOverlay" onclick="toggleCart()"></div>

<!-- Toast -->
<div class="toast" id="toast">Ajouté au panier</div>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <span class="bags">Bags</span>
    <span class="collection">Collection</span>
    <span class="paris-tag">Paris</span>
  </div>
  <ul class="nav-links">
    <li><a href="#products">Collection</a></li>
    <li><a href="#about">À propos</a></li>
    <li><a href="#newsletter">Contact</a></li>
  </ul>
  <div class="nav-right">
    <button class="cart-btn" onclick="toggleCart()">
      Panier
      <span class="cart-count" id="cartCount">0</span>
    </button>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-tag">Collection Été 2026</div>
    <h1 class="hero-title">
      L'été,<br>
      porté avec<br>
      <em>élégance.</em>
    </h1>
    <p class="hero-desc">
      Des sacs et accessoires estivaux pensés pour celles et ceux qui vivent l'été avec style. Minimalistes, durables, parisiens.
    </p>
    <div class="hero-cta">
      <a href="#products" class="btn-primary">Découvrir</a>
      <a href="#about" class="btn-secondary">Notre histoire</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-image-placeholder">
      <svg class="hero-bag-svg" width="200" height="240" viewBox="0 0 200 240" fill="none">
        <rect x="40" y="80" width="120" height="140" rx="2" stroke="white" stroke-width="1.5"/>
        <path d="M70 80 C70 55 130 55 130 80" stroke="white" stroke-width="1.5" fill="none"/>
        <line x1="40" y1="110" x2="160" y2="110" stroke="white" stroke-width="0.5" opacity="0.4"/>
        <rect x="85" y="92" width="30" height="18" rx="1" stroke="white" stroke-width="0.8" fill="none"/>
        <circle cx="100" cy="101" r="3" stroke="white" stroke-width="0.8" fill="none"/>
      </svg>
      <svg width="140" height="1" style="opacity:0.1"><rect width="140" height="1" fill="white"/></svg>
      <div style="font-family:'Cormorant Garamond',serif;font-style:italic;font-size:13px;letter-spacing:4px;color:rgba(255,255,255,0.2)">Summer 2026</div>
    </div>
    <div class="hero-overlay-text">Bags Collection · Paris</div>
    <div class="floating-badge">
      <span>20€</span>
      <span>Dès</span>
    </div>
  </div>
</section>
<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track">
    <span class="marquee-item">Tote Bags Estivaux</span>
    <span class="marquee-item">Accessoires d'Été</span>
    <span class="marquee-item">Livraison France</span>
    <span class="marquee-item">Collection 2026</span>
    <span class="marquee-item">Paris</span>
    <span class="marquee-item">Tote Bags Estivaux</span>
    <span class="marquee-item">Accessoires d'Été</span>
    <span class="marquee-item">Livraison France</span>
    <span class="marquee-item">Collection 2026</span>
    <span class="marquee-item">Paris</span>
  </div>
</div>

<!-- PRODUITS -->
<section id="products">
  <div class="section-header">
    <div class="section-tag">Notre Sélection</div>
    <h2 class="section-title">La Collection <em>Été</em></h2>
  </div>

  <div class="products-section">
    <div class="products-filter">
      <button class="filter-btn active" onclick="filterProducts('all', this)">Tout</button>
      <button class="filter-btn" onclick="filterProducts('tote', this)">Tote Bags</button>
      <button class="filter-btn" onclick="filterProducts('accessoire', this)">Accessoires</button>
      <button class="filter-btn" onclick="filterProducts('bain', this)">Bain</button>
    </div>

    <div class="products-grid" id="productsGrid">

      <!-- Produit 1 -->
      <div class="product-card" data-category="tote">
        <div class="product-image">
          <div class="product-image-inner">
            <svg width="100" height="120" viewBox="0 0 100 120" fill="none">
              <rect x="15" y="35" width="70" height="75" rx="1" stroke="white" stroke-width="1"/>
              <path d="M30 35 C30 18 70 18 70 35" stroke="white" stroke-width="1" fill="none"/>
              <line x1="15" y1="55" x2="85" y2="55" stroke="white" stroke-width="0.4" opacity="0.4"/>
            </svg>
          </div>
          <div class="product-overlay">
            <button class="overlay-btn" onclick="addToCart('Tote Bag Sable', 20, 'Sable', this)">Ajouter</button>
          </div>
          <div class="product-badge new">Nouveau</div>
        </div>
        <div class="product-info">
          <div class="product-category">Tote Bag</div>
          <div class="product-name">Le Classique</div>
          <div class="product-colors">
            <div class="color-dot" style="background:#c8b89a" title="Sable"></div>
            <div class="color-dot" style="background:#1a1a1a" title="Noir"></div>
            <div class="color-dot" style="background:#f5f0e8" title="Crème"></div>
          </div>
          <div class="product-footer">
            <span class="product-price">20 €</span>
            <button class="add-to-cart" onclick="addToCart('Tote Bag Le Classique', 20, 'Sable', this)">+</button>
          </div>
        </div>
      </div>

      <!-- Produit 2 -->
      <div class="product-card" data-category="tote">
        <div class="product-image" style="background:#1a2a3a">
          <div class="product-image-inner">
            <svg width="100" height="120" viewBox="0 0 100 120" fill="none">
              <rect x="10" y="30" width="80" height="80" rx="1" stroke="white" stroke-width="1"/>
              <path d="M25 30 C25 10 75 10 75 30" stroke="white" stroke-width="1" fill="none"/>
              <rect x="38" y="42" width="24" height="14" rx="0.5" stroke="white" stroke-width="0.6" fill="none"/>
            </svg>
          </div>
          <div class="product-overlay">
            <button class="overlay-btn" onclick="addToCart('Tote Bag Oversize Bleu', 20, 'Bleu ciel', this)">Ajouter</button>
          </div>
        </div>
        <div class="product-info">
          <div class="product-category">Tote Bag</div>
          <div class="product-name">L'Oversize</div>
          <div class="product-colors">
            <div class="color-dot" style="background:#87ceeb" title="Bleu ciel"></div>
            <div class="color-dot" style="background:#8fbc8f" title="Vert sauge"></div>
            <div class="color-dot" style="background:#ffb6c1" title="Rose poudré"></div>
          </div>
          <div class="product-footer">
            <span class="product-price">20 €</span>
            <button class="add-to-cart" onclick="addToCart('Tote Bag L\'Oversize', 20, 'Bleu ciel', this)">+</button>
          </div>
        </div>
      </div>

      <!-- Produit 3 -->
      <div class="product-card" data-category="accessoire">
        <div class="product-image" style="background:#2a1a0a">
          <div class="product-image-inner">
            <svg width="80" height="100" viewBox="0 0 80 100" fill="none">
              <ellipse cx="40" cy="55" rx="28" ry="35" stroke="white" stroke-width="1"/>
              <path d="M20 35 Q40 10 60 35" stroke="white" stroke-width="1" fill="none"/>
              <line x1="12" y1="55" x2="68" y2="55" stroke="white" stroke-width="0.4" opacity="0.3"/>
            </svg>
          </div>
          <div class="product-overlay">
            <button class="overlay-btn" onclick="addToCart('Sac Filet Naturel', 20, 'Naturel', this)">Ajouter</button>
          </div>
          <div class="product-badge">Été</div>
        </div>
        <div class="product-info">
          <div class="product-category">Sac Filet</div>
          <div class="product-name">Le Filet</div>
          <div class="product-colors">
            <div class="color-dot" style="background:#d4a76a" title="Naturel"></div>
            <div class="color-dot" style="background:#fff" title="Blanc" style="border:1px solid #ddd"></div>
          </div>
          <div class="product-footer">
            <span class="product-price">20 €</span>
            <button class="add-to-cart" onclick="addToCart('Sac Filet', 20, 'Naturel', this)">+</button>
          </div>
        </div>
      </div>

      <!-- Produit 4 -->
      <div class="product-card" data-category="tote">
        <div class="product-image" style="background:#0a1a0a">
          <div class="product-image-inner">
            <svg width="70" height="90" viewBox="0 0 70 90" fill="none">
              <rect x="10" y="25" width="50" height="55" rx="1" stroke="white" stroke-width="1"/>
              <path d="M22 25 C22 12 48 12 48 25" stroke="white" stroke-width="1" fill="none"/>
              <rect x="28" y="35" width="14" height="10" rx="0.5" stroke="white" stroke-width="0.6" fill="none"/>
            </svg>
          </div>
          <div class="product-overlay">
            <button class="overlay-btn" onclick="addToCart('Mini Tote Vert', 20, 'Vert sauge', this)">Ajouter</button>
          </div>
        </div>
        <div class="product-info">
          <div class="product-category">Mini Tote</div>
          <div class="product-name">Le Mini</div>
          <div class="product-colors">
            <div class="color-dot" style="background:#8fbc8f" title="Vert sauge"></div>
            <div class="color-dot" style="background:#c8b89a" title="Sable"></div>
            <div class="color-dot" style="background:#1a1a1a" title="Noir"></div>
            <div class="color-dot" style="background:#ffb6c1" title="Rose"></div>
          </div>
          <div class="product-footer">
            <span class="product-price">20 €</span>
            <button class="add-to-cart" onclick="addToCart('Mini Tote', 20, 'Vert sauge', this)">+</button>
          </div>
        </div>
      </div>

      <!-- Produit 5 -->
      <div class="product-card" data-category="accessoire">
        <div class="product-image" style="background:#1a1a2a">
          <div class="product-image-inner">
            <svg width="120" height="60" viewBox="0 0 120 60" fill="none">
              <rect x="10" y="20" width="100" height="25" rx="12" stroke="white" stroke-width="1"/>
              <rect x="45" y="15" width="30" height="8" rx="4" stroke="white" stroke-width="0.8" fill="none"/>
              <circle cx="60" cy="19" r="3" stroke="white" stroke-width="0.6" fill="none"/>
            </svg>
          </div>
          <div class="product-overlay">
            <button class="overlay-btn" onclick="addToCart('Chapeau de Plage', 20, 'Naturel', this)">Ajouter</button>
          </div>
          <div class="product-badge new">Nouveau</div>
        </div>
        <div class="product-info">
          <div class="product-category">Accessoire</div>
          <div class="product-name">Le Bob</div>
          <div class="product-colors">
            <div class="color-dot" style="background:#d4a76a" title="Naturel"></div>
            <div class="color-dot" style="background:#1a1a1a" title="Noir"></div>
            <div class="color-dot" style="background:#fff" title="Blanc"></div>
          </div>
          <div class="product-footer">
            <span class="product-price">20 €</span>
            <button class="add-to-cart" onclick="addToCart('Le Bob', 20, 'Naturel', this)">+</button>
          </div>
        </div>
      </div>

      <!-- Produit 6 -->
      <div class="product-card" data-category="bain">
        <div class="product-image" style="background:#0a1a2a">
          <div class="product-image-inner">
            <svg width="90" height="110" viewBox="0 0 90 110" fill="none">
              <rect x="15" y="10" width="60" height="90" rx="2" stroke="white" stroke-width="1"/>
              <line x1="15" y1="35" x2="75" y2="35" stroke="white" stroke-width="0.4" opacity="0.5"/>
              <line x1="15" y1="60" x2="75" y2="60" stroke="white" stroke-width="0.4" opacity="0.3"/>
              <line x1="15" y1="85" x2="75" y2="85" stroke="white" stroke-width="0.4" opacity="0.2"/>
            </svg>
          </div>
          <div class="product-overlay">
            <button class="overlay-btn" onclick="addToCart('Serviette de Plage', 20, 'Bleu', this)">Ajouter</button>
          </div>
        </div>
        <div class="product-info">
          <div class="product-category">Bain</div>
          <div class="product-name">La Serviette</div>
          <div class="product-colors">
            <div class="color-dot" style="background:#87ceeb" title="Bleu"></div>
            <div class="color-dot" style="background:#ffb6c1" title="Rose"></div>
            <div class="color-dot" style="background:#c8b89a" title="Sable"></div>
          </div>
          <div class="product-footer">
            <span class="product-price">20 €</span>
            <button class="add-to-cart" onclick="addToCart('Serviette de Plage', 20, 'Bleu', this)">+</button>
          </div>
        </div>
      </div>

      <!-- Produit 7 -->
      <div class="product-card" data-category="accessoire">
        <div class="product-image" style="background:#1a0a0a">
          <div class="product-image-inner">
            <svg width="100" height="80" viewBox="0 0 100 80" fill="none">
              <rect x="15" y="25" width="70" height="35" rx="17" stroke="white" stroke-width="1"/>
              <circle cx="50" cy="42" r="8" stroke="white" stroke-width="0.8" fill="none"/>
              <circle cx="50" cy="42" r="3" stroke="white" stroke-width="0.6" fill="none"/>
            </svg>
          </div>
          <div class="product-overlay">
            <button class="overlay-btn" onclick="addToCart('Lunettes de Soleil', 20, 'Noir', this)">Ajouter</button>
          </div>
          <div class="product-badge">Été</div>
        </div>
        <div class="product-info">
          <div class="product-category">Accessoire</div>
          <div class="product-name">Les Lunettes</div>
          <div class="product-colors">
            <div class="color-dot" style="background:#1a1a1a" title="Noir"></div>
            <div class="color-dot" style="background:#c8a86e" title="Tortoise"></div>
          </div>
          <div class="product-footer">
            <span class="product-price">20 €</span>
            <button class="add-to-cart" onclick="addToCart('Lunettes de Soleil', 20, 'Noir', this)">+</button>
          </div>
        </div>
      </div>

      <!-- Produit 8 -->
      <div class="product-card" data-category="tote">
        <div class="product-image" style="background:#0a0a1a">
          <div class="product-image-inner">
            <svg width="100" height="120" viewBox="0 0 100 120" fill="none">
              <rect x="20" y="40" width="60" height="70" rx="1" stroke="white" stroke-width="1"/>
              <path d="M33 40 L20 15 M67 40 L80 15" stroke="white" stroke-width="1"/>
              <line x1="20" y1="60" x2="80" y2="60" stroke="white" stroke-width="0.4" opacity="0.4"/>
            </svg>
          </div>
          <div class="product-overlay">
            <button class="overlay-btn" onclick="addToCart('Tote Bag Premium', 20, 'Noir', this)">Ajouter</button>
          </div>
          <div class="product-badge new">Nouveau</div>
        </div>
        <div class="product-info">
          <div class="product-category">Tote Bag</div>
          <div class="product-name">Le Premium</div>
          <div class="product-colors">
            <div class="color-dot" style="background:#1a1a1a" title="Noir"></div>
            <div class="color-dot" style="background:#f5f0e8" title="Crème"></div>
          </div>
          <div class="product-footer">
            <span class="product-price">20 €</span>
            <button class="add-to-cart" onclick="addToCart('Tote Bag Premium', 20, 'Noir', this)">+</button>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about" class="about-section">
  <div class="about-left">
    <svg width="200" height="200" viewBox="0 0 200 200" fill="none" opacity="0.15">
      <circle cx="100" cy="100" r="80" stroke="white" stroke-width="0.5"/>
      <circle cx="100" cy="100" r="60" stroke="white" stroke-width="0.5"/>
      <circle cx="100" cy="100" r="40" stroke="white" stroke-width="0.5"/>
      <line x1="20" y1="100" x2="180" y2="100" stroke="white" stroke-width="0.5"/>
      <line x1="100" y1="20" x2="100" y2="180" stroke="white" stroke-width="0.5"/>
    </svg>
  </div>
  <div class="about-right">
    <div class="about-number">01</div>
    <h2 class="about-title">L'été commence<br><em>ici, à Paris.</em></h2>
    <p class="about-text">
      Bags Collection est née d'une passion simple : porter l'été avec élégance, sans se ruiner. Chaque sac, chaque accessoire est sélectionné pour sa qualité, son style et sa praticité.
      <br><br>
      Basée à Paris, notre collection s'inspire de la Méditerranée — ses couleurs, ses textures, sa légèreté.
    </p>
    <div class="about-stats">
      <div class="stat">
        <span class="stat-num">8+</span>
        <span class="stat-label">Produits</span>
      </div>
      <div class="stat">
        <span class="stat-num">6</span>
        <span class="stat-label">Coloris</span>
      </div>
      <div class="stat">
        <span class="stat-num">20€</span>
        <span class="stat-label">Prix unique</span>
      </div>
    </div>
  </div>
</section>

<!-- NEWSLETTER -->
<section id="newsletter" class="newsletter">
  <div class="section-tag" style="color:rgba(242,237,228,0.4)">Restez connectés</div>
  <h2 class="newsletter-title">
    L'été dans<br><em>votre boîte mail.</em>
  </h2>
  <div class="newsletter-form">
    <input type="email" class="newsletter-input" placeholder="votre@email.com">
    <button class="newsletter-btn">S'inscrire</button>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-brand">
    <div class="footer-brand-name">Bags Collection</div>
    <p class="footer-brand-desc">Des sacs et accessoires estivaux pensés à Paris, pour vivre l'été avec style.</p>
  </div>
  <div class="footer-col">
    <h4>Collection</h4>
    <ul>
      <li><a href="#">Tote Bags</a></li>
      <li><a href="#">Accessoires</a></li>
      <li><a href="#">Bain</a></li>
      <li><a href="#">Nouveautés</a></li>
    </ul>
  </div>
  <div class="footer-col">
    <h4>Infos</h4>
    <ul>
      <li><a href="#">À propos</a></li>
      <li><a href="#">Livraison</a></li>
      <li><a href="#">Retours</a></li>
      <li><a href="#">FAQ</a></li>
    </ul>
  </div>
  <div class="footer-col">
    <h4>Suivez-nous</h4>
    <ul>
      <li><a href="#">Instagram</a></li>
      <li><a href="#">TikTok</a></li>
      <li><a href="#">Pinterest</a></li>
    </ul>
  </div>
</footer>
<div class="footer-bottom">
  <p>© 2026 Bags Collection · Paris</p>
  <p>Mentions légales · CGV · Confidentialité</p>
</div>

<!-- PANIER -->
<div class="cart-sidebar" id="cartSidebar">
  <div class="cart-header">
    <span class="cart-title">Mon Panier</span>
    <button class="cart-close" onclick="toggleCart()">✕</button>
  </div>
  <div class="cart-items" id="cartItems">
    <div class="cart-empty" id="cartEmpty">Votre panier est vide</div>
  </div>
  <div class="cart-footer">
    <div class="cart-subtotal">
      <span>Total</span>
      <span id="cartTotal">0 €</span>
    </div>
    <p class="cart-shipping">Livraison offerte dès 40€</p>
    <button class="checkout-btn">Commander</button>
  </div>
</div>

<script>
// ── CURSOR ──
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursorRing');
document.addEventListener('mousemove', e => {
  cursor.style.transform = `translate(${e.clientX - 5}px, ${e.clientY - 5}px)`;
  ring.style.transform = `translate(${e.clientX - 18}px, ${e.clientY - 18}px)`;
});
document.querySelectorAll('button, a, .product-card').forEach(el => {
  el.addEventListener('mouseenter', () => { cursor.classList.add('hover'); ring.classList.add('hover'); });
  el.addEventListener('mouseleave', () => { cursor.classList.remove('hover'); ring.classList.remove('hover'); });
});

// ── CART ──
let cart = [];
function toggleCart() {
  document.getElementById('cartSidebar').classList.toggle('open');
  document.getElementById('cartOverlay').classList.toggle('open');
}

function addToCart(name, price, color, btn) {
  const existing = cart.find(i => i.name === name && i.color === color);
  if (existing) { existing.qty++; }
  else { cart.push({ name, price, color, qty: 1 }); }
  updateCart();
  showToast();
}

function updateCart() {
  const count = cart.reduce((s, i) => s + i.qty, 0);
  const total = cart.reduce((s, i) => s + i.price * i.qty, 0);
  document.getElementById('cartCount').textContent = count;
  document.getElementById('cartTotal').textContent = total + ' €';

  const itemsEl = document.getElementById('cartItems');
  const emptyEl = document.getElementById('cartEmpty');

  if (cart.length === 0) {
    emptyEl.style.display = 'block';
    const items = itemsEl.querySelectorAll('.cart-item');
    items.forEach(i => i.remove());
    return;
  }
  emptyEl.style.display = 'none';
  itemsEl.querySelectorAll('.cart-item').forEach(i => i.remove());

  cart.forEach((item, idx) => {
    const el = document.createElement('div');
    el.className = 'cart-item';
    el.innerHTML = `
      <div class="cart-item-img">
        <svg width="30" height="38" viewBox="0 0 30 38" fill="none">
          <rect x="4" y="10" width="22" height="24" stroke="white" stroke-width="0.8"/>
          <path d="M9 10 C9 4 21 4 21 10" stroke="white" stroke-width="0.8" fill="none"/>
        </svg>
      </div>
      <div class="cart-item-info">
        <div class="cart-item-name">${item.name}</div>
        <div class="cart-item-color">${item.color}</div>
        <div class="cart-item-qty">
          <button class="qty-btn" onclick="changeQty(${idx}, -1)">−</button>
          <span class="qty-num">${item.qty}</span>
          <button class="qty-btn" onclick="changeQty(${idx}, 1)">+</button>
          <button class="remove-btn" onclick="removeItem(${idx})">✕</button>
        </div>
      </div>
      <div class="cart-item-price">${item.price * item.qty} €</div>
    `;
    itemsEl.appendChild(el);
  });
}

function changeQty(idx, delta) {
  cart[idx].qty += delta;
  if (cart[idx].qty <= 0) cart.splice(idx, 1);
  updateCart();
}
function removeItem(idx) {
  cart.splice(idx, 1);
  updateCart();
}

function showToast() {
  const t = document.getElementById('toast');
  t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 2500);
}

// ── FILTER ──
function filterProducts(cat, btn) {
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  document.querySelectorAll('.product-card').forEach(card => {
    if (cat === 'all' || card.dataset.category === cat) {
      card.style.display = '';
    } else {
      card.style.display = 'none';
    }
  });
}
</script>
</body>
</html>