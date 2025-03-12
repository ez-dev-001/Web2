<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Макет Envato</title>
    <style>
        body {
            font-family: sans-serif;
            background-image: url('bokeh-background.jpg'); /* Замініть на ваше зображення боке */
            background-size: cover;
            margin: 0; /* Видалити стандартні відступи body */
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh; /* Забезпечити повну висоту вікна перегляду */
        }

        .container {
            display: flex;
            flex-wrap: wrap; /* Дозволити модулям переноситися на менших екранах */
            max-width: 1200px; /* Обмежити максимальну ширину */
            width: 95%; /* Використовувати більшу частину екрана, але з деякими відступами */
            gap: 20px; /* Простір між модулями */
        }

        .module {
            width: calc(50% - 20px); /* Два модулі в рядку, враховуючи проміжок */
            min-height: 200px; /* Мінімальна висота, налаштуйте за потребою */
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
            font-size: 1.5em;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2); /* Додати тонку тінь */
            box-sizing: border-box; /* Включити відступи в ширину/висоту */
        }

        .module img {
            max-width: 80%; /* Переконайтеся, що зображення вміщуються в модуль */
            height: auto;
            margin-bottom: 10px;
        }

        .audiojungle {
            background-color: #4CAF50; /* Зелений */
        }

        .activeden {
            background-color: #FFA500; /* Помаранчевий */
        }

        .photodune {
            background-color: #2196F3; /* Синій */
        }


        .info-section {
            width: 100%;
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            box-sizing: border-box;
        }

        .tabs {
            display: flex;
            margin-bottom: 15px;
        }

        .tab {
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-bottom: none;
            border-radius: 5px 5px 0 0;
            background-color: #eee;
            cursor: pointer;
            margin-right: 5px;
        }

        .tab.active {
            background-color: white;
            border-bottom: 1px solid white; /* Приховати нижню межу активної вкладки */
        }

        .tab-content {
            border: 1px solid #ddd;
            padding: 15px;
            border-radius: 0 5px 5px 5px; /* Закруглити тільки нижні кути */
        }
        .logo-section{
            display:flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .logo-section img {
            max-height:50px;
            margin-right: 10px;
        }

        .item-images {
            display: flex;
            flex-wrap: wrap; /* Дозволити зображенням переноситися */
            gap: 10px;
        }

        .item-images img {
            max-width: 80px; /* Налаштуйте за потребою */
            height: auto;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .time-modules {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            width: calc(50% - 20px); /* Займає те саме місце, що й більший модуль */
        }
        .time-module{
            width: calc(33.33% - 10px); /* 3 модулі в рядку */
            height: 80px;
            background-color: lightgrey;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            border-radius: 5px;
        }

        .time-module img{
            width: 40px;
            height:40px;
            margin-bottom: 5px;
        }
         /* Адаптивні налаштування */
        @media (max-width: 768px) {
            .module, .time-modules {
                width: 100%; /* Повна ширина на менших екранах */
            }
             .time-module{
                width: calc(50% - 10px); /*Два на рядок на середніх пристроях.*/
            }
        }



    </style>
</head>
<body>

<div class="container">

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
            <img src="envato-icon.png" alt="envato">
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
    <div class="module audiojungle">
        <img src="snake.png" alt="Audiojungle Змія">
        audiojungle
    </div>
    <div class="module photodune">
        <img src="beetle.png" alt="Photodune Жук">
        photodune
    </div>
    <div class="module activeden">
        <img src="fox.png" alt="Activeden Лисиця">
        activeden
    </div>



    <div class="info-section">
        <div class="tabs">
            <div class="tab active" onclick="showTab('about')">Про Envato</div>
            <div class="tab" onclick="showTab('marketplaces')">Магазини</div>
            <div class="tab" onclick="showTab('tuts')">Мережа Tuts+</div>
        </div>

        <div class="tab-content" id="about">
             <div class="logo-section">
                <img src="envato-logo.png" alt="Логотип Envato">
            </div>
            <p>Envato – це стартап, що базується в Австралії, з людьми по всьому світу та сайтами, які щосекунди обслуговують сторінки. Ми почали у вітальні в 2006 році і з того часу неухильно працюємо над тим, щоб перетворити нашу компанію на претендента світового класу. Наш досвід – творчість, ми любимо відкритий код, ми віримо, що робота – це набагато більше, ніж просто заробляння грошей, і ми повністю віддані створенню чудових продуктів!</p>

            <div class="item-images">
                <img src="item1.png" alt="Елемент 1">
                <img src="item2.png" alt="Елемент 2">
                <img src="item3.png" alt="Елемент 3">
                <img src="item4.png" alt="Елемент 4">
                <img src="item5.png" alt="Елемент 5">
                <!-- Додайте більше зображень елементів за потребою -->
            </div>
            <a href="https://envato.com">Відвідайте веб-сайт Envato</a>
        </div>

        <div class="tab-content" id="marketplaces" style="display: none;">
            Вміст магазинів тут.
        </div>

        <div class="tab-content" id="tuts" style="display: none;">
            Вміст мережі Tuts+ тут.
        </div>
    </div>
</div>

<script>
    function showTab(tabId) {
        // Сховати весь вміст вкладок
        const tabContents = document.querySelectorAll('.tab-content');
        tabContents.forEach(content => {
            content.style.display = 'none';
        });

        // Видалити клас 'active' з усіх вкладок
        const tabs = document.querySelectorAll('.tab');
        tabs.forEach(tab => {
            tab.classList.remove('active');
        });

        // Показати вміст вибраної вкладки та позначити вкладку як активну
        document.getElementById(tabId).style.display = 'block';
        event.currentTarget.classList.add('active');
    }
</script>

</body>
</html>
