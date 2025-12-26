<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Hot Cup Cafe | Swoyambhu, Kathmandu</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
    scroll-behavior: smooth;
}

body {
    background-color: #f4f1ee;
    color: #333;
}

/* ===== Header ===== */
header {
    background-color: #6f4e37;
    color: white;
    padding: 25px;
    text-align: center;
    animation: fadeDown 1s ease forwards;
}

/* ===== Nav ===== */
nav {
    background-color: #4e342e;
    display: flex;
    justify-content: center;
    padding: 12px;
    position: sticky;
    top: 0;
    z-index: 100;
}

nav a {
    color: white;
    text-decoration: none;
    margin: 0 18px;
    font-weight: bold;
    transition: color 0.3s ease;
}

nav a.active,
nav a:hover {
    color: #ffcc80;
}

/* ===== Sections ===== */
section {
    padding: 40px;
    text-align: center;
}

.box {
    background-color: white;
    margin: 20px auto;
    border-radius: 12px;
    padding: 30px;
    width: 80%;
    max-width: 900px;
    opacity: 0;
    transform: scale(0.5);
}

/* Show animation for boxes */
.box.show {
    animation: popIn 0.6s cubic-bezier(0.68, -0.55, 0.27, 1.55) forwards;
}

/* ===== Menu Items ===== */
.menu-item {
    margin: 12px 0;
    font-size: 18px;
    opacity: 0;
    transform: translateX(-50px) rotate(-5deg);
    animation: slideBounce 0.6s forwards;
}

.menu-item:nth-child(1){animation-delay:.1s}
.menu-item:nth-child(2){animation-delay:.2s}
.menu-item:nth-child(3){animation-delay:.3s}
.menu-item:nth-child(4){animation-delay:.4s}
.menu-item:nth-child(5){animation-delay:.5s}
.menu-item:nth-child(6){animation-delay:.6s}
.menu-item:nth-child(7){animation-delay:.7s}
.menu-item:nth-child(8){animation-delay:.8s}

.menu-item:hover {
    transform: scale(1.15) skewX(5deg);
    color: #ff7043;
    transition: all 0.3s ease;
}

/* ===== Buttons ===== */
button {
    background-color: #6f4e37;
    color: white;
    border: none;
    padding: 12px 22px;
    cursor: pointer;
    border-radius: 30px;
    margin-top: 18px;
    font-size: 15px;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

button:hover {
    animation: buttonPop 0.4s forwards;
}

/* Ripple effect */
button span.ripple {
    position: absolute;
    border-radius: 50%;
    transform: scale(0);
    animation: ripple 0.6s linear;
    background: rgba(255,255,255,0.7);
}

/* Messages pop */
#offer, #message {
    margin-top: 15px;
    font-weight: bold;
    color: green;
    animation: pop 0.4s ease forwards;
}

/* Iframe hover pop */
iframe {
    width: 100%;
    height: 350px;
    border-radius: 10px;
    margin-top: 20px;
    transition: transform 0.4s ease, box-shadow 0.4s ease;
}

iframe:hover {
    transform: scale(1.06) rotate(-0.5deg);
    box-shadow: 0 15px 30px rgba(0,0,0,0.2);
}

/* ===== Footer ===== */
footer {
    background-color: #4e342e;
    color: white;
    text-align: center;
    padding: 15px;
    margin-top: 30px;
}

/* ===== Keyframes ===== */
@keyframes fadeDown {
    from {opacity:0; transform:translateY(-30px);}
    to {opacity:1; transform:translateY(0);}
}

@keyframes popIn {
    0% {opacity: 0; transform: scale(0.5);}
    60% {opacity: 1; transform: scale(1.2);}
    100% {opacity: 1; transform: scale(1);}
}

@keyframes slideBounce {
    0% {opacity: 0; transform: translateX(-50px) rotate(-5deg);}
    60% {opacity: 1; transform: translateX(10px) rotate(3deg);}
    100% {opacity: 1; transform: translateX(0) rotate(0);}
}

@keyframes buttonPop {
    0% {transform: scale(1);}
    50% {transform: scale(1.2);}
    100% {transform: scale(1.1);}
}

@keyframes ripple {
    to {transform: scale(4); opacity: 0;}
}

@keyframes pop {
    0% {transform: scale(0.8);}
    70% {transform: scale(1.15);}
    100% {transform: scale(1);}
}
</style>
</head>

<body>

<header>
    <h1>Hot Cup Cafe</h1>
    <p>Warm Drinks • Happy Moments • Swoyambhu, Kathmandu</p>
</header>

<nav>
    <a href="#about">About</a>
    <a href="#menu">Menu</a>
    <a href="#owners">Owners</a>
    <a href="#contact">Contact</a>
    <a href="#map">Map</a>
</nav>

<section id="about">
<div class="box">
    <h2>About Hot Cup Cafe</h2>
    <p>Affordable tea, coffee and snacks in the near heart of Swoyambhu.
        <br> We focus on giving you a tasteful and enjoyable meals/foods that can be enjoyed by you, your friends and your family as well!
        <br> But sadly, due to Hot Cup Cafe being a small family buisness, we do not support onlmine deliveries and orders. Sorry and Thank you!
    </p>
</div>
</section>

<section id="menu">
<div class="box">
    <h2>Our Menu</h2>
    <div class="menu-item">🍵 Milk Tea – Rs. 25</div>
    <div class="menu-item">🍵 Black Tea – Rs. 20</div>
    <div class="menu-item">☕ Milk Coffee – Rs. 50</div>
    <div class="menu-item">☕ Black Coffee – Rs. 35</div>
    <div class="menu-item">🥜 Chana – Rs. 20 per bowl</div>
    <div class="menu-item">🍳 Omelet – Rs. 25 per egg</div>
    <div class="menu-item">🍜 Chau Chau – Rs. 30</div>
    <div class="menu-item">🍩 Donut – Rs. 20</div>

    <button onclick="showOffer(event)">Today's Offer</button>
    <p id="offer"></p>
</div>
</section>

<section id="owners">
<div class="box">
    <h2>Owners</h2>
    <p><strong>Rup Chandra Maharjan</strong> & <strong>Niruta Maharjan</strong>
    <br>
    A small family business that wants to make your little moment happy and enjoyable by our food. 
Come with friends, family or even alone. We will make your moment tasteful!
</p>
</div>
</section>

<section id="contact">
<div class="box">
    <h2>Contact Us</h2>
    <p>📍 Swoyambhu, Kathmandu</p>
    <p>📞 WhatsApp: <strong>+977 9860089560</strong></p>
    <button onclick="sendWhatsApp(event)">Message Us on WhatsApp</button>
    <p id="message"></p>
</div>
</section>

<section id="map">
<div class="box">
    <h2>How to Reach Us</h2>
    <iframe src="https://www.google.com/maps?q=Swoyambhu%20Kathmandu&output=embed"></iframe>
</div>
</section>

<footer>
    <p>© 2025 Hot Cup Cafe | Swoyambhu, Kathmandu</p>
</footer>

<script>
/* Scroll-triggered animations for boxes */
const boxes = document.querySelectorAll(".box");
window.addEventListener("scroll", () => {
    boxes.forEach((box, i) => {
        if (box.getBoundingClientRect().top < window.innerHeight - 100) {
            if (!box.classList.contains("show")) {
                box.classList.add("show");
            }
        }
    });
});

/* Ripple effect */
document.querySelectorAll("button").forEach(btn => {
    btn.addEventListener("click", function(e) {
        const ripple = document.createElement("span");
        ripple.className = "ripple";
        ripple.style.left = e.offsetX + "px";
        ripple.style.top = e.offsetY + "px";
        this.appendChild(ripple);
        setTimeout(() => ripple.remove(), 600);
    });
});

function showOffer() {
    document.getElementById("offer").innerText =
        "☕ Buy 4 Milk Tea and get 1 Black Tea FREE!";
}

function sendWhatsApp() {
    const num = "9779860089560";
    const msg = "Hello Hot Cup Cafe, I would like to know more.";
    window.open("https://wa.me/" + num + "?text=" + encodeURIComponent(msg), "_blank");
    document.getElementById("message").innerText = "Opening WhatsApp…";
}
</script>

</body>
</html>
