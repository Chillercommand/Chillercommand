<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Schuh-Shop</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 1em 0;
            text-align: center;
        }

        header h1 {
            margin: 0;
        }

        nav ul {
            list-style-type: none;
        
            padding: 0;
        }

        nav ul li {
            display: inline;
            margin: 0 15px;
        }

        nav ul li a {
            color: #fff;
            text-decoration: none;
        }

        section {
            padding: 2em;
        }

        .product {
            background-color: #fff;
            padding: 1em;
            margin: 1em 0;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .product img {
            width: 200px;
            height: auto;
        }

        .product h3 {
            margin: 0.5em 0;
        }

        footer {
            text-align: center;
            padding: 1em 0;
            background-color: #333;
            color: #fff;
            margin-top: 2em;
        }
    </style>
</head>
<body>
    <header>
        <h1>Schuh-Shop</h1>
        <nav>
            <ul>
                <li><a href="#home">Startseite</a></li>
                <li><a href="#products">Produkte</a></li>
                <li><a href="#contact">Kontakt</a></li>
            </ul>
        </nav>
    </header>

    <section id="home">
        <h2>Willkommen in unserem Schuh-Shop!</h2>
        <p>Hier finden Sie die neuesten Trends in der Schuhmode.</p>
    </section>

    <section id="products">
        <h2>Unsere Produkte</h2>
        <div class="product" id="product1">
            <img src="shoe1.jpg" alt="Schuh 1">
            <h3>Sportschuh</h3>
            <p>Preis: 49,99€</p>
            <button onclick="addToCart('Sportschuh', 49.99)">In den Warenkorb</button>
        </div>
        <div class="product" id="product2">
            <img src="shoe2.jpg" alt="Schuh 2">
            <h3>Eleganter Schuh</h3>
            <p>Preis: 89,99€</p>
            <button onclick="addToCart('Eleganter Schuh', 89.99)">In den Warenkorb</button>
        </div>
        <!-- Weitere Produkte können hier hinzugefügt werden -->
    </section>

    <section id="cart">
        <h2>Warenkorb</h2>
        <ul id="cartItems"></ul>
        <p>Gesamt: <span id="total">0,00</span>€</p>
    </section>

    <footer>
        <p>&copy; 2024 Schuh-Shop. Alle Rechte vorbehalten.</p>
    </footer>

    <script>
        const cartItems = [];
        const cartItemsElement = document.getElementById('cartItems');
        const totalElement = document.getElementById('total');

        function addToCart(productName, productPrice) {
            cartItems.push({ name: productName, price: productPrice });
            updateCart();
        }

        function updateCart() {
            cartItemsElement.innerHTML = '';
            let total = 0;
            cartItems.forEach(item => {
                const li = document.createElement('li');
                li.textContent = `${item.name} - ${item.price.toFixed(2)}€`;
                cartItemsElement.appendChild(li);
                total += item.price;
            });
            totalElement.textContent = total.toFixed(2);
        }
    </script>
</body>
</html>

