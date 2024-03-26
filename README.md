<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Çanta Mağazası</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
        }

        header {
            background: #333;
            color: #fff;
            padding-top: 30px;
            min-height: 70px;
            border-bottom: #0071dc 3px solid;
        }

        header h1 {
            text-align: center;
        }

        nav {
            float: left;
            width: 30%;
            text-align: center;
            margin-top: 20px;
        }

        nav ul {
            list-style-type: none;
            padding: 0;
        }

        nav ul li {
            display: inline-block;
            margin-right: 20px;
        }

        nav ul li a {
            color: #fff;
            text-decoration: none;
            font-size: 18px;
        }

        .product-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            margin-top: 20px;
        }

        .product-card {
            width: 300px;
            background: #fff;
            margin: 10px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .product-card img {
            width: 100%;
            border-top-left-radius: 5px;
            border-top-right-radius: 5px;
        }

        .product-info {
            padding: 10px;
        }

        .product-info h3 {
            margin: 5px 0;
        }

        .product-info p {
            font-size: 14px;
        }

        footer {
            background: #333;
            color: #fff;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>Çanta Mağazası</h1>
            <nav>
                <ul>
                    <li><a href="#">Kadın Çantaları</a></li>
                    <li><a href="#">Erkek Çantaları</a></li>
                    <li><a href="#">Çocuk Çantaları</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <div class="container product-container">
        <div class="product-card">
            <img src="bag1.jpg" alt="Çanta 1">
            <div class="product-info">
                <h3>Çanta 1</h3>
                <p>Fiyat: $50</p>
                <button>Sepete Ekle</button>
            </div>
        </div>
        <div class="product-card">
            <img src="bag2.jpg" alt="Çanta 2">
            <div class="product-info">
                <h3>Çanta 2</h3>
                <p>Fiyat: $40</p>
                <button>Sepete Ekle</button>
            </div>
        </div>
        <!-- Diğer çanta kartları buraya eklenebilir -->
    </div>

    <footer>
        <p>Çanta Mağazası &copy; 2024</p>
    </footer>
</body>
</html>
