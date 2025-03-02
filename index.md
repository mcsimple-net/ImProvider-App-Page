<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ЯПровайдер</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background-color: #f7f7f7;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            display: flex;
            align-items: center;
        }

        .logo img {
            height: 40px;
            margin-right: 10px;
        }

        .logo h1 {
            font-size: 24px;
            color: #0066cc;
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav li {
            margin-left: 20px;
        }

        nav a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }

        nav a:hover {
            color: #0066cc;
        }

        .login-btn {
            background-color: #0066cc;
            color: white;
            padding: 8px 15px;
            border-radius: 4px;
        }

        .login-btn:hover {
            background-color: #0055aa;
            color: white;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #0066cc, #00aaff);
            color: white;
            padding: 80px 0;
            text-align: center;
        }

        .hero h2 {
            font-size: 36px;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 18px;
            max-width: 800px;
            margin: 0 auto 30px;
            line-height: 1.6;
        }

        .cta-btn {
            display: inline-block;
            background-color: white;
            color: #0066cc;
            padding: 12px 30px;
            border-radius: 30px;
            font-weight: bold;
            font-size: 16px;
            text-decoration: none;
            transition: all 0.3s;
        }

        .cta-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        /* Features Section */
        .features {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 32px;
            margin-bottom: 50px;
            color: #0066cc;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
        }

        .feature-img {
            height: 200px;
            overflow: hidden;
        }

        .feature-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .feature-card:hover .feature-img img {
            transform: scale(1.1);
        }

        .feature-content {
            padding: 20px;
        }

        .feature-content h3 {
            font-size: 20px;
            margin-bottom: 10px;
            color: #0066cc;
        }

        .feature-content p {
            color: #666;
            line-height: 1.6;
        }

        /* Plans Section */
        .plans {
            padding: 80px 0;
            background-color: #e6f2ff;
        }

        .plans-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .plan-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
            display: flex;
            flex-direction: column;
        }

        .plan-card:hover {
            transform: translateY(-5px);
        }

        .plan-header {
            padding: 20px;
            background-color: #0066cc;
            color: white;
            text-align: center;
        }

        .plan-header h3 {
            font-size: 24px;
        }

        .plan-price {
            font-size: 36px;
            margin: 10px 0;
        }

        .plan-price span {
            font-size: 16px;
        }

        .plan-features {
            padding: 20px;
            flex-grow: 1;
        }

        .plan-features ul {
            list-style: none;
            margin-bottom: 25px;
        }

        .plan-features li {
            padding: 8px 0;
            border-bottom: 1px solid #eee;
            display: flex;
            align-items: center;
        }

        .plan-features li:before {
            content: "✓";
            color: #0066cc;
            margin-right: 10px;
            font-weight: bold;
        }

        .plan-features a {
            display: block;
            text-align: center;
            background-color: #0066cc;
            color: white;
            padding: 12px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s;
        }

        .plan-features a:hover {
            background-color: #0055aa;
        }

        /* Testimonials */
        .testimonials {
            padding: 80px 0;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background-color: white;
            border-radius: 8px;
            padding: 25px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }

        .testimonial-text {
            font-style: italic;
            color: #666;
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
        }

        .author-img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 15px;
        }

        .author-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .author-info h4 {
            font-size: 16px;
            margin-bottom: 5px;
        }

        .author-info p {
            color: #666;
            font-size: 14px;
        }

        /* Coverage Section */
        .coverage {
            padding: 80px 0;
            background-color: #e6f2ff;
            text-align: center;
        }

        .coverage-map {
            margin: 0 auto;
            max-width: 800px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 20px rgba(0, 0, 0, 0.15);
        }

        .coverage-map img {
            width: 100%;
            display: block;
        }

        /* Contact Section */
        .contact {
            padding: 80px 0;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .contact-info {
            background-color: #0066cc;
            color: white;
            padding: 30px;
            border-radius: 8px;
        }

        .contact-info h3 {
            font-size: 24px;
            margin-bottom: 20px;
        }

        .info-item {
            display: flex;
            margin-bottom: 15px;
        }

        .info-item i {
            margin-right: 10px;
            font-size: 20px;
        }

        .contact-form {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }

        .contact-form h3 {
            font-size: 24px;
            margin-bottom: 20px;
            color: #0066cc;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            color: #666;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }

        .form-group textarea {
            height: 120px;
        }

        .submit-btn {
            background-color: #0066cc;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .submit-btn:hover {
            background-color: #0055aa;
        }

        /* Footer */
        footer {
            background-color: #333;
            color: #fff;
            padding: 50px 0 20px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .footer-section h3 {
            font-size: 18px;
            margin-bottom: 20px;
            color: #0099ff;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: white;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: #555;
            color: white;
            border-radius: 50%;
            text-decoration: none;
            transition: background-color 0.3s;
        }

        .social-links a:hover {
            background-color: #0066cc;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid #555;
            color: #aaa;
            font-size: 14px;
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            font-size: 24px;
            background: none;
            border: none;
            color: #0066cc;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }

            nav ul {
                display: none;
                position: absolute;
                top: 70px;
                left: 0;
                right: 0;
                background-color: white;
                flex-direction: column;
                padding: 20px;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
            }

            nav li {
                margin: 10px 0;
            }

            .hero h2 {
                font-size: 28px;
            }

            .section-title {
                font-size: 26px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-container">
            <div class="logo">
                <img src="/api/placeholder/40/40" alt="ImProvider Logo" />
                <h1>ImProvider</h1>
            </div>
            <button class="mobile-menu-btn">☰</button>
            <!---
            <nav>
                <ul>
                    <li><a href="#features">1</a></li>
                    <li><a href="#plans">2</a></li>
                    <li><a href="#testimonials">3</a></li>
                    <li><a href="#coverage">4</a></li>
                    <li><a href="#contact">5</a></li>
                    <li><a href="#" class="login-btn">6</a></li>
                </ul>
            </nav>
                --->
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h2>Приложение для управления роутерами Mikrotik</h2>
            <p>123</p>
            <a href="#plans" class="cta-btn">c</a>
        </div>
    </section>

    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Why you need it</h2>
            <div class="features-grid">
                <div class="feature-card">
                <!---
                    <div class="feature-img">
                        <img src="/api/placeholder/400/200" alt="Высокая скорость" />
                    </div>
                    --->
                    <div class="feature-content">
                        
                        <p>ImProvider is an incredibly versatile app. Using the ImProvider Android app, you can set up a time-controlled Wi-Fi hotspot using tickets. Also you can divide the internet channel between your clients whatever you need and at the same time protect your router and the user's devices. Whether you are providing internet access to clients who rely on your equipment, or are looking to improve access for customers in need of faster speeds, ImProvider has you covered.

ImProvider Network Ports Management separates your clients from each other and from your network, ensuring maximum security and control. You can limit each client's internet speed access for greater control over your network and the ability to earn money or provide other incentives.

For instance, in a hotel ImProvider can help you to create the hotspot and share your internet connection using ticket system. You can set up the hotspot in your hotel, hostel, guest house, cafe, restaurant, lounge, or any public space to increase comfort for your clients. Set the internet speed limit for the users and print tickets selecting connection time and quantity of devices. ImProvider can help you offer premium internet services to customers who need it. Whether it's for online studies, teaching, watching TV, or hosting an online conference, ImProvider ensures constant reliable access for all of your clients. 

Gone are the days of relying on a system administrator to handle these tasks. ImProvider is the all-in-one solution that empowers you to take full control over your internet provision and network management. And, with our fully customizable app, we can tailor ImProvider exclusively to your equipment and requirements.

Kindly note that ImProvider is absolutely secure. It doesn't send your information anywhere or open you router for connecting from outside. </p>


                    </div>
 </section>

 <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">How Internet providers do business</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <!---
                    <div class="feature-img">
                        <img src="/api/placeholder/400/200" alt="Высокая скорость" />
                    </div>
                    --->
                    <div class="feature-content">
                        <h3></h3>
                        <p>An internet provider is a company that provides clients with access to the internet in exchange for payment. Providers purchase access from first-level operators (Tier-1) and resell it to another providers. Local provider sells it to end-users, offering internet services as a service rather than a product.

As a provider, you can sell access to your internet channel multiple times, typically up to 5 times the width of the channel. For instance, if you have a 100-megabit internet channel, you can sell access to five clients at 50 megabits and ten clients at 10 megabits, making it a viable project. With competitive pricing, you can offer a lower rate than your provider, earning profits while providing high-speed internet to your clients. It's crucial to ensure that no single client uses more than half of your channel's capacity to avoid bandwidth issues for other users.

Join the league of successful internet providers and provide your clients with fast, reliable internet access. </p>


                    </div>

 </section>
                
                <!---
                <div class="feature-card">
                    <div class="feature-img">
                        <img src="/api/placeholder/400/200" alt="Надежное соединение" />
                    </div>
                    <div class="feature-content">
                        <h3>Надежное соединение</h3>
                        <p>Наша инфраструктура обеспечивает стабильность на уровне 99.9%, чтобы вы могли быть на связи в любое время суток без сбоев и перерывов.</p>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-img">
                        <img src="/api/placeholder/400/200" alt="Профессиональная поддержка" />
                    </div>
                    <div class="feature-content">
                        <h3>Профессиональная поддержка</h3>
                        <p>Наша служба поддержки доступна 24/7, чтобы решить любые технические вопросы и обеспечить бесперебойную работу вашего интернета.</p>
                    </div>
                    --->
                </div>
            </div>
        </div>
    </section>

    <section class="plans" id="plans">
        <div class="container">
            <h2 class="section-title">Выберите свой тариф</h2>
            <div class="plans-grid">
                <div class="plan-card">
                    <div class="plan-header">
                        <h3>Базовый</h3>
                        <div class="plan-price">450₽ <span>/мес</span></div>
                    </div>
                    <div class="plan-features">
                        <ul>
                            <li>Скорость до 100 Мбит/с</li>
                            <li>Безлимитный трафик</li>
                            <li>Wi-Fi роутер в аренду</li>
                            <li>Базовая техподдержка</li>
                        </ul>
                        <a href="#">Выбрать тариф</a>
                    </div>
                </div>
                <div class="plan-card">
                    <div class="plan-header">
                        <h3>Стандарт</h3>
                        <div class="plan-price">650₽ <span>/мес</span></div>
                    </div>
                    <div class="plan-features">
                        <ul>
                            <li>Скорость до 300 Мбит/с</li>
                            <li>Безлимитный трафик</li>
                            <li>Wi-Fi роутер бесплатно</li>
                            <li>Приоритетная техподдержка</li>
                            <li>Антивирус в подарок</li>
                        </ul>
                        <a href="#">Выбрать тариф</a>
                    </div>
                </div>
                <div class="plan-card">
                    <div class="plan-header">
                        <h3>Премиум</h3>
                        <div class="plan-price">950₽ <span>/мес</span></div>
                    </div>
                    <div class="plan-features">
                        <ul>
                            <li>Скорость до 1 Гбит/с</li>
                            <li>Безлимитный трафик</li>
                            <li>Премиум Wi-Fi роутер бесплатно</li>
                            <li>VIP техподдержка 24/7</li>
                            <li>Расширенный пакет безопасности</li>
                            <li>Статический IP-адрес</li>
                        </ul>
                        <a href="#">Выбрать тариф</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="testimonials" id="testimonials">
        <div class="container">
            <h2 class="section-title">Что говорят наши клиенты</h2>
            <div class="testimonials-grid">
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "Пользуюсь услугами ImProvider уже более года и могу с уверенностью сказать, что это лучший провайдер в нашем районе. Скорость всегда соответствует заявленной, а техподдержка отвечает моментально."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="/api/placeholder/50/50" alt="Фото клиента" />
                        </div>
                        <div class="author-info">
                            <h4>Алексей Петров</h4>
                            <p>Москва</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "После переключения на ImProvider я наконец-то могу смотреть фильмы в 4K без постоянных зависаний. Кроме того, установка прошла быстро и качественно, а цены приятно удивили по сравнению с моим предыдущим провайдером."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="/api/placeholder/50/50" alt="Фото клиента" />
                        </div>
                        <div class="author-info">
                            <h4>Мария Иванова</h4>
                            <p>Санкт-Петербург</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "Как владелец малого бизнеса, я очень ценю надежность и стабильность интернет-соединения. ImProvider обеспечивает именно это, что позволяет нам эффективно работать без простоев. Отдельное спасибо за корпоративную поддержку!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="/api/placeholder/50/50" alt="Фото клиента" />
                        </div>
                        <div class="author-info">
                            <h4>Дмитрий Соколов</h4>
                            <p>Казань</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="coverage" id="coverage">
        <div class="container">
            <h2 class="section-title">Зоны покрытия</h2>
            <p>Мы постоянно расширяем нашу сеть, чтобы предоставлять услуги высокоскоростного интернета как можно большему числу клиентов. Проверьте, доступен ли наш сервис в вашем районе.</p>
            <div class="coverage-map">
                <img src="/api/placeholder/800/400" alt="Карта покрытия" />
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <div class="container">
            <h2 class="section-title">Свяжитесь с нами</h2>
            <div class="contact-grid">
                <div class="contact-info">
                    <h3>Наши контакты</h3>
                    <div class="info-item">
                        <i>📱</i>
                        <span>+7 (800) 123-45-67</span>
                    </div>
                    <div class="info-item">
                        <i>📧</i>
                        <span>info@improvider.ru</span>
                    </div>
                    <div class="info-item">
                        <i>🏢</i>
                        <span>Москва, ул. Интернетная, д. 42</span>
                    </div>
                    <div class="info-item">
                        <i>⏰</i>
                        <span>Пн-Вс: 8:00 - 20:00</span>
                    </div>
                </div>
                <div class="contact-form">
                    <h3>Отправить сообщение</h3>
                    <form>
                        <div class="form-group">
                            <label for="name">Имя</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Телефон</label>
                            <input type="tel" id="phone" name="phone" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Сообщение</label>
                            <textarea id="message" name="message" required></textarea>
                        </div>
                        <button type="submit" class="submit-btn">Отправить</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-section">
                    <h3>ImProvider</h3>
                    <p>Мы стремимся предоставлять высококачественные услуги интернет-связи для дома и бизнеса по доступным ценам.</p>
                    <div class="social-links">
                        <a href="#"><span>FB</span></a>
                        <a href="#"><span>TW</span></a>
                        <a href="#"><span>IG</span></a>
                        <a href="#"><span>VK</span></a>
                    </div>
                </div>
                <div class="footer-section">
                    <h3>Услуги</h3>
                    <ul class="footer-links">
                        <li><a href="#">Домашний интернет</a></li>
                        <li><a href="#">Бизнес-решения</a></li>
                        <li><a href="#">Выделенные линии</a></li>
                        <li><a href="#">VPN сервисы</a></li>
                        <li><a href="#">Облачные хранилища</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Компания</h3>
                    <ul class="footer-links">
                        <li><a href="#">О нас</a></li>
                        <li><a href="#">Команда</a></li>
                        <li><a href="#">Карьера</a></li>
                        <li><a href="#">Новости</a></li>
                        <li><a href="#">Блог</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Поддержка</h3>
                    <ul class="footer-links">
                        <li><a href="#">Справочный центр</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Связаться с нами</a></li>
                        <li><a href="#">Статус сети</a></li>
                        <li><a href="#">Правовая информация</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 ImProvider. Все права защищены.</p>
            </div>
        </div>
    </footer>
</body>
</html>
