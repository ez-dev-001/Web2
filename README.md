<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Статичне меню</title>
    <style>
        body {
            font-family: sans-serif; /* Загальний шрифт */
            display: flex;
            justify-content: center; /* Центруємо меню горизонтально */
            align-items: center;   /* Центруємо меню вертикально */
            min-height: 100vh;  /* Щоб меню було по центру, навіть якщо мало контенту */
            margin: 0;        /* Забираємо стандартні відступи */
            background-color: #f8f8f8; /* Світло-сірий фон */
        }

        .menu-container {
            display: flex; /* Розміщуємо блоки в ряд */
            gap: 20px;     /* Відступ між блоками */
        }

        .menu-item {
            width: 250px; /* Фіксована ширина */
            border: 2px solid #ddd; /* Рамка навколо всього блоку */
            text-align: center; /* Центруємо текст */
            position: relative; /* Для позиціонування підпису */
        }

        .menu-item img {
            width: 100%;     /* Зображення на всю ширину */
            height: 180px;   /* Фіксована висота */
            object-fit: cover; /* Обрізка зображення, щоб воно вписувалося */
            border-bottom: 2px solid #ddd; /* Рамка під зображенням */
            display: block; /* Усуває невеликий пробіл під зображенням */
        }

        .menu-item ul {
            list-style: none; /* Забираємо маркери списку */
            padding: 0;       /* Забираємо внутрішні відступи */
            margin: 0;        /* Забираємо зовнішні відступи */
        }

        .menu-item ul li {
            padding: 12px 0;  /* Відступи всередині пунктів меню */
            border-bottom: 1px solid #eee; /* Лінія між пунктами */
        }

        .menu-item ul li:last-child {
            border-bottom: none; /* Забираємо лінію у останнього пункта */
        }

        .menu-item a {
            text-decoration: none; /* Забираємо підкреслення */
            color: #444;           /* Колір тексту */
            display: block;        /* Щоб посилання займало всю ширину */
            padding: 12px;           /* Відступи навколо тексту */
        }

        /* Стилі для підпису */
        .menu-item .caption {
            position: absolute;  /* Абсолютне позиціонування */
            bottom: 0;         /* Притискаємо до низу */
            left: 0;
            width: 100%;         /* На всю ширину */
            background-color: rgba(0, 0, 0, 0.7); /* Напівпрозорий чорний фон */
            color: white;          /* Білий текст */
            padding: 8px;        /* Відступи */
            box-sizing: border-box; /* Щоб padding не збільшував ширину */
            font-size: 0.9em;      /* Трохи менший шрифт */
            opacity: 0;            /* Спочатку прихований */
            transition: opacity 0.3s ease; /* Плавна поява */
        }

        .menu-item:hover .caption {
            opacity: 1;            /* Показуємо підпис при наведенні */
        }

        /* Стилі для центрального блоку (лисиця) */
        .menu-item.fox ul li:hover {
            background-color: #f5e1a9; /* Світло-жовтий фон при наведенні */
        }

        .menu-item.fox ul li:hover a {
            color: #222;
        }

        /* Стилі для інших блоків */
        .menu-item:not(.fox) a:hover {
            color: #c75f3a;  /* Зміна кольору тексту при наведенні */
        }
    </style>
</head>
<body>

<div class="menu-container">
    <div class="menu-item">
        <img src="https://via.placeholder.com/250x180/77dd77/ffffff?text=Змія" alt="Зображення змії">
        <div class="caption">Зображення змінюється в певний час</div>
        <ul>
            <li><a href="#">Про Envato</a></li>
            <li><a href="#">Магазини</a></li>
            <li><a href="#">Мережа Tuts+</a></li>
        </ul>
    </div>

    <div class="menu-item fox">
        <img src="https://via.placeholder.com/250x180/f0b37e/ffffff?text=Лисиця" alt="Зображення лисиці">
        <div class="caption"></div>
        <ul>
            <li><a href="#">Про Envato</a></li>
            <li><a href="#">Магазини</a></li>
            <li><a href="#">Мережа Tuts+</a></li>
        </ul>
    </div>

    <div class="menu-item">
        <img src="https://via.placeholder.com/250x180/77b5d9/ffffff?text=Жук" alt="Зображення жука">
        <div class="caption">Зображення змінюється в певний час</div>
        <ul>
            <li><a href="#">Про Envato</a></li>
            <li><a href="#">Магазини</a></li>
            <li><a href="#">Мережа Tuts+</a></li>
        </ul>
    </div>
    
    <div class="menu-item">
        <img src="https://via.placeholder.com/250x180/b19cd9/ffffff?text=Годинник" alt="Зображення годинника">
        <div class="caption">(7:00 до 12:00)<br>Ранок</div>
        <ul>
            <li><a href="#">Про Envato</a></li>
            <li><a href="#">Магазини</a></li>
            <li><a href="#">Мережа Tuts+</a></li>
        </ul>
    </div>
</div>

</body>
</html>
