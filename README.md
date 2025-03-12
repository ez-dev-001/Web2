<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Макет Envato (Таблиці одна на одній)</title>
    <style>
        body {
            font-family: sans-serif;
            background-image: url('bokeh-background.jpg'); /* Замініть на ваше зображення */
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
            padding-top: 20px;
            color: #333;
        }

        .container {
            max-width: 1000px;
            width: 90%;
            /*  display: flex;  Видалено, бо тепер накладання */
            /*  flex-direction: column; Видалено */
            /*  gap: 20px; Видалено */
            position: relative; /* Для абсолютного позиціонування таблиць */
        }

        /* Контейнер для кожної "таблиці" (тепер абсолютно позиціоновані) */
        .table-container {
            border: 1px solid #ccc;
            border-radius: 8px;
            padding: 15px;
            background-color: white;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            position: absolute; /* Абсолютне позиціонування */
            top: 0;
            left: 0;
            width: 100%; /* Займають всю ширину */
            height: auto;  /*  Висота визначається контентом */
             /* Забезпечує правильне відображення z-index */
            overflow: hidden; /* Hide backgrounds when they are not active*/

        }

        /* Контейнер для фонових зображень */
        .background-images {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
             display: flex;
            z-index: 1;
        }
          .background-images > div{
              background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            width: 100%;
            height:100%;
            display: none;
        }
           /* Показуємо зображення, якщо є відповідний якір */
        .background-images > div:target{
            display: block;
        }

         /* Показуємо перше зображення за замовчуванням */
        .table-container:first-child .bg-audiojungle,
        .table-container:nth-child(2) .bg-audiojungle,
        .table-container:nth-child(3) .bg-audiojungle
        {
             display: block;
        }

        /* Класи для кожного фонового зображення */
        .bg-audiojungle { background-image: url('snake.png'); }
        .bg-activeden   { background-image: url('fox.png');   }
        .bg-photodune   { background-image: url('beetle.png');  }

        /* Навігація (змінює фон, спільна для всіх) */
        .image-nav {
            display: flex;
            gap: 10px;
            margin-bottom: 10px;
             position: relative;
            z-index: 4; /* Над усіма таблицями */
             justify-content: center; /* Center the navigation */
        }

        .image-nav a {
            display: block;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background-color: #ddd;
            border: 1px solid #ccc;
            text-indent: -9999px;
            overflow: hidden;
        }
         .image-nav a:hover,
        .image-nav a:focus{
           box-shadow: 0 0 5px rgba(0, 0, 0, 0.5);/* Add a hover effect */
        }

        /* Основний контент */
        .content {
            position: relative;
            z-index: 2;
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
             justify-content: space-between;
        }

          /* Верхній ряд (модулі з картинками) */
        .top-row {
            display: flex;
            width: 48%;  /*  щоб було місце для модулів часу */
            gap: 10px;
             flex-wrap: wrap; /* Allow items to wrap*/
             justify-content: space-between; /* Distribute space evenly */

        }

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
             flex: 1 0 calc(33.33% - 10px); /* Three items per row, with gap */
             min-width: 0; /* Allow for shrinking */

        }
        .image-module span{
            font-size: 0.75em;
        }

        .image-module img {
            max-width: 70%;
            height: auto;
            margin-bottom: 8px;
        }

        /* Модулі часу */
        .time-modules {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            grid-template-rows: repeat(3, auto);
            gap: 10px;
            width: 48%;

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
            font-size: 0.7em;
        }

        /* Інфо-секція */
        .info-section {
            width: 100%;
            background-color: white;
            border-radius: 8px;
            padding: 15px;
             box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            box-sizing: border-box;
            font-size: 0.8em;
            margin-top: 20px; /* Add space from time modules*/
        }

        /* Tabs (no JS) */
        .tabs { display: flex; margin-bottom: 10px; }
        .tab {
            padding: 8px 12px; border: 1px solid #ddd; border-bottom: none;
            border-radius: 5px 5px 0 0; background-color: #eee; margin-right: 4px;
            font-size: 0.9em; text-decoration: none; color: #333;
        }
        .tab-content {
            border: 1px solid #ddd; padding: 10px; border-radius: 0 5px 5px 5px;
            display: none;
        }
        .tab-content:target { display: block; }

          /* Стилізуємо першу вкладку як активну за замовчуванням */
        #about1 { display: block; }
        #about2, #about3 {display: none; } /* Hide by default */
        .tabs a:first-child { background-color: white; border-bottom: 1px solid white; }

        .logo-section { display: flex; align-items: center; margin-bottom: 8px; }
        .logo-section img { max-height: 40px; margin-right: 8px; }
        .item-images { display: flex; flex-wrap: wrap; gap: 5px; }
        .item-images img { max-width: 70px; height: auto; border: 1px solid #ddd; border-radius: 4px;}
        .visit-link { margin-top: 10px; font-size: 1em; display: block; text-align: center;}

           /* Адаптивність */
         @media (max-width: 768px) {
             .top-row,
            .time-modules {
                width: 100%; /* Full width on smaller screens*/
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

    <!-- Спільна навігація для всіх таблиць -->
    <div class="image-nav">
        <a href="#audiojungle">Audiojungle</a>
        <a href="#activeden">Activeden</a>
        <a href="#photodune">Photodune</a>
    </div>

    <!-- Перша "таблиця" -->
    <div class="table-container" style="z-index: 4;">
       <div class="background-images">
            <div id="audiojungle" class="bg-audiojungle"></div>
            <div id="activeden" class="bg-activeden"></div>
            <div id="photodune" class="bg-photodune"></div>
        </div>
        <div class="content">
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
             <div class="info-section">
                <!-- Tabs (no JS) -->
                <div class="tabs">
                    <a href="#about1" class="tab">Про Envato</a>
                    <a href="#marketplaces1" class="tab">Магазини</a>
                    <a href="#tuts1" class="tab">Мережа Tuts+</a>
                </div>

                <div class="tab-content" id="about1">
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
                   <a class="visit-link" href="https://envato.com">Відвідайте веб-сайт Envato</a>
                </div>

                <div class="tab-content" id="marketplaces1">
                    Вміст магазинів тут.
                </div>

                <div class="tab-content" id="tuts1">
                    Вміст мережі Tuts+ тут.
                </div>
            </div>
        </div>
    </div>

    <!-- Друга "таблиця" (з іншим z-index і контентом) -->
    <div class="table-container" style="z-index: 3;">
       <div class="background-images">
            <div  class="bg-audiojungle"></div>
            <div  class="bg-activeden"></div>
            <div  class="bg-photodune"></div>
        </div>
        <div class="content">
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
            <div class="info-section">
                <!-- Tabs (no JS) -->
                <div class="tabs">
                    <a href="#about2" class="tab">Про Envato</a>
                    <a href="#marketplaces2" class="tab">Магазини</a>
                    <a href="#tuts2" class="tab">Мережа Tuts+</a>
                </div>

                <div class="tab-content" id="about2">
                   <div class="logo-section">
                        <img src="envato-logo.png" alt="Логотип Envato">
                    </div>
                    <p>Інший текст про Envato...</p>
                    <div class="item-images">
                       <img src="item1.png" alt="Елемент 1">
                        <img src="item2.png" alt="Елемент 2">
                       <img src="item3.png" alt="Елемент 3">
                        <img src="item4.png" alt="Елемент 4">
                        <img src="item5.png" alt="Елемент 5">
                    </div>
                    <a class="visit-link" href="https://envato.com">Відвідайте веб-сайт Envato</a>
                </div>

                <div class="tab-content" id="marketplaces2">
                    Інший вміст магазинів.
                </div>

                <div class="tab-content" id="tuts2">
                    Інший вміст мережі Tuts+.
                </div>
            </div>
        </div>
    </div>

    <!-- Третя "таблиця" (з іншим z-index і контентом) -->
    <div class="table-container" style="z-index: 2;">
         <div class="background-images">
            <div  class="bg-audiojungle"></div>
            <div  class="bg-activeden"></div>
            <div  class="bg-photodune"></div>
        </div>
        <div class="content">
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
            <div class="info-section">
                <!-- Tabs (no JS) -->
                <div class="tabs">
                    <a href="#about3" class="tab">Про Envato</a>
                    <a href="#marketplaces3" class="tab">Магазини</a>
                    <a href="#tuts3" class="tab">Мережа Tuts+</a>
                </div>

                 <div class="tab-content" id="about3">
                    <div class="logo-section">
                       <img src="envato-logo.png" alt="Логотип Envato">
                    </div>
                    <p>Ще інший текст про Envato...</p>
                     <div class="item-images">
                        <img src="item1.png" alt="Елемент 1">
                        <img src="item2.png" alt="Елемент 2">
                         <img src="item3.png" alt="Елемент 3">
                       <img src="item4.png" alt="Елемент 4">
                        <img src="item5.png" alt="Елемент 5">
                    </div>
                    <a class="visit-link"  href="https://envato.com">Відвідайте веб-сайт Envato</a>
                </div>

                <div class="tab-content" id="marketplaces3">
                   Ще інший вміст магазинів.
                </div>

                <div class="tab-content" id="tuts3">
                   Ще інший вміст мережі Tuts+.
                </div>
            </div>
        </div>
    </div>
</div>

</body>
</html>
