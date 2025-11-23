<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мой сайт-визитка</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Верхнее меню */
        .top-menu {
            background: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .menu-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            gap: 40px;
        }
        
        .menu-item {
            padding: 10px 20px;
            cursor: pointer;
            font-weight: 500;
            color: #333;
            transition: all 0.3s ease;
            border-radius: 5px;
            text-decoration: none;
        }
        
        .menu-item:hover {
            background: #f0f7ff;
            color: #2575fc;
        }
        
        header {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            color: white;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .profile-img {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 5px solid rgba(255,255,255,0.3);
            object-fit: cover;
            margin-bottom: 20px;
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
        }
        
        .tagline {
            font-size: 1.3rem;
            opacity: 0.9;
        }
        
        section {
            background: white;
            padding: 40px;
            margin-bottom: 30px;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
            scroll-margin-top: 80px;
        }
        
        h2 {
            color: #2575fc;
            margin-bottom: 25px;
            padding-bottom: 10px;
            border-bottom: 2px solid #f0f0f0;
            font-size: 1.8rem;
        }
        
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .gallery-item {
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        
        .gallery-item:hover {
            transform: translateY(-5px);
        }
        
        .gallery-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            display: block;
        }
        
        .gallery-item p {
            padding: 15px;
            background: white;
        }
        
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 20px;
        }
        
        .skill {
            background: #f0f7ff;
            padding: 12px 20px;
            border-radius: 30px;
            font-weight: 500;
            color: #2575fc;
            border: 1px solid #d0e3ff;
        }
        
        .contact-info {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 20px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 20px;
            background: #f8f9fa;
            border-radius: 8px;
            text-decoration: none;
            color: #333;
            transition: all 0.3s ease;
        }
        
        .contact-item:hover {
            background: #2575fc;
            color: white;
            transform: translateY(-3px);
        }
        
        /* Стили для формы заказа */
        .order-form {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        .form-label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #333;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border 0.3s ease;
        }
        
        .form-control:focus {
            border-color: #2575fc;
            outline: none;
        }
        
        textarea.form-control {
            min-height: 120px;
            resize: vertical;
        }
        
        .form-row {
            display: flex;
            gap: 20px;
        }
        
        .form-col {
            flex: 1;
        }
        
        .service-options {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 10px;
        }
        
        .service-option {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .service-option:hover {
            border-color: #2575fc;
            background: #f0f7ff;
        }
        
        .service-option.selected {
            border-color: #2575fc;
            background: #e6f0ff;
        }
        
        .service-price {
            font-weight: 600;
            color: #2575fc;
            margin-left: auto;
        }
        
        .btn {
            display: inline-block;
            padding: 14px 30px;
            background: #2575fc;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
            text-decoration: none;
        }
        
        .btn:hover {
            background: #1c65e0;
            transform: translateY(-2px);
        }
        
        .btn-block {
            display: block;
            width: 100%;
        }
        
        footer {
            text-align: center;
            padding: 25px;
            background: #333;
            color: white;
            border-radius: 10px;
            margin-top: 30px;
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }
            
            .menu-container {
                flex-direction: column;
                gap: 10px;
                text-align: center;
            }
            
            header {
                padding: 40px 20px;
            }
            
            h1 {
                font-size: 2.2rem;
            }
            
            section {
                padding: 25px;
            }
            
            .form-row {
                flex-direction: column;
                gap: 0;
            }
        }
    </style>
</head>
<body>
    <!-- Верхнее меню -->
    <nav class="top-menu">
        <div class="menu-container">
            <a href="#portfolio" class="menu-item">Мои работы</a>
            <a href="#about" class="menu-item">Обо мне</a>
            <a href="#contact" class="menu-item">Контакты</a>
            <a href="#order" class="menu-item">Заказать</a>
        </div>
    </nav>

    <div class="container">
        <header>
            <img src="фото4.jpg" alt="Фото профиля" class="profile-img">
            <h1>Алексей Петров</h1>
            <p class="tagline">Фотограф и дизайнер</p>
        </header>

        <section id="portfolio">
            <h2>Мои работы</h2>
            <p>Вот некоторые из моих последних проектов в области фотографии и дизайна. Я специализируюсь на создании визуально привлекательных и эмоционально насыщенных изображений, которые рассказывают историю и вызывают отклик у зрителя. Каждый проект для меня - это возможность исследовать новые техники и подходы, чтобы достичь наилучшего результата для клиента.</p>
            <div class="gallery">
                <div class="gallery-item">
                    <img src="горныйпейзаж.jpg" alt="Горы">
                    <p>Горный пейзаж</p>
                </div>
                <div class="gallery-item">
                    <img src="архитектура.jpg" alt="Архитектура">
                    <p>Городская архитектура</p>
                </div>
                <div class="gallery-item">
                    <img src="море.jpg" alt="Море">
                    <p>Морской пейзаж</p>
                </div>
                <div class="gallery-item">
                    <img src="дизайнинтерьера.jpg" alt="Интерьер">
                    <p>Дизайн интерьера</p>
                </div>
            </div>
        </section>

        <section id="about">
            <h2>Обо мне</h2>
            <p>Я профессиональный фотограф и дизайнер с 7-летним опытом работы. Специализируюсь на портретной, пейзажной и архитектурной фотографии, а также на создании современных интерьеров. Моя карьера началась с учебы в Московской школе фотографии, где я освоил не только технические аспекты, но и художественное видение, необходимое для создания выразительных снимков.</p>
            <p>Моя цель - запечатлеть уникальные моменты и создать визуальные решения, которые вдохновляют и вызывают эмоции. Я верю, что хорошая фотография или дизайн должны не только соответствовать техническим стандартам, но и передавать настроение, историю и индивидуальность. В каждом проекте я стремлюсь найти баланс между творческим подходом и практическими потребностями клиента. С недавнего времени я решил увлечься составлением сайтов.
Для того, чтобы качественно изучить и понять как создавать сайты я пошёл на специальную программу обучения в Финансовый университет при Правительстве РФ! Надеюсь, у меня вышло неплохо!</p>
            <h3 style="margin-top: 25px; color: #2575fc;">Мои навыки</h3>
            <div class="skills-container">
                <div class="skill">Фотография</div>
                <div class="skill">Ретушь</div>
                <div class="skill">Дизайн интерьеров</div>
                <div class="skill">Adobe Photoshop</div>
                <div class="skill">Adobe Lightroom</div>
                <div class="skill">3D визуализация</div>
                <div class="skill">Композиция</div>
                <div class="skill">Работа со светом</div>
            </div>
        </section>

        <section id="order">
            <h2>Форма заказа</h2>
            <p>Заполните форму ниже, чтобы оформить заказ на мои услуги. Я свяжусь с вами в течение 24 часов для уточнения деталей и согласования сроков выполнения работы.</p>
            
            <form class="order-form" id="orderForm">
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label class="form-label" for="name">Ваше имя *</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                    </div>
                    <div class="form-col">
                        <div class="form-group">
                            <label class="form-label" for="phone">Телефон *</label>
                            <input type="tel" id="phone" class="form-control" required>
                        </div>
                    </div>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="email">Email *</label>
                    <input type="email" id="email" class="form-control" required>
                </div>
                
                <div class="form-group">
                    <label class="form-label">Выберите услугу *</label>
                    <div class="service-options">
                        <div class="service-option" data-service="portrait">
                            <input type="radio" id="portrait" name="service" value="portrait" style="display: none;">
                            <span>Портретная съемка</span>
                            <span class="service-price">5 000 ₽</span>
                        </div>
                        <div class="service-option" data-service="landscape">
                            <input type="radio" id="landscape" name="service" value="landscape" style="display: none;">
                            <span>Пейзажная съемка</span>
                            <span class="service-price">8 000 ₽</span>
                        </div>
                        <div class="service-option" data-service="architecture">
                            <input type="radio" id="architecture" name="service" value="architecture" style="display: none;">
                            <span>Архитектурная съемка</span>
                            <span class="service-price">10 000 ₽</span>
                        </div>
                        <div class="service-option" data-service="interior">
                            <input type="radio" id="interior" name="service" value="interior" style="display: none;">
                            <span>Дизайн интерьера</span>
                            <span class="service-price">15 000 ₽</span>
                        </div>
                        <div class="service-option" data-service="other">
                            <input type="radio" id="other" name="service" value="other" style="display: none;">
                            <span>Другая услуга</span>
                            <span class="service-price">по договоренности</span>
                        </div>
                    </div>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="date">Предпочтительная дата съемки/встречи</label>
                    <input type="date" id="date" class="form-control">
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="message">Дополнительная информация</label>
                    <textarea id="message" class="form-control" placeholder="Опишите ваши пожелания, идеи или особые требования..."></textarea>
                </div>
                
                <button type="submit" class="btn btn-block">Отправить заявку</button>
            </form>
        </section>

        <section id="contact">
            <h2>Контакты</h2>
            <p>Свяжитесь со мной для обсуждения вашего проекта или сотрудничества. Я всегда открыт к новым интересным предложениям и готов ответить на все ваши вопросы. Обычно я отвечаю в течение 24 часов, но в периоды высокой загруженности ответ может занять немного больше времени. Не стесняйтесь обращаться по любому из указанных ниже способов связи - я обязательно с вами свяжусь.</p>
            <div class="contact-info">
                <a href="tel:+79991234567" class="contact-item">
                    📞 +7 (999) 123-45-67
                </a>
                <a href="mailto:alexey@example.com" class="contact-item">
                    ✉️ alexey@example.com
                </a>
                <a href="https://instagram.com" class="contact-item">
                    📷 Instagram
                </a>
                <a href="https://t.me" class="contact-item">
                    📱 Telegram
                </a>
            </div>
        </section>

        <footer>
            <p>&copy; 2023 Алексей Петров. Все права защищены.</p>
        </footer>
    </div>

    <script>
        // Плавная прокрутка к разделам при клике на пункты меню
        document.querySelectorAll('.menu-item').forEach(item => {
            item.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetSection = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetSection.offsetTop - 80,
                    behavior: 'smooth'
                });
            });
        });
        
        // Выбор услуги в форме заказа
        document.querySelectorAll('.service-option').forEach(option => {
            option.addEventListener('click', function() {
                // Снимаем выделение со всех опций
                document.querySelectorAll('.service-option').forEach(opt => {
                    opt.classList.remove('selected');
                });
                
                // Выделяем выбранную опцию
                this.classList.add('selected');
                
                // Активируем соответствующий radio input
                const radioInput = this.querySelector('input[type="radio"]');
                radioInput.checked = true;
            });
        });
        
        // Обработка отправки формы
        document.getElementById('orderForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Проверяем, выбрана ли услуга
            const selectedService = document.querySelector('input[name="service"]:checked');
            if (!selectedService) {
                alert('Пожалуйста, выберите услугу');
                return;
            }
            
            // Получаем данные формы
            const formData = {
                name: document.getElementById('name').value,
                phone: document.getElementById('phone').value,
                email: document.getElementById('email').value,
                service: selectedService.value,
                date: document.getElementById('date').value,
                message: document.getElementById('message').value
            };
            
            // В реальном приложении здесь был бы AJAX-запрос к серверу
            alert('Спасибо за заявку! Я свяжусь с вами в ближайшее время.');
            
            // Очищаем форму
            this.reset();
            document.querySelectorAll('.service-option').forEach(opt => {
                opt.classList.remove('selected');
            });
        });
    </script>
</body>
</html>
