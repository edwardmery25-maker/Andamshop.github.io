<!DOCTYPE html>
<html lang="fa">
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
            background-color: #f3ead8;
            color: #172a46;
        }

        /* HEADER */

        header {
            background-color: #172a46;
            color: #f3ead8;
            padding: 18px 6%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo img {
            height: 55px;
            width: auto;
            display: block;
        }

        nav {
            display: flex;
            align-items: center;
            gap: 28px;
        }

        nav a {
            color: #f3ead8;
            text-decoration: none;
            font-size: 15px;
            cursor: pointer;
        }

        nav a:hover {
            opacity: 0.7;
        }

        /* SEARCH */

        .search-btn {
            background: none;
            border: none;
            color: #f3ead8;
            font-size: 25px;
            cursor: pointer;
            padding: 0;
        }

        .search-btn:hover {
            opacity: 0.7;
        }

        /* HERO */

        .hero {
            text-align: center;
            padding: 90px 20px 70px;
            background-color: #e8dcc4;
        }

        .hero h1 {
            font-size: 52px;
            margin-bottom: 15px;
            color: #172a46;
        }

        .hero p {
            font-size: 18px;
            color: #394b63;
        }

        /* PRODUCTS */

        .products-section {
            padding: 70px 6%;
        }

        .section-title {
            text-align: center;
            margin-bottom: 45px;
        }

        .section-title h2 {
            font-size: 34px;
            margin-bottom: 10px;
        }

        .section-title p {
            color: #5c6470;
        }

        .products {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 28px;
        }

        .product {
            background-color: #fffaf0;
            border: 1px solid #d6c9ae;
            border-radius: 12px;
            overflow: hidden;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .product:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(23, 42, 70, 0.12);
        }

        .product-image {
            width: 100%;
            height: 230px;
            object-fit: cover;
            display: block;
            background-color: #ddd2bb;
        }

        .product-info {
            padding: 20px;
        }

        .product-info h3 {
            font-size: 19px;
            margin-bottom: 10px;
        }

        .product-info p {
            color: #69717c;
            font-size: 14px;
            margin-bottom: 15px;
        }

        .price {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .buy-btn {
            width: 100%;
            padding: 12px;
            background-color: #172a46;
            color: #f3ead8;
            border: none;
            border-radius: 7px;
            cursor: pointer;
            font-size: 15px;
        }

        .buy-btn:hover {
            background-color: #263e60;
        }

        /* SOLD OUT */

        .sold-out {
            background-color: #9a9a94;
            cursor: not-allowed;
        }

        .sold-out:hover {
            background-color: #9a9a94;
        }

        .sold-label {
            display: inline-block;
            background-color: #172a46;
            color: #f3ead8;
            padding: 5px 9px;
            border-radius: 5px;
            font-size: 11px;
            margin-bottom: 12px;
        }

        /* POPUP */

        .popup-overlay {
            display: none;
            position: fixed;
            inset: 0;
            background-color: rgba(10, 20, 35, 0.65);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .popup {
            background-color: #fffaf0;
            color: #172a46;
            width: 100%;
            max-width: 480px;
            padding: 35px;
            border-radius: 14px;
            text-align: center;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }

        .popup p {
            font-size: 18px;
            line-height: 1.8;
            margin-bottom: 25px;
        }

        .close-btn {
            background-color: #172a46;
            color: #f3ead8;
            border: none;
            padding: 11px 30px;
            border-radius: 7px;
            cursor: pointer;
            font-size: 15px;
        }

        /* FOOTER */

        footer {
            background-color: #172a46;
            color: #f3ead8;
            text-align: center;
            padding: 30px 20px;
            margin-top: 30px;
        }

        /* RESPONSIVE */

        @media (max-width: 1000px) {
            .products {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 650px) {
            header {
                padding: 15px 20px;
            }

            .logo img {
                height: 45px;
            }

            nav {
                gap: 14px;
            }

            nav a {
                display: none;
            }

            .hero {
                padding: 65px 20px;
            }

            .hero h1 {
                font-size: 38px;
            }

            .products {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>

<body>

    <!-- HEADER -->

    <header>

        <a href="#" class="logo">
            <img src="logo.png" alt="Store Logo">
        </a>

        <nav>
            <a href="#" onclick="showMessage('به صفحه اصلی خوش آمدید.')">
                Home
            </a>

            <a href="#products" onclick="showMessage('چیزی برای دیدن نیست .')">
                Products
            </a>

            <a href="#" onclick="showMessage('اطلاعاتی درباره ما وجود ندارد.')">
                About
            </a>

            <a href="#" onclick="showMessage('لطفاً مزاحم نشوید.')">
                Contact
            </a>

            <!-- SEARCH ICON -->

            <button class="search-btn"
                    onclick="showMessage('🔍 توی بدن خودت دنبالش بگرد، اینجا چیزی نیست.')">
                🔍
            </button>
        </nav>

    </header>


    <!-- HERO -->

    <section class="hero">

        <h1>Welcome.</h1>

        <p>
            Everything you need. Probably.
        </p>

    </section>


    <!-- PRODUCTS -->

    <section class="products-section" id="products">

        <div class="section-title">
            <h2>Our Products</h2>
            <p>Quality products for absolutely no reason.</p>
        </div>


        <div class="products">


            <!-- PRODUCT 1 -->

            <div class="product">

                <img src="product1.jpg"
                     alt="Product 1"
                     class="product-image">

                <div class="product-info">

                    <span class="sold-label">
                        SOLD OUT
                    </span>

                    <h3>Product One</h3>

                    <p>
                        A completely normal product.
                    </p>

                    <div class="price">
                        $29.99
                    </div>

                    <button class="buy-btn sold-out"
                            onclick="showMessage('این محصول فروخته شده. حتی خودمون هم نمی‌دونیم به کی.')">
                        SOLD OUT
                    </button>

                </div>
            </div>


            <!-- PRODUCT 2 -->

            <div class="product">

                <img src="product2.jpg"
                     alt="Product 2"
                     class="product-image">

                <div class="product-info">

                    <h3>Product Two</h3>

                    <p>
                        Very useful. Probably.
                    </p>

                    <div class="price">
                        $39.99
                    </div>

                    <button class="buy-btn"
                            onclick="showMessage('به‌عنوان یه مدافع حقوق حیوانات، همچین کار غیرانسانی‌ای رو نمی‌ذارم بکنی. 🐦‍⬛‼️❌')">
                        Buy Now
                    </button>

                </div>
            </div>


            <!-- PRODUCT 3 -->

            <div class="product">

                <img src="product3.jpg"
                     alt="Product 3"
                     class="product-image">

                <div class="product-info">

                    <span class="sold-label">
                        SOLD OUT
                    </span>

                    <h3>Product Three</h3>

                    <p>
                        You missed your chance.
                    </p>

                    <div class="price">
                        $49.99
                    </div>

                    <button class="buy-btn sold-out"
                            onclick="showMessage('این یکی هم فروخته شده. واقعاً سریع خرید می‌کنید.')">
                        SOLD OUT
                    </button>

                </div>
            </div>


            <!-- PRODUCT 4 -->

            <div class="product">

                <img src="product4.jpg"
                     alt="Product 4"
                     class="product-image">

                <div class="product-info">

                    <h3>Product Four</h3>

                    <p>
                        Nobody knows what this does.
                    </p>

                    <div class="price">
                        $59.99
                    </div>

                    <button class="buy-btn"
                            onclick="showMessage('به‌عنوان یه مدافع حقوق حیوانات، همچین کار غیرانسانی‌ای رو نمی‌ذارم بکنی. 🐦‍⬛‼️❌')">
                        Buy Now
                    </button>

                </div>
            </div>


            <!-- PRODUCT 5 -->

            <div class="product">

                <img src="product5.jpg"
                     alt="Product 5"
                     class="product-image">

                <div class="product-info">

                    <h3>Product Five</h3>

                    <p>
                        Surprisingly expensive.
                    </p>

                    <div class="price">
                        $69.99
                    </div>

                    <button class="buy-btn"
                            onclick="showMessage('به‌عنوان یه مدافع حقوق حیوانات، همچین کار غیرانسانی‌ای رو نمی‌ذارم بکنی. 🐦‍⬛‼️❌')">
                        Buy Now
                    </button>

                </div>
            </div>


            <!-- PRODUCT 6 -->

            <div class="product">

                <img src="product6.jpg"
                     alt="Product 6"
                     class="product-image">

                <div class="product-info">

                    <h3>Product Six</h3>

                    <p>
                        We think it's useful.
                    </p>

                    <div class="price">
                        $79.99
                    </div>

                    <button class="buy-btn"
                            onclick="showMessage('به‌عنوان یه مدافع حقوق حیوانات، همچین کار غیرانسانی‌ای رو نمی‌ذارم بکنی. 🐦‍⬛‼️❌')">
                        Buy Now
                    </button>

                </div>
            </div>


            <!-- PRODUCT 7 -->

            <div class="product">

                <img src="product7.jpg"
                     alt="Product 7"
                     class="product-image">

                <div class="product-info">

                    <h3>Product Seven</h3>

                    <p>
                        Nobody asked for this.
                    </p>

                    <div class="price">
                        $89.99
                    </div>

                    <button class="buy-btn"
                            onclick="showMessage('به‌عنوان یه مدافع حقوق حیوانات، همچین کار غیرانسانی‌ای رو نمی‌ذارم بکنی. 🐦‍⬛‼️❌')">
                        Buy Now
                    </button>

                </div>
            </div>


            <!-- PRODUCT 8 -->

            <div class="product">

                <img src="product8.jpg"
                     alt="Product 8"
                     class="product-image">

                <div class="product-info">

                    <h3>Product Eight</h3>

                    <p>
                        The final mistake.
                    </p>

                    <div class="price">
                        $99.99
                    </div>

                    <button class="buy-btn"
                            onclick="showMessage('به‌عنوان یه مدافع حقوق حیوانات، همچین کار غیرانسانی‌ای رو نمی‌ذارم بکنی. 🐦‍⬛‼️❌')">
                        Buy Now
                    </button>

                </div>
            </div>


        </div>

    </section>


    <!-- POPUP -->

    <div class="popup-overlay" id="popup">

        <div class="popup">

            <p id="popupMessage"></p>

            <button class="close-btn"
                    onclick="closeMessage()">
                فهمیدم
            </button>

        </div>

    </div>


    <!-- FOOTER -->

    <footer>

        <p>
            © 2026 Totally Normal Store
        </p>

    </footer>


    <!-- JAVASCRIPT -->

    <script>

        function showMessage(message) {

            document.getElementById("popupMessage").innerText = message;

            document.getElementById("popup").style.display = "flex";

        }


        function closeMessage() {

            document.getElementById("popup").style.display = "none";

        }


        /* Close popup by clicking outside */

        document.getElementById("popup").addEventListener("click", function(event) {

            if (event.target === this) {

                closeMessage();

            }

        });

    </script>

</body>
</html>
