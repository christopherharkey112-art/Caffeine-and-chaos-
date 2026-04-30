<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Caffeine & Chaos — Crestview, FL</title>
<link href="https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Permanent+Marker&family=DM+Sans:wght@300;400;500&family=Bebas+Neue&display=swap" rel="stylesheet">
<style>
:root {
--black: #0a0807;
--dark: #141210;
--card: #1c1816;
--orange: #f97316;
--gold: #f59e0b;
--cream: #fef3c7;
--white: #fafaf8;
--muted: #a8998a;
--border: #2a2420;
}

- { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; }

body {
background: var(–black);
color: var(–white);
font-family: ‘DM Sans’, sans-serif;
overflow-x: hidden;
}

/* grain overlay */
body::after {
content: ‘’;
position: fixed;
inset: 0;
pointer-events: none;
z-index: 999;
opacity: 0.35;
background-image: url(“data:image/svg+xml,%3Csvg xmlns=‘http://www.w3.org/2000/svg’ width=‘300’ height=‘300’%3E%3Cfilter id=‘n’%3E%3CfeTurbulence type=‘fractalNoise’ baseFrequency=‘0.75’ numOctaves=‘4’ stitchTiles=‘stitch’/%3E%3C/filter%3E%3Crect width=‘300’ height=‘300’ filter=‘url(%23n)’ opacity=‘0.08’/%3E%3C/svg%3E”);
}

/* ── NAV ── */
nav {
position: fixed; top: 0; left: 0; right: 0; z-index: 200;
display: flex; align-items: center; justify-content: space-between;
padding: 1.1rem 3rem;
background: rgba(10,8,7,0.88);
backdrop-filter: blur(14px);
border-bottom: 1px solid var(–border);
}
.nav-logo {
font-family: ‘Permanent Marker’, cursive;
font-size: 1.45rem;
color: var(–orange);
text-decoration: none;
}
.nav-links { display: flex; gap: 2.4rem; list-style: none; }
.nav-links a {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 1.05rem;
letter-spacing: 2.5px;
color: var(–muted);
text-decoration: none;
transition: color 0.2s;
}
.nav-links a:hover { color: var(–orange); }

/* ── HERO ── */
.hero {
min-height: 100vh;
display: flex; flex-direction: column;
align-items: center; justify-content: center;
text-align: center;
padding: 7rem 2rem 4rem;
position: relative; overflow: hidden;
}
.hero-glow {
position: absolute; inset: 0;
background:
radial-gradient(ellipse 70% 55% at 50% 45%, rgba(249,115,22,0.15) 0%, transparent 70%),
radial-gradient(ellipse 40% 35% at 15% 85%, rgba(245,158,11,0.09) 0%, transparent 60%);
pointer-events: none;
}

/* floating orbs */
.orb {
position: absolute;
border-radius: 50%;
filter: blur(60px);
opacity: 0.18;
animation: drift 8s ease-in-out infinite alternate;
}
.orb1 { width: 350px; height: 350px; background: var(–orange); top: 10%; left: -8%; animation-delay: 0s; }
.orb2 { width: 250px; height: 250px; background: var(–gold); bottom: 15%; right: -5%; animation-delay: 2s; }
.orb3 { width: 180px; height: 180px; background: #ef4444; top: 60%; left: 40%; animation-delay: 4s; }
@keyframes drift {
from { transform: translate(0, 0) scale(1); }
to { transform: translate(30px, -40px) scale(1.1); }
}

.hero-badge {
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 5px; font-size: 0.8rem;
color: var(–orange);
border: 1px solid rgba(249,115,22,0.4);
padding: 0.35rem 1.2rem; border-radius: 999px;
margin-bottom: 1.8rem;
position: relative;
animation: fadeUp 0.7s ease both;
}
.hero-title {
font-family: ‘Abril Fatface’, serif;
font-size: clamp(4rem, 12vw, 9rem);
line-height: 0.92;
position: relative;
animation: fadeUp 0.8s 0.1s ease both;
}
.hero-title span { color: var(–orange); display: block; }
.hero-title em {
font-style: normal;
color: var(–gold);
font-family: ‘Permanent Marker’, cursive;
font-size: 0.55em;
}
.hero-sub {
margin-top: 1.8rem;
font-size: 1.05rem;
color: var(–muted);
max-width: 480px;
line-height: 1.7;
animation: fadeUp 0.8s 0.2s ease both;
}
.hero-buttons {
display: flex; gap: 1rem; margin-top: 2.5rem; flex-wrap: wrap; justify-content: center;
animation: fadeUp 0.8s 0.3s ease both;
}
.btn {
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 2.5px; font-size: 1rem;
padding: 0.85rem 2.2rem; border-radius: 6px;
text-decoration: none; transition: all 0.2s;
cursor: pointer; border: none;
}
.btn-primary {
background: var(–orange); color: var(–black);
}
.btn-primary:hover { background: var(–gold); transform: translateY(-2px); box-shadow: 0 8px 30px rgba(249,115,22,0.4); }
.btn-outline {
background: transparent;
border: 1px solid var(–border);
color: var(–white);
}
.btn-outline:hover { border-color: var(–orange); color: var(–orange); transform: translateY(-2px); }

.hero-scroll {
position: absolute; bottom: 2.5rem;
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 3px; font-size: 0.75rem;
color: var(–muted);
display: flex; flex-direction: column; align-items: center; gap: 0.5rem;
animation: fadeUp 1s 0.6s ease both;
}
.scroll-line {
width: 1px; height: 50px;
background: linear-gradient(to bottom, var(–orange), transparent);
animation: scrollPulse 2s ease-in-out infinite;
}
@keyframes scrollPulse {
0%, 100% { opacity: 1; } 50% { opacity: 0.3; }
}

@keyframes fadeUp {
from { opacity: 0; transform: translateY(28px); }
to { opacity: 1; transform: translateY(0); }
}

/* ── TICKER ── */
.ticker-wrap {
overflow: hidden;
background: var(–orange);
padding: 0.7rem 0;
border-top: 2px solid var(–gold);
border-bottom: 2px solid var(–gold);
}
.ticker {
display: flex; gap: 0;
animation: ticker 25s linear infinite;
white-space: nowrap;
}
.ticker span {
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 3px; font-size: 1rem;
color: var(–black);
padding: 0 2.5rem;
}
.ticker span.dot { color: rgba(0,0,0,0.4); }
@keyframes ticker {
from { transform: translateX(0); }
to { transform: translateX(-50%); }
}

/* ── SECTION COMMONS ── */
section { padding: 7rem 2rem; position: relative; }
.section-label {
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 5px; font-size: 0.78rem;
color: var(–orange); margin-bottom: 1rem;
}
.section-title {
font-family: ‘Abril Fatface’, serif;
font-size: clamp(2.5rem, 6vw, 4.5rem);
line-height: 1.05;
margin-bottom: 1.5rem;
}
.section-title span { color: var(–orange); }
.container { max-width: 1100px; margin: 0 auto; }

/* ── ABOUT ── */
.about { background: var(–dark); }
.about-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 5rem; align-items: center;
}
.about-text p {
color: var(–muted); line-height: 1.8; font-size: 1.05rem;
margin-bottom: 1.2rem;
}
.about-stats {
display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem;
margin-top: 2.5rem;
}
.stat-card {
background: var(–card);
border: 1px solid var(–border);
border-radius: 10px; padding: 1.5rem;
transition: border-color 0.2s, transform 0.2s;
}
.stat-card:hover { border-color: var(–orange); transform: translateY(-3px); }
.stat-num {
font-family: ‘Abril Fatface’, serif;
font-size: 2.8rem; color: var(–orange); line-height: 1;
}
.stat-label { font-size: 0.82rem; color: var(–muted); margin-top: 0.3rem; letter-spacing: 1px; }

/* big decorative text */
.about-deco {
font-family: ‘Permanent Marker’, cursive;
font-size: clamp(3rem, 8vw, 6rem);
color: transparent;
-webkit-text-stroke: 1px rgba(249,115,22,0.25);
line-height: 1.1;
user-select: none;
}

/* ── MENU ── */
.menu { background: var(–black); }
.menu-tabs {
display: flex; gap: 0.6rem; flex-wrap: wrap; margin-bottom: 3rem;
}
.tab {
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 2px; font-size: 0.95rem;
padding: 0.6rem 1.6rem; border-radius: 6px;
background: var(–card); border: 1px solid var(–border);
color: var(–muted); cursor: pointer; transition: all 0.2s;
}
.tab:hover, .tab.active {
background: var(–orange); border-color: var(–orange);
color: var(–black);
}
.menu-grid {
display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
gap: 1.2rem;
}
.menu-item {
background: var(–card);
border: 1px solid var(–border);
border-radius: 10px; padding: 1.4rem 1.6rem;
transition: all 0.22s;
}
.menu-item:hover {
border-color: var(–orange);
transform: translateY(-3px);
box-shadow: 0 8px 25px rgba(249,115,22,0.12);
}
.menu-item-name {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 1.2rem; letter-spacing: 1.5px;
color: var(–white); margin-bottom: 0.4rem;
}
.menu-item-desc { font-size: 0.85rem; color: var(–muted); line-height: 1.5; }
.menu-panel { display: none; }
.menu-panel.active { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1.2rem; }

/* ── HOURS / CONTACT ── */
.contact { background: var(–dark); }
.contact-grid {
display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start;
}
.hours-table { width: 100%; border-collapse: collapse; margin-top: 1.5rem; }
.hours-table tr { border-bottom: 1px solid var(–border); }
.hours-table tr:last-child { border-bottom: none; }
.hours-table td { padding: 0.9rem 0; font-size: 0.97rem; }
.hours-table td:last-child { text-align: right; color: var(–orange); font-weight: 500; }
.hours-table .today td { color: var(–gold); font-weight: 500; }

.info-block { margin-top: 2rem; display: flex; flex-direction: column; gap: 1.2rem; }
.info-item {
display: flex; align-items: flex-start; gap: 1rem;
background: var(–card); border: 1px solid var(–border);
border-radius: 10px; padding: 1.2rem 1.4rem;
transition: border-color 0.2s;
}
.info-item:hover { border-color: var(–orange); }
.info-icon { font-size: 1.4rem; flex-shrink: 0; margin-top: 0.1rem; }
.info-label { font-size: 0.75rem; color: var(–muted); letter-spacing: 1px; margin-bottom: 0.2rem; font-family: ‘Bebas Neue’, sans-serif; }
.info-val { font-size: 0.97rem; color: var(–white); }
.info-val a { color: var(–orange); text-decoration: none; }
.info-val a:hover { text-decoration: underline; }

/* ── REVIEWS ── */
.reviews { background: var(–black); }
.reviews-grid {
display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
gap: 1.5rem; margin-top: 3rem;
}
.review-card {
background: var(–card); border: 1px solid var(–border);
border-radius: 12px; padding: 1.8rem;
transition: all 0.22s;
}
.review-card:hover { border-color: var(–gold); transform: translateY(-3px); }
.stars { color: var(–gold); font-size: 1rem; margin-bottom: 0.8rem; }
.review-text { color: var(–muted); line-height: 1.7; font-size: 0.95rem; font-style: italic; }
.review-author { margin-top: 1.2rem; font-family: ‘Bebas Neue’, sans-serif; letter-spacing: 1.5px; font-size: 0.9rem; color: var(–orange); }

/* ── FOOTER ── */
footer {
background: var(–dark);
border-top: 1px solid var(–border);
padding: 3rem 2rem;
text-align: center;
}
.footer-logo {
font-family: ‘Permanent Marker’, cursive;
font-size: 2rem; color: var(–orange);
margin-bottom: 0.8rem;
}
.footer-tagline { color: var(–muted); font-size: 0.9rem; margin-bottom: 1.8rem; }
.footer-links { display: flex; gap: 2rem; justify-content: center; flex-wrap: wrap; margin-bottom: 2rem; }
.footer-links a {
font-family: ‘Bebas Neue’, sans-serif;
letter-spacing: 2px; font-size: 0.9rem;
color: var(–muted); text-decoration: none; transition: color 0.2s;
}
.footer-links a:hover { color: var(–orange); }
.footer-copy { font-size: 0.8rem; color: #5a4e45; }

/* ── RESPONSIVE ── */
@media (max-width: 768px) {
nav { padding: 1rem 1.5rem; }
.nav-links { gap: 1.4rem; }
.about-grid, .contact-grid { grid-template-columns: 1fr; gap: 3rem; }
.about-stats { grid-template-columns: 1fr 1fr; }
section { padding: 5rem 1.5rem; }
}
@media (max-width: 500px) {
.nav-links { display: none; }
}
</style>

</head>
<body>

<!-- NAV -->

<nav>
<a class="nav-logo" href="#">C&amp;C</a>
<ul class="nav-links">
<li><a href="#about">About</a></li>
<li><a href="#menu">Menu</a></li>
<li><a href="#contact">Visit Us</a></li>
</ul>
</nav>

<!-- HERO -->

<section class="hero" id="home">
<div class="hero-glow"></div>
<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="hero-badge">☕ Crestview's Wildest Coffee Shop</div>
<h1 class="hero-title">
Caffeine
<span>&amp;</span>
<em>Chaos</em>
</h1>
<p class="hero-sub">Locally roasted beans. 100+ flavor combos. House-made sweet cream cold foam. Energy drinks that hit different. Come get your cup.</p>
<div class="hero-buttons">
<a href="#menu" class="btn btn-primary">See the Menu</a>
<a href="#contact" class="btn btn-outline">Find Us</a>
</div>

<div class="hero-scroll">
<div class="scroll-line"></div>
SCROLL
</div>
</section>

<!-- TICKER -->

<div class="ticker-wrap">
<div class="ticker">
<span>ENERGY DRINKS</span><span class="dot">✦</span>
<span>COLD BREW</span><span class="dot">✦</span>
<span>SHAKEN ESPRESSO</span><span class="dot">✦</span>
<span>HOUSE-MADE PASTRIES</span><span class="dot">✦</span>
<span>SWEET CREAM COLD FOAM</span><span class="dot">✦</span>
<span>KIDS DRINKS</span><span class="dot">✦</span>
<span>CHAI &amp; MATCHA</span><span class="dot">✦</span>
<!-- duplicate for seamless loop -->
<span>ENERGY DRINKS</span><span class="dot">✦</span>
<span>COLD BREW</span><span class="dot">✦</span>
<span>SHAKEN ESPRESSO</span><span class="dot">✦</span>
<span>HOUSE-MADE PASTRIES</span><span class="dot">✦</span>
<span>SWEET CREAM COLD FOAM</span><span class="dot">✦</span>
<span>KIDS DRINKS</span><span class="dot">✦</span>
<span>CHAI &amp; MATCHA</span><span class="dot">✦</span>
</div>
</div>

<!-- ABOUT -->

<section class="about" id="about">
<div class="container">
<div class="about-grid">
<div class="about-text">
<div class="section-label">Our Story</div>
<h2 class="section-title">More than just <span>coffee.</span></h2>
<p>Proudly serving locally roasted beans from Crestview, delivered straight to your cup. Classic hand-crafted espresso beverages, fraps ranging from decaf to extra shots, and everything in between.</p>
<p>We specialize in the perfect roast cold brews and our very own house-made sweet cream cold foam — you won't find it anywhere else. With a selection of more than 100 flavor combinations, we're certain to find your perfect cup.</p>
<p>Don't worry tea lovers — we've got chai and matcha with a variety of add-ins too. And don't forget our house-made pastries: muffins, coffee cake, loaves, cake pops and more!</p>

```
<div class="about-stats">
<div class="stat-card">
<div class="stat-num">100+</div>
<div class="stat-label">Flavor Combos</div>
</div>
<div class="stat-card">
<div class="stat-num">4.5★</div>
<div class="stat-label">Google Rating</div>
</div>
<div class="stat-card">
<div class="stat-num">Local</div>
<div class="stat-label">Roasted Beans</div>
</div>
<div class="stat-card">
<div class="stat-num">Daily</div>
<div class="stat-label">Fresh Pastries</div>
</div>
</div>
</div>

<div style="display:flex;flex-direction:column;gap:1.5rem;align-items:center;justify-content:center;">
<div class="about-deco">Fuel<br>the<br>Chaos.</div>
<p style="color:var(--muted);font-size:0.9rem;text-align:center;max-width:260px;line-height:1.6;">Hot or iced — every drink is crafted to order and available your way.</p>
</div>
</div>
```

</div>
</section>

<!-- MENU -->

<section class="menu" id="menu">
<div class="container">
<div class="section-label">What We Serve</div>
<h2 class="section-title">The <span>Menu</span></h2>

```
<div class="menu-tabs">
<button class="tab active" onclick="showTab('energy')">⚡ Energy Drinks</button>
<button class="tab" onclick="showTab('coffee')">☕ Coffee Drinks</button>
<button class="tab" onclick="showTab('kids')">🧋 Kids Drinks</button>
</div>

<!-- Energy Drinks -->
<div class="menu-panel active" id="tab-energy">
<div class="menu-item"><div class="menu-item-name">Swamp Water</div><div class="menu-item-desc">Kiwi • Cherry Lime • Watermelon</div></div>
<div class="menu-item"><div class="menu-item-name">Purple Nerds</div><div class="menu-item-desc">Blue Raspberry • Watermelon • Pomegranate</div></div>
<div class="menu-item"><div class="menu-item-name">Black Magic</div><div class="menu-item-desc">Blackberry • Desert Pear • Pomegranate • Amaretto</div></div>
<div class="menu-item"><div class="menu-item-name">Jamie's Sour Drink</div><div class="menu-item-desc">Blue Raspberry • Cherry Lime</div></div>
<div class="menu-item"><div class="menu-item-name">Cotton Candy Chaos</div><div class="menu-item-desc">Blue Raspberry • Vanilla</div></div>
<div class="menu-item"><div class="menu-item-name">Cherry Lime Volt</div><div class="menu-item-desc">Cherry Lime</div></div>
</div>

<!-- Coffee Drinks -->
<div class="menu-panel" id="tab-coffee">
<div class="menu-item"><div class="menu-item-name">Tabitha's Shaken Espresso</div><div class="menu-item-desc">White Mocha • Toffee Nut</div></div>
<div class="menu-item"><div class="menu-item-name">Whiskey Vanilla</div><div class="menu-item-desc">Bourbon Caramel • Vanilla</div></div>
<div class="menu-item"><div class="menu-item-name">Cinnamon Crunch</div><div class="menu-item-desc">Brown Sugar • Hazelnut</div></div>
<div class="menu-item"><div class="menu-item-name">Butterbeer</div><div class="menu-item-desc">Caramel • Butterscotch</div></div>
<div class="menu-item"><div class="menu-item-name">The Chaos</div><div class="menu-item-desc">Mocha • White Mocha • Bourbon Caramel</div></div>
<div class="menu-item"><div class="menu-item-name">Caramel Chaos</div><div class="menu-item-desc">Mocha • Caramel • Coconut</div></div>
<div class="menu-item"><div class="menu-item-name">Buttery Cinnamon Roll</div><div class="menu-item-desc">Brown Butter Cinnamon Roll</div></div>
<div class="menu-item"><div class="menu-item-name">Brownie Batter</div><div class="menu-item-desc">Mocha • Bourbon Caramel • Hazelnut</div></div>
<div class="menu-item"><div class="menu-item-name">Dubai Chocolate</div><div class="menu-item-desc">Pistachio • Mocha</div></div>
<div class="menu-item"><div class="menu-item-name">Sugar Cookie</div><div class="menu-item-desc">Amaretto • Cookie Butter</div></div>
<div class="menu-item"><div class="menu-item-name">Oatmeal Cream Pie</div><div class="menu-item-desc">Brown Sugar • Toasted</div></div>
<div class="menu-item"><div class="menu-item-name">Pistachio Honeycomb</div><div class="menu-item-desc">Honey • Pistachio</div></div>
<div class="menu-item"><div class="menu-item-name">Whiteout Mocha Madness</div><div class="menu-item-desc">Mocha • Brown Sugar • Vanilla</div></div>
<div class="menu-item"><div class="menu-item-name">Pistachio Dream</div><div class="menu-item-desc">Pistachio • Brown Sugar • Cinnamon</div></div>
<div class="menu-item"><div class="menu-item-name">Toffee Crush</div><div class="menu-item-desc">Toffee Nut • Caramel</div></div>
<div class="menu-item"><div class="menu-item-name">Honey Nut</div><div class="menu-item-desc">Honey • Coconut</div></div>
</div>

<!-- Kids Drinks -->
<div class="menu-panel" id="tab-kids">
<div class="menu-item"><div class="menu-item-name">Cotton Candy</div><div class="menu-item-desc">Sweet & fluffy — a kid favorite</div></div>
<div class="menu-item"><div class="menu-item-name">Caramel</div><div class="menu-item-desc">Classic smooth caramel drink</div></div>
<div class="menu-item"><div class="menu-item-name">Strawberry</div><div class="menu-item-desc">Fresh strawberry flavor</div></div>
<div class="menu-item"><div class="menu-item-name">Mocha</div><div class="menu-item-desc">Chocolate-y and smooth</div></div>
<div class="menu-item"><div class="menu-item-name">Hot Chocolate</div><div class="menu-item-desc">Warm classic hot chocolate</div></div>
<div class="menu-item"><div class="menu-item-name">S'mores Hot Chocolate</div><div class="menu-item-desc">Campfire vibes in a cup</div></div>
<div class="menu-item"><div class="menu-item-name">White Sugar Cookie Hot Chocolate</div><div class="menu-item-desc">Sweet, cozy, and delicious</div></div>
</div>

<p style="margin-top:2rem;color:var(--muted);font-size:0.88rem;">✦ All drinks available hot or iced unless otherwise noted.</p>
```

</div>
</section>

<!-- REVIEWS -->

<section class="reviews" id="reviews">
<div class="container">
<div class="section-label">What People Say</div>
<h2 class="section-title">The <span>Reviews</span> Speak.</h2>
<div class="reviews-grid">
<div class="review-card">
<div class="stars">★★★★★</div>
<p class="review-text">"Absolutely love their cold brew!! The staff is so friendly and sweet — they always make your visit feel special."</p>
<div class="review-author">— Google Review</div>
</div>
<div class="review-card">
<div class="stars">★★★★★</div>
<p class="review-text">"Absolutely delicious coffee and friendly service with a smile. The creative flavor combos are unlike anything else in Crestview."</p>
<div class="review-author">— Google Review</div>
</div>
<div class="review-card">
<div class="stars">★★★★☆</div>
<p class="review-text">"This place makes Starbucks seem like a bargain — but honestly? Worth every penny. The drinks are just that good."</p>
<div class="review-author">— Google Review</div>
</div>
</div>
</div>
</section>

<!-- CONTACT / HOURS -->

<section class="contact" id="contact">
<div class="container">
<div class="section-label">Come See Us</div>
<h2 class="section-title">Hours &amp; <span>Location</span></h2>
<div class="contact-grid">

```
<div>
<table class="hours-table">
<tr><td>Monday</td><td>6 AM – 2 PM</td></tr>
<tr><td>Tuesday</td><td>6 AM – 2 PM</td></tr>
<tr class="today"><td>Wednesday</td><td>6 AM – 2 PM</td></tr>
<tr><td>Thursday</td><td>6 AM – 2 PM</td></tr>
<tr><td>Friday</td><td>6 AM – 2 PM</td></tr>
<tr><td>Saturday</td><td>7 AM – 2 PM</td></tr>
<tr><td>Sunday</td><td>7 AM – 2 PM</td></tr>
</table>
</div>

<div class="info-block">
<div class="info-item">
<div class="info-icon">📍</div>
<div>
<div class="info-label">Address</div>
<div class="info-val"><a href="https://maps.google.com/?q=1212+N+Ferdon+Blvd+Crestview+FL" target="_blank">1212 N Ferdon Blvd<br>Crestview, FL 32536</a></div>
</div>
</div>
<div class="info-item">
<div class="info-icon">📞</div>
<div>
<div class="info-label">Phone</div>
<div class="info-val"><a href="tel:8505858108">(850) 585-8108</a></div>
</div>
</div>
<div class="info-item">
<div class="info-icon">⏱️</div>
<div>
<div class="info-label">Quick Visit</div>
<div class="info-val">Most people spend about 10 minutes — grab your order and go, or stay and enjoy the vibe!</div>
</div>
</div>
<a href="https://maps.google.com/?q=1212+N+Ferdon+Blvd+Crestview+FL" target="_blank" class="btn btn-primary" style="text-align:center;margin-top:0.5rem;">Get Directions</a>
</div>

</div>
```

</div>
</section>

<!-- FOOTER -->

<footer>
<div class="footer-logo">Caffeine &amp; Chaos</div>
<p class="footer-tagline">Crestview's wildest cup — 1212 N Ferdon Blvd</p>
<div class="footer-links">
<a href="#home">Home</a>
<a href="#about">About</a>
<a href="#menu">Menu</a>
<a href="#contact">Visit Us</a>
</div>
<p class="footer-copy">© 2025 Caffeine and Chaos. All rights reserved.</p>
</footer>

<script>
function showTab(name) {
document.querySelectorAll('.menu-panel').forEach(p => p.classList.remove('active'));
document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
document.getElementById('tab-' + name).classList.add('active');
event.target.classList.add('active');
}
</script>

</body>
</html>
# Caffeine-and-chaos-
Fully Functioning website to level up your experience!
