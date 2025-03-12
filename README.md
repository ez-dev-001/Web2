<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Макет Envato (Точний, 3 Таблиці)</title>
    <style>
        body {
            font-family: sans-serif;
            background-image: url('bokeh-background.jpg'); /* Замініть на ВАШЕ зображення боке */
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
            padding-top: 20px;
            color: #333; /* Темний колір тексту для кращої читабельності */
        }

        .container {
            max-width: 1000px;
            width: 90%;
            display: flex;
            flex-direction: column; /* Stack tables vertically */
            gap: 20px;
        }

        /* Основний контейнер для таблиць */
        .table-container {
            display: flex;
            flex-wrap: wrap; /* Дозволяє елементам переноситися */
            gap: 20px;
            justify-content: space-between; /* Розподіляє простір */
           border: 1px solid #ccc;
            border-radius: 8px;
            padding: 15px;
            background-color: white;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);

        }

        /* Контейнер для верхнього ряду (модулі з картинками) */
        .top-row {
            display: flex;
            gap: 10px;
            width: 48%;  /*  щоб було місце для модулів часу */
            flex-wrap: wrap; /* Allow items to wrap*/
             justify-content: space-between;
        }

        /* Модулі з картинками */
        .image-module {
            border-radius: 8px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
            font-size: 1.2em;
            padding: 15px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            flex: 1;
            min-width: 0; /* Дозволяє стискатися */
        }

        .image-module img {
            max-width: 70%;
            height: auto;
            margin-bottom: 8px;
        }

         .image-module span{
          font-size:0.75em;
        }

        .audiojungle { background-color: #4CAF50; }
        .activeden { background-color: #FFA500; }
        .photodune { background-color: #2196F3; }

        /* Модулі часу */
        .time-modules {
            display: grid; /* Використовуємо Grid Layout */
            grid-template-columns: repeat(2, 1fr); /* Дві колонки */
            grid-template-rows: repeat(3, auto);    /* Три рядки */
            gap: 10px;
            width: 48%;  /* Займають половину ширини */
        }

        .time-module {
            background-color: rgba(220, 220, 220, 0.8);
            border-radius: 4px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 5px;
            text-align: center;
        }

        .time-module img {
            width: 30px;
            height: 30px;
            margin-bottom: 3px;
        }
          .time-module span{
             font-size: 0.7em; /*Smaller font size.*/
         }

        /* Інфо-секція (тепер окрема "таблиця") */
        .info-section {
           width: 98%; /* Full width, less padding */
            background-color: white;
            border-radius: 8px;
            padding: 15px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            box-sizing: border-box; /* Include padding in width */
            font-size: 0.8em;
            border: 1px solid #ccc;
        }

        /* Вкладки (без JS) */
        .tabs {
            display: flex;
            margin-bottom: 10px;
        }

        .tab {
            padding: 8px 12px;
            border: 1px solid #ddd;
            border-bottom: none;
            border-radius: 5px 5px 0 0;
            background-color: #eee;
            margin-right: 4px;
            font-size: 0.9em;
            text-decoration: none;
            color: #333;
        }

        .tab-content {
            border: 1px solid #ddd;
            padding: 10px;
            border-radius: 0 5px 5px 5px;
            display: none; /* Hide all by default */
        }

        .tab-content:target {
            display: block;
        }

          /* Стилізуємо першу вкладку як активну за замовчуванням */
        #about {
            display: block;
        }
        .tabs a:first-child {
           background-color: white;
            border-bottom: 1px solid white;
        }

        .logo-section {
            display: flex;
            align-items: center;
            margin-bottom: 8px;
        }

        .logo-section img {
            max-height: 40px;
            margin-right: 8px;
        }

        .item-images {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
        }

        .item-images img {
            max-width: 70px;
            height: auto;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        .visit-link {
            margin-top: 10px;
            font-size: 1em;
            display: block;
            text-align: center;
        }

         /* Адаптивність */
         @media (max-width: 768px) {
            .top-row,
            .time-modules {
                width: 100%; /* Full width on smaller screens */
            }
              .time-modules{
                 grid-template-columns: repeat(3, 1fr); /* 3 columns on mobile */
                 grid-template-rows: repeat(2, auto); /*Two rows.*/
            }
              .image-module{
                width: 48%;
            }
        }
         @media (max-width: 480px) {

              .image-module{
                width: 100%;
            }
              .time-modules{
                 grid-template-columns: repeat(2, 1fr); /* 2 columns on mobile */
                 grid-template-rows: repeat(3, auto);
            }
        }

    </style>
</head>
<body>

<div class="container">

    <!-- Перша "таблиця" -->
    <div class="table-container">
        <div class="top-row">
            <div class="image-module audiojungle">
                <img src="snake.png" alt="Audiojungle Змія">
                <span>audiojungle</span>
            </div>
            <div class="image-module activeden">
                <img src="fox.png" alt="Activeden Лисиця">
                <span>activeden</span>
            </div>
             <div class="image-module photodune">
                <img src="beetle.png" alt="Photodune Жук">
               <span>photodune</span>
            </div>
        </div>
        <div class="time-modules">
            <div class="time-module">
                 <img src="activeden-icon.png" alt="activeden">
                <span>(7:30 до 12:30)</span>
                <span>Ранок</span>
            </div>
            <div class="time-module">
                <img src="audiojungle-icon.png" alt="audiojungle">
                 <span>(12:30 до 17:30)</span>
                 <span>День</span>
            </div>
            <div class="time-module">
                <img src="photodune-icon.png" alt="photodune">
                <span>(17:30 до 00:30)</span>
                <span>Вечір</span>

            </div>
            <div class="time-module">
                <img src="snake.png" alt="Змія">
                <span>(00:30 до 7:30)</span>
                <span>Ніч</span>
            </div>
            <div class="time-module">
                <img src="placeholder-icon.png" alt="Заглушка">
                 <span>Час</span>
                 <span>Мітка</span>
            </div>
              <div class="time-module">
                 <img src="placeholder-icon.png" alt="Заглушка">
                 <span>Час</span>
                 <span>Мітка</span>
            </div>

        </div>
    </div>

    <!-- Друга "таблиця" (немає на скріншоті, але ви сказали "3 таблиці") -->
     <!-- Порожній контейнер. Видаліть, якщо не потрібно -->

    <!-- Третя "таблиця" (інфо-секція) -->
     <div class="info-section">
            <div class="tabs">
                <a href="#about" class="tab">Про Envato</a>
                <a href="#marketplaces" class="tab">Магазини</a>
                <a href="#tuts" class="tab">Мережа Tuts+</a>
            </div>

            <div class="tab-content" id="about">
                <div class="logo-section">
                    <img src="envato-logo.png" alt="Логотип Envato">
                </div>
                <p>Envato – це стартап...</p>
                <div class="item-images">
                    <img src="item1.png" alt="Елемент 1">
                    <img src="item2.png" alt="Елемент 2">
                    <img src="item3.png" alt="Елемент 3">
                    <img src="item4.png" alt="Елемент 4">
                    <img src="item5.png" alt="Елемент 5">
                </div>
                <a class ="visit-link" href="https://envato.com">Відвідайте веб-сайт Envato</a>
            </div>

            <div class="tab-content" id="marketplaces">
                Вміст магазинів тут.
            </div>

            <div class="tab-content" id="tuts">
                Вміст мережі Tuts+ тут.
            </div>
        </div>

</div>

</body>
</html>
