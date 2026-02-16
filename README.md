<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>La Cave des Millésimes</title>


<style>

/* ===== STYLE GENERAL ===== */

body{
    margin:0;
    font-family:'Montserrat', sans-serif;
    background:#f4efe9;
    color:#333;
}

h1,h2,h3{
    font-family:'Playfair Display', serif;
}

/* ===== HEADER ===== */

header{
    background:#4b0f1b;
    color:white;
    padding:20px 60px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

/* ✅ AJOUT : bloc logo + texte */
.brand{
    display:flex;
    align-items:center;
    gap:12px; /* espace entre logo et texte */
}

/* ✅ AJOUT : style du logo */
.brand-logo{
    height:42px; /* ajuste si besoin */
    width:auto;
    display:block;
    object-fit:contain;
}

/* ✅ AJOUT : retire la marge par défaut du h1 pour un alignement parfait */
header h1{
    margin:0;
}

nav a{
    color:white;
    text-decoration:none;
    margin-left:25px;
    font-weight:500;
}

nav a:hover{
    opacity:0.7;
}

/* ===== PANIER ICON ===== */

.cart-icon{
    position:fixed;
    top:20px;
    right:30px;
    background:#4b0f1b;
    color:white;
    padding:12px 18px;
    border-radius:30px;
    cursor:pointer;
    box-shadow:0 4px 10px rgba(0,0,0,0.2);
}

/* ===== SECTIONS ===== */

.section{
    display:none;
    padding:60px 10%;
}

.active{
    display:block;
}

/* ===== PRODUITS ===== */

.products{
    display:flex;
    flex-wrap:wrap;
    gap:30px;
}

.product{
    background:white;
    width:260px;
    border-radius:12px;
    box-shadow:0 5px 15px rgba(0,0,0,0.1);
    overflow:hidden;
    text-align:center;
}

.product img{
    width:100%;
    height:220px;
    object-fit:cover;
}

.product h3{
    margin:10px 0;
}

.price{
    color:#4b0f1b;
    font-weight:600;
    margin-bottom:10px;
}

.btn{
    background:#4b0f1b;
    color:white;
    border:none;
    padding:10px 18px;
    border-radius:6px;
    cursor:pointer;
    margin-bottom:15px;
}

.btn:hover{
    background:#6a1a28;
}

/* ===== PANIER ===== */

.cart-box{
    background:white;
    padding:20px;
    margin-top:40px;
    border-radius:10px;
    box-shadow:0 5px 15px rgba(0,0,0,0.1);
}

/* ===== GALERIE ===== */

.gallery{
    display:flex;
    gap:30px;
    flex-wrap:wrap;
}

.gallery img{
    width:260px;
    height:220px;
    object-fit:cover;
    border-radius:12px;
    box-shadow:0 5px 15px rgba(0,0,0,0.1);
}

/* ===== INPUT ===== */

input{
    padding:10px;
    margin:5px;
    border-radius:6px;
    border:1px solid #ccc;
}

/* ===== FOOTER ===== */

footer{
    background:#4b0f1b;
    color:white;
    text-align:center;
    padding:30px;
    margin-top:60px;
}

</style>
</head>

<body>

<header>
    <!-- ✅ MODIF : logo + Millésimes -->
    <div class="brand">
        <img class="brand-logo" src="t1.png" alt="Logo Millésimes">
        <h1>Millésimes</h1>
    </div>

    <nav>
        <a href="#" onclick="showSection('home')">Accueil</a>
        <a href="#" onclick="showSection('boutique')">Boutique</a>
        <a href="#" onclick="showSection('galerie')">Galerie</a>
        <a href="#" onclick="showSection('histoire')">Histoire</a>
        <a href="#" onclick="showSection('client')">Espace client</a>
    </nav>
</header>

<div class="cart-icon" onclick="showSection('boutique')">
🛒 <span id="cart-count">0</span>
</div>

<!-- ACCUEIL -->

<section id="home" class="section active">
    <h2>Bienvenue dans notre cave d'exception</h2>
    <p>Découvrez une sélection premium de vins, champagnes et spiritueux.</p>
</section>

<!-- BOUTIQUE -->

<section id="boutique" class="section">

<h2>Boutique en ligne</h2>

<div class="products">

<div class="product">
<img src="https://images.unsplash.com/photo-1510812431401-41d2bd2722f3">
<h3>Bordeaux Grand Cru</h3>
<p class="price">29.90 €</p>
<button class="btn" onclick="addToCart(29.90)">Ajouter</button>
</div>

<div class="product">
<img src="https://images.unsplash.com/photo-1605276373954-0c4a0dac5b12">
<h3>Champagne Prestige</h3>
<p class="price">49.90 €</p>
<button class="btn" onclick="addToCart(49.90)">Ajouter</button>
</div>

<div class="product">
<img src="https://images.unsplash.com/photo-1514361892635-cebb82b2c58b">
<h3>Whisky Single Malt</h3>
<p class="price">64.90 €</p>
<button class="btn" onclick="addToCart(64.90)">Ajouter</button>
</div>

<div class="product">
<img src="https://images.unsplash.com/photo-1544025162-d76694265947">
<h3>Plateau Fromages & Charcuterie</h3>
<p class="price">39.90 €</p>
<button class="btn" onclick="addToCart(39.90)">Ajouter</button>
</div>

</div>

<div class="cart-box">
<h3>Votre panier</h3>
<p>Total : <span id="total">0</span> €</p>

<h4>Paiement sécurisé</h4>

<input type="text" placeholder="Nom sur la carte">
<input type="text" placeholder="Numéro de carte">
<input type="text" placeholder="MM/AA">
<input type="text" placeholder="CVC">

<br><br>

<button class="btn" onclick="pay()">Payer maintenant</button>

</div>

</section>

<!-- GALERIE -->

<section id="galerie" class="section">
<h2>Notre Cave</h2>

<div class="gallery">
<img src="https://images.unsplash.com/photo-1556742049-0cfed4f6a45d">
<img src="https://images.unsplash.com/photo-1580910051074-3eb694886505">
</div>

</section>

<!-- HISTOIRE -->

<section id="histoire" class="section">
<h2>Notre Histoire</h2>

<p>
Depuis plusieurs années, la Cave des Millésimes sélectionne des vins d’exception
auprès de producteurs passionnés afin de proposer une expérience unique.
</p>

</section>

<!-- ESPACE CLIENT -->

<section id="client" class="section">

<h2>Carte de fidélité</h2>

<p>Total cumulé : <span id="loyalty">0</span> €</p>
<p>5% de remise tous les 50€ d’achats cumulés.</p>

</section>

<footer>
© 2026 La Cave des Millésimes
</footer>

<script>

let total = 0;
let loyalty = 0;
let count = 0;

function showSection(id){

document.querySelectorAll(".section").forEach(sec=>{
sec.classList.remove("active");
});

document.getElementById(id).classList.add("active");

}

function addToCart(price){

total += price;
loyalty += price;
count++;

document.getElementById("total").textContent = total.toFixed(2);
document.getElementById("loyalty").textContent = loyalty.toFixed(2);
document.getElementById("cart-count").textContent = count;

}

function pay(){

alert("Paiement validé ! Merci pour votre commande.");

total = 0;
count = 0;

document.getElementById("total").textContent = 0;
document.getElementById("cart-count").textContent = 0;

}

</script>

</body>
</html>
