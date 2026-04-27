<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>HisGot Coffee POS</title>

<style>
body {
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(to right, #3e2723, #5d4037);
    margin: 0;
    color: #fff;
}

h1 { text-align: center; }

/* NAVBAR */
.navbar {
    background: #4e342e;
    padding: 12px;
    display: flex;
    justify-content: center;
    gap: 30px;
}

.navbar a {
    color: white;
    text-decoration: none;
    font-weight: bold;
    cursor: pointer;
}

/* PAGES */
.page { display: none; padding: 20px; }
.active { display: block; }

/* LOGIN */
.center {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80vh;
}

.card {
    background: #fff8f0;
    color: #000;
    padding: 20px;
    border-radius: 15px;
    width: 320px;
    text-align: center;
}

/* INPUT + BUTTON */
input, button {
    width: 90%;
    padding: 10px;
    margin: 10px 0;
    border-radius: 8px;
}

button {
    background: #6d4c41;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background: #4e342e;
}

/* POS */
.container { padding: 20px; }

.flex {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
}

/* MENU + RECEIPT */
.menu, .receipt {
    background: #fff8f0;
    color: #000;
    padding: 15px;
    border-radius: 15px;
    width: 340px;
}

/* SCROLL MENU */
.menu {
    max-height: 500px;
    overflow-y: auto;
}

/* ITEM */
.item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 10px 0;
}

/* IMAGE + TEXT */
.item-left {
    display: flex;
    align-items: center;
    gap: 10px;
}

.item img {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    object-fit: cover;
}

/* TOTAL */
.total {
    font-size: 20px;
    font-weight: bold;
}
</style>
</head>

<body>

<!-- NAVBAR -->
<div class="navbar">
    <a onclick="showPage('home')">HOME</a>
    <a onclick="showPage('about')">ABOUT US</a>
    <a onclick="showPage('contact')">CONTACT</a>
</div>

<!-- HOME -->
<div class="page active" id="home">

<!-- LOGIN -->
<div class="center" id="loginPage">
    <div class="card">
        <h2>☕ Login</h2>
        <input id="username" placeholder="Username">
        <input id="password" type="password" placeholder="Password">
        <button onclick="login()">Login</button>
        <p id="error" style="color:red"></p>
    </div>
</div>

<!-- POS -->
<div class="container" id="posSystem" style="display:none;">
    <h1>☕ HisGot Coffee Shop</h1>

    <div class="flex">

        <!-- MENU -->
        <div class="menu">
            <h2>Menu</h2>

            <h3>☕ Coffee</h3>

            <!-- Coffee Items -->
            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1511920170033-f8396924c348" onerror="this.src='https://via.placeholder.com/40'">
                    Americano
                </div>
                <button onclick="addItem('Americano',120)">₱120</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085" onerror="this.src='https://via.placeholder.com/40'">
                    Espresso
                </div>
                <button onclick="addItem('Espresso',100)">₱100</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1509042239860-f550ce710b93" onerror="this.src='https://via.placeholder.com/40'">
                    Latte
                </div>
                <button onclick="addItem('Latte',150)">₱150</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1507133750040-4a8f57021571" onerror="this.src='https://via.placeholder.com/40'">
                    Cappuccino
                </div>
                <button onclick="addItem('Cappuccino',140)">₱140</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1498804103079-a6351b050096" onerror="this.src='https://via.placeholder.com/40'">
                    Mocha
                </div>
                <button onclick="addItem('Mocha',170)">₱170</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1461023058943-07fcbe16d735" onerror="this.src='https://via.placeholder.com/40'">
                    Caramel Latte
                </div>
                <button onclick="addItem('Caramel Latte',160)">₱160</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1442512595331-e89e73853f31" onerror="this.src='https://via.placeholder.com/40'">
                    Hazelnut Latte
                </div>
                <button onclick="addItem('Hazelnut Latte',160)">₱160</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1464306076886-da185f6a2d06" onerror="this.src='https://via.placeholder.com/40'">
                    Flat White
                </div>
                <button onclick="addItem('Flat White',150)">₱150</button>
            </div>

            <hr>

            <h3>🍪 Snacks</h3>

            <!-- Snacks -->
            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1604908176997-431c1c7b5a72" onerror="this.src='https://via.placeholder.com/40'">
                    Chocolate Cake
                </div>
                <button onclick="addItem('Chocolate Cake',120)">₱120</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1541781774459-bb2af2f05b55" onerror="this.src='https://via.placeholder.com/40'">
                    Donut
                </div>
                <button onclick="addItem('Donut',60)">₱60</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1551024601-bec78aea704b" onerror="this.src='https://via.placeholder.com/40'">
                    Croissant
                </div>
                <button onclick="addItem('Croissant',90)">₱90</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1509440159596-0249088772ff" onerror="this.src='https://via.placeholder.com/40'">
                    Sandwich
                </div>
                <button onclick="addItem('Sandwich',110)">₱110</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1517686469429-8bdb88b9f907" onerror="this.src='https://via.placeholder.com/40'">
                    Cookies
                </div>
                <button onclick="addItem('Cookies',70)">₱70</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1512058564366-18510be2db19" onerror="this.src='https://via.placeholder.com/40'">
                    Muffin
                </div>
                <button onclick="addItem('Muffin',80)">₱80</button>
            </div>

            <div class="item">
                <div class="item-left">
                    <img src="https://images.unsplash.com/photo-1550547660-d9450f859349" onerror="this.src='https://via.placeholder.com/40'">
                    Burger
                </div>
                <button onclick="addItem('Burger',150)">₱150</button>
            </div>

        </div>

        <!-- RECEIPT -->
        <div class="receipt">
            <h2>Receipt</h2>
            <div id="receipt-items"></div>
            <div class="total">₱<span id="total">0</span></div>
            <button onclick="clearReceipt()">Clear</button>
        </div>

    </div>
</div>

</div>

<!-- ABOUT -->
<div class="page" id="about">
    <h1>About Us</h1>
    <p style="text-align:center;">We serve high-quality coffee ☕</p>
</div>

<!-- CONTACT -->
<div class="page" id="contact">
    <h1>Contact</h1>
    <p style="text-align:center;">📞 0938-3010-078</p>
</div>

<script>
function showPage(pageId) {
    document.querySelectorAll(".page").forEach(p => p.classList.remove("active"));
    document.getElementById(pageId).classList.add("active");
}

function login() {
    if(username.value === "admin" && password.value === "1234") {
        loginPage.style.display = "none";
        posSystem.style.display = "block";
    } else {
        error.innerText = "Invalid login!";
    }
}

let total = 0;

function addItem(name, price) {
    const div = document.createElement("div");
    div.textContent = name + " - ₱" + price;
    document.getElementById("receipt-items").appendChild(div);

    total += price;
    document.getElementById("total").textContent = total;
}

function clearReceipt() {
    document.getElementById("receipt-items").innerHTML = "";
    total = 0;
    document.getElementById("total").textContent = 0;
}
</script>

</body>
</html>
