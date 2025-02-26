
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ЯПровайдер - приложение для управления роутерами Mikrotik</title>
    <style>
        :root {
            --primary-color: #3498db;
            --secondary-color: #2c3e50;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #34495e;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light-color);
            color: var(--dark-color);
            line-height: 1.6;
        }
        
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            display: flex;
            align-items: center;
        }
        
        .logo-icon {
            margin-right: 10px;
            font-size: 2rem;
        }
        
        .menu {
            display: flex;
            list-style: none;
        }
        
        .menu li {
            margin-left: 1.5rem;
        }
        
        .menu a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .menu a:hover {
            color: var(--light-color);
        }
        
        .hero {
            background: linear-gradient(rgba(44, 62, 80, 0.8), rgba(44, 62, 80, 0.8)), url('/api/placeholder/1200/600') center/cover;
            color: white;
            text-align: center;
            padding: 8rem 2rem 6rem;
            margin-top: 60px;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 2rem;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        
        .btn:hover {
            background-color: #c0392b;
        }
        
        .features {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 0 2rem;
        }
        
        .section-title {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 3rem;
            color: var(--secondary-color);
        }
        
        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .feature-card {
            background-color: white;
            border-radius: 10px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
        }
        
        .feature-icon {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 1.5rem;
        }
        
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--secondary-color);
        }
        
        .tariffs {
            background-color: var(--secondary-color);
            color: white;
            padding: 4rem 2rem;
        }
        
        .tariff-plans {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .tariff-card {
            background-color: white;
            color: var(--dark-color);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .tariff-header {
            background-color: var(--primary-color);
            color: white;
            padding: 1.5rem;
            text-align: center;
        }
        
        .tariff-price {
            font-size: 2.5rem;
            font-weight: bold;
            margin: 1rem 0;
        }
        
        .tariff-period {
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        .tariff-features {
            padding: 2rem;
            list-style: none;
        }
        
        .tariff-features li {
            padding: 0.5rem 0;
            border-bottom: 1px solid #eee;
        }
        
        .tariff-features li:last-child {
            border-bottom: none;
        }
        
        .tariff-footer {
            padding: 1.5rem;
            text-align: center;
        }
        
        .btn-secondary {
            background-color: var(--primary-color);
        }
        
        .btn-secondary:hover {
            background-color: #2980b9;
        }
        
        .reviews {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 0 2rem;
        }
        
        .review-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .review-card {
            background-color: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .review-header {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .review-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background-color: var(--primary-color);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.5rem;
            font-weight: bold;
            margin-right: 1rem;
        }
        
        .review-stars {
            color: gold;
            font-size: 1.2rem;
            margin-top: 0.5rem;
        }
        
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 4rem 2rem 2rem;
        }
        
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .footer-logo {
            font-size: 1.8rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }
        
        .footer-links h3 {
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: #bdc3c7;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .footer-contact p {
            margin-bottom: 0.8rem;
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            margin-top: 2rem;
            border-top: 1px solid #4a5c6a;
            max-width: 1200px;
            margin: 2rem auto 0;
        }
        
        .social-icons {
            display: flex;
            justify-content: center;
            margin-bottom: 1rem;
        }
        
        .social-icons a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: #4a5c6a;
            color: white;
            border-radius: 50%;
            margin: 0 0.5rem;
            text-decoration: none;
            transition: background-color 0.3s;
        }
        
        .social-icons a:hover {
            background-color: var(--primary-color);
        }
        
        @media (max-width: 768px) {
            .menu {
                display: none;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">
                <span class="logo-icon">⚡</span>
                <span>ЯПровайдер</span>
            </div>
            <ul class="menu">
                <li><a href="#features">Услуги</a></li>
                <li><a href="#tariffs">Тарифы</a></li>
                <li><a href="#reviews">Отзывы</a></li>
                <li><a href="#contacts">Контакты</a></li>
                <li><a href="#" class="btn">Личный кабинет</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero">
        <h1>ЯПровайдер — это невероятно универсальное приложение</h1>
        <p>С помощью приложения ЯПровайдер для Android вы можете настроить Wi-Fi hotspot с ограничением по времени, используя билеты. Также вы можете распределять интернет-канал между вашими клиентами так, как вам нужно, одновременно защищая ваш роутер и устройства пользователей. Независимо от того, предоставляете ли вы доступ в интернет клиентам, которые полагаются на ваше оборудование, или хотите улучшить доступ для клиентов, которым нужна высокая скорость, ЯПровайдер поможет вам.

Управление сетевыми портами ЯПровайдер разделяет ваших клиентов друг от друга и от вашей сети, обеспечивая максимальную безопасность и контроль. Вы можете ограничивать скорость интернета для каждого клиента, чтобы лучше управлять своей сетью, а также зарабатывать или предоставлять другие преимущества.

Например, в отеле ЯПровайдер может помочь вам создать hotspot и поделиться вашим интернет-соединением с помощью системы билетов. Вы можете настроить hotspot в вашем отеле, хостеле, гостевом доме, кафе, ресторане, лаундже или любом другом общественном месте, чтобы повысить комфорт для ваших клиентов. Установите ограничение скорости интернета для пользователей и печатайте билеты, выбирая время соединения и количество устройств. ЯПровайдер поможет вам предложить премиальный интернет-сервис клиентам, которые в нем нуждаются. Будь то онлайн-обучение, преподавание, просмотр телевизора или проведение онлайн-конференций, ImProvider обеспечивает постоянный и надежный доступ для всех ваших клиентов.

Времена, когда нужно было полагаться на системного администратора для выполнения этих задач, остались в прошлом. ЯПровайдер — это универсальное решение, которое позволяет вам полностью контролировать предоставление интернета и управление сетью. Благодаря полностью настраиваемому приложению мы можем адаптировать ЯПровайдер исключительно под ваше оборудование и требования.

Обратите внимание, что ImProvider абсолютно безопасен. Он не отправляет вашу информацию куда-либо и не открывает ваш роутер для подключения извне.</p>
        <a href="#tariffs" class="btn">Выбрать тариф</a>
    </section>

    <section class="features" id="features">
        <h2 class="section-title">Наши услуги</h2>
        <div class="feature-grid">
            <div class="feature-card">
                <div class="feature-icon">🚀</div>
                <h3>Высокоскоростной интернет</h3>
                <p>Скорость до 1 Гбит/с с гарантированной стабильностью соединения и низкой задержкой.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">📺</div>
                <h3>Цифровое ТВ</h3>
                <p>Более 200 каналов в высоком качестве, включая 4K-контент и возможность просмотра на любых устройствах.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">📱</div>
                <h3>Мобильная связь</h3>
                <p>Выгодные тарифы со множеством бесплатных услуг и большим объемом трафика.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">☁️</div>
                <h3>Облачные сервисы</h3>
                <p>Надежное хранение данных с возможностью резервного копирования и быстрого доступа.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🛡️</div>
                <h3>Защита от киберугроз</h3>
                <p>Комплексные решения по кибербезопасности для защиты ваших данных.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🏢</div>
                <h3>Решения для бизнеса</h3>
                <p>Интегрированные решения для организаций любого масштаба с круглосуточной поддержкой.</p>
            </div>
        </div>
    </section>

    <section class="tariffs" id="tariffs">
        <h2 class="section-title" style="color: white;">Тарифные планы</h2>
        <div class="tariff-plans">
            <div class="tariff-card">
                <div class="tariff-header">
                    <h3>Стандарт</h3>
                    <div class="tariff-price">699 ₽</div>
                    <div class="tariff-period">в месяц</div>
                </div>
                <ul class="tariff-features">
                    <li>Интернет 100 Мбит/с</li>
                    <li>50 ТВ каналов</li>
                    <li>Wi-Fi роутер в аренду</li>
                    <li>Техническая поддержка</li>
                </ul>
                <div class="tariff-footer">
                    <a href="#" class="btn btn-secondary">Подключить</a>
                </div>
            </div>
            <div class="tariff-card">
                <div class="tariff-header" style="background-color: #e74c3c;">
                    <h3>Оптимальный</h3>
                    <div class="tariff-price">999 ₽</div>
                    <div class="tariff-period">в месяц</div>
                </div>
                <ul class="tariff-features">
                    <li>Интернет 300 Мбит/с</li>
                    <li>150 ТВ каналов</li>
                    <li>Wi-Fi роутер в комплекте</li>
                    <li>Антивирус в подарок</li>
                    <li>Приоритетная поддержка</li>
                </ul>
                <div class="tariff-footer">
                    <a href="#" class="btn" style="background-color: #e74c3c;">Подключить</a>
                </div>
            </div>
            <div class="tariff-card">
                <div class="tariff-header">
                    <h3>Максимальный</h3>
                    <div class="tariff-price">1499 ₽</div>
                    <div class="tariff-period">в месяц</div>
                </div>
                <ul class="tariff-features">
                    <li>Интернет 1 Гбит/с</li>
                    <li>200+ ТВ каналов, включая 4K</li>
                    <li>Wi-Fi 6 роутер в комплекте</li>
                    <li>Пакет кибербезопасности</li>
                    <li>Облачное хранилище 1 ТБ</li>
                    <li>VIP поддержка 24/7</li>
                </ul>
                <div class="tariff-footer">
                    <a href="#" class="btn btn-secondary">Подключить</a>
                </div>
            </div>
        </div>
    </section>

    <section class="reviews" id="reviews">
        <h2 class="section-title">Отзывы наших клиентов</h2>
        <div class="review-grid">
            <div class="review-card">
                <div class="review-header">
                    <div class="review-avatar">АК</div>
                    <div>
                        <h4>Александр Ковалев</h4>
                        <div class="review-stars">★★★★★</div>
                    </div>
                </div>
                <p>Пользуюсь услугами япровайдер уже 3 года. Скорость интернета всегда соответствует заявленной, а если возникают вопросы, техподдержка реагирует моментально.</p>
            </div>
            <div class="review-card">
                <div class="review-header">
                    <div class="review-avatar">МС</div>
                    <div>
                        <h4>Мария Соколова</h4>
                        <div class="review-stars">★★★★☆</div>
                    </div>
                </div>
                <p>Перешла на япровайдер от другого оператора и очень довольна. Подключение прошло быстро, а качество сигнала и стабильность намного лучше, чем у предыдущего провайдера.</p>
            </div>
            <div class="review-card">
                <div class="review-header">
                    <div class="review-avatar">ИВ</div>
                    <div>
                        <h4>Игорь Волков</h4>
                        <div class="review-stars">★★★★★</div>
                    </div>
                </div>
                <p>Наша компания использует корпоративные решения от япровайдер. Отличная инфраструктура, надежные серверы и грамотная техподдержка. Рекомендую для бизнеса!</p>
            </div>
        </div>
    </section>

    <footer id="contacts">
        <div class="footer-content">
            <div class="footer-about">
                <div class="footer-logo">
                    <span>⚡ япровайдер</span>
                </div>
                <p>Мы стремимся предоставлять высококачественные услуги связи, которые улучшают жизнь наших клиентов и помогают развиваться их бизнесу.</p>
            </div>
            <div class="footer-links">
                <h3>Услуги</h3>
                <ul>
                    <li><a href="#">Домашний интернет</a></li>
                    <li><a href="#">Цифровое ТВ</a></li>
                    <li><a href="#">Мобильная связь</a></li>
                    <li><a href="#">Облачные сервисы</a></li>
                    <li><a href="#">Решения для бизнеса</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h3>Компания</h3>
                <ul>
                    <li><a href="#">О нас</a></li>
                    <li><a href="#">Новости</a></li>
                    <li><a href="#">Карьера</a></li>
                    <li><a href="#">Партнерам</a></li>
                    <li><a href="#">Контакты</a></li>
                </ul>
            </div>
            <div class="footer-contact">
                <h3>Контактная информация</h3>
                <p>📱 8 (800) 123-45-67</p>
                <p>📧 77@info.ru</p>
                <p>🏙️ Москва, ул. Цифровая, д. 42</p>
                <p>⏰ Пн-Вс: 8:00 - 22:00</p>
            </div>
        </div>
        <div class="footer-bottom">
            <div class="social-icons">
                <a href="#">VK</a>
                <a href="#">TG</a>
                <a href="#">OK</a>
            </div>
            <p>© 2025 япровайдер. Все права защищены.</p>
        </div>
    </footer>
</body>
</html>
