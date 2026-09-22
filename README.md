# Andamshop.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Totally Normal Store</title>

    <style>

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: Arial, sans-serif;
            background: #f4f4f4;
            color: #222;
        }

        header {
            background: #111;
            color: white;
            padding: 20px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        header h1 {
            font-size: 24px;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin-left: 25px;
            cursor: pointer;
        }

        .hero {
            text-align: center;
            padding: 80px 20px;
            background: white;
        }

        .hero h2 {
            font-size: 48px;
            margin-bottom: 15px;
        }

        .hero p {
            color: #666;
            font-size: 18px;
        }

        .products {
            padding: 60px 8%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
        }

        .product {
            background: white;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            text-align: center;
        }

        .product-image {
            height: 180px;
            background: #ddd;
            border-radius: 8px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #777;
        }

        .product h3 {
            margin-bottom: 10px;
        }

        .price {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 20px;
        }

        button {
            border: none;
            background: #111;
            color: white;
            padding: 12px 25px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 15px;
        }

        button:hover {
            background: #333;
        }

        footer {
            background: #111;
            color: white;
            text-align: center;
            padding: 30px;
        }

        /* POPUP */

        .popup-background {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.65);
            align-items: center;
            justify-content: center;
            z-index: 1000;
        }

        .popup {
            background: white;
            width: 90%;
            max-width: 450px;
            padding: 40px;
            border-radius: 15px;
            text-align: center;
            animation: popupAnimation 0.2s ease;
        }

        .popup h2 {
            margin-bottom: 15px;
        }

        .popup p {
            color: #555;
            line-height: 1.6;
            margin-bottom: 25px;
        }

        @keyframes popupAnimation {
            from {
                transform: scale(0.8);
                opacity: 0;
            }

            to {
                transform: scale(1);
                opacity: 1;
            }
        }

    </style>
</head>

<body>

<header>

    <h1>Totally Normal Store</h1>

    <nav>
        <a onclick="showMessage('home')">Home</a>
        <a onclick="showMessage('products')">Products</a>
        <a onclick="showMessage('about')">About</a>
        <a onclick="showMessage('contact')">Contact</a>
    </nav>

</header>


<section class="hero">

    <h2>Welcome.</h2>

    <p>Everything you need. Probably.</p>

</section>


<section class="products">

    <div class="product">

        <div class="product-image">
            PRODUCT IMAGE
        </div>

        <h3>Mysterious Object</h3>

        <div class="price">€29.99</div>

        <button onclick="showMessage('buy')">
            BUY NOW
        </button>

    </div>


    <div class="product">

        <div class="product-image">
            PRODUCT IMAGE
        </div>

        <h3>Definitely Real Product</h3>

        <div class="price">€49.99</div>

        <button onclick="showMessage('buy')">
            BUY NOW
        </button>

    </div>


    <div class="product">

        <div class="product-image">
            PRODUCT IMAGE
        </div>

        <h3>Suspiciously Cheap Thing</h3>

        <div class="price">€9.99</div>

        <button onclick="showMessage('buy')">
            BUY NOW
        </button>

    </div>

</section>


<footer>

    © 2026 Totally Normal Store

</footer>


<!-- POPUP -->

<div class="popup-background" id="popup">

    <div class="popup">

        <h2 id="popup-title">
            SYSTEM MESSAGE
        </h2>

        <p id="popup-text">
            Something happened.
        </p>

        <button onclick="closePopup()">
            OK
        </button>

    </div>

</div>


<script>

    const messages = {

        home:
        "چطوری باور کردی من همچین کار غیرانسانی‌ای می‌کنم؟ 😂",

        products:
        "محصولات اینجا کاملاً واقعی هستند. احتمالاً.",

        about:
        "واقعاً می‌خوای درباره من بدونی؟ انتخاب عجیبیه.",

        contact:
        "می‌خواستی با من تماس بگیری؟ چرا؟",

        buy:
        "چطوری باور کردی من همچین کار غیرانسانی‌ای می‌کنم؟ 😂"

    };


    function showMessage(type) {

        document.getElementById("popup-text").innerText =
            messages[type];

        document.getElementById("popup").style.display =
            "flex";
    }


    function closePopup() {

        document.getElementById("popup").style.display =
            "none";
    }

</script>

</body>
</html>
