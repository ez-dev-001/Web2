<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сайт за зразком</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #222;
            color: white;
            text-align: center;
            margin: 0;
            padding: 0;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 50px;
        }

        .main-block {
            background: url('https://source.unsplash.com/400x300/?abstract') no-repeat center center / cover;
            padding: 20px;
            width: 300px;
            border-radius: 10px;
            text-align: center;
        }

        .main-block img {
            width: 100%;
            border: 5px solid white;
        }

        .menu {
            display: flex;
            justify-content: space-around;
            margin: 10px 0;
        }

        .menu a {
            text-decoration: none;
            color: white;
            padding: 5px 10px;
            border-radius: 5px;
        }

        .menu a:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }

        .side-block {
            background: #333;
            padding: 15px;
            width: 200px;
            border-radius: 10px;
            text-align: center;
        }

        .side-block img {
            width: 100%;
            border: 5px solid white;
        }

        .side-block p {
            margin-top: 10px;
        }

        .side-block:hover p {
            color: yellow;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Центральний блок -->
        <div class="main-block">
            <img src="https://source.unsplash.com/300x200/?fox" alt="activeden">
            <div class="menu">
                <a href="#">Про нас</a>
                <a href="#">Маркетплейс</a>
                <a href="#">Мережа Tuts+</a>
            </div>
            <p>Це платформа для продажу цифрового контенту. Тут можна знайти графіку, звуки, відео та багато іншого.</p>
        </div>

        <!-- Бічні блоки -->
        <div class="side-block">
            <img src="https://source.unsplash.com/200x150/?snake" alt="audiojungle">
            <p>Аудіофайли для ваших проєктів.</p>
        </div>

        <div class="side-block">
            <img src="https://source.unsplash.com/200x150/?turtle" alt="photodune">
            <p>Стокові фотографії на будь-який смак.</p>
        </div>
    </div>
</body>
</html>
