<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>Happy Island | Летняя кофейня у моря</title>
  <!-- Google Fonts + Font Awesome 6 -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: linear-gradient(145deg, #FFF8F0 0%, #FFEFE0 100%);
      color: #1E2F2F;
      scroll-behavior: smooth;
    }

    h1, h2, h3, .logo, .nav-links a {
      font-family: 'Quicksand', sans-serif;
      font-weight: 700;
    }

    .container {
      max-width: 1250px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* ---------- Пляжный фон с волнами ---------- */
    .beach-bg {
      position: relative;
      background: linear-gradient(125deg, #FEE2B5 0%, #FFD8A9 100%);
      overflow-x: hidden;
    }

    /* волны сверху */
    .wave-top {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      line-height: 0;
      transform: rotate(180deg);
    }
    .wave-top svg {
      position: relative;
      display: block;
      width: calc(100% + 1.3px);
      height: 70px;
    }

    /* песок внизу */
    .sand-footer {
      background: #F7E5C2;
      position: relative;
    }

    /* Header (стеклянный эффект) */
    header {
      background: rgba(255, 248, 235, 0.92);
      backdrop-filter: blur(12px);
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
      position: sticky;
      top: 0;
      z-index: 100;
      border-bottom: 2px solid rgba(255, 215, 150, 0.6);
    }

    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 16px 0;
      flex-wrap: wrap;
      gap: 15px;
    }

    .logo {
      font-size: 2rem;
      background: linear-gradient(135deg, #FF8C42, #D45A1E);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.5px;
    }
    .logo i {
      color: #F7B05E;
      font-size: 1.9rem;
      margin-right: 6px;
      background: none;
      -webkit-background-clip: unset;
      color: #E76F2D;
    }

    .nav-links {
      display: flex;
      gap: 28px;
      list-style: none;
    }
    .nav-links a {
      text-decoration: none;
      font-weight: 600;
      color: #3D5A5A;
      transition: 0.2s;
      font-size: 1rem;
    }
    .nav-links a:hover {
      color: #FF7E3A;
      border-bottom: 2px solid #FFAA66;
      padding-bottom: 4px;
    }

    /* Герой с морем */
    .hero-summer {
      padding: 60px 0 70px;
      background: radial-gradient(circle at 10% 30%, rgba(255,226,170,0.5), rgba(253,205,130,0.3));
    }
    .hero-flex {
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      gap: 40px;
    }
    .hero-text {
      flex: 1;
    }
    .hero-badge {
      background: #FFE2B0;
      display: inline-block;
      padding: 6px 18px;
      border-radius: 60px;
      font-size: 0.85rem;
      font-weight: 700;
      color: #C9551A;
      margin-bottom: 20px;
    }
    .hero-text h1 {
      font-size: 3.5rem;
      color: #005A5C;
      line-height: 1.2;
    }
    .hero-text h1 span {
      color: #F16A2B;
    }
    .beach-address {
      background: white;
      border-radius: 48px;
      padding: 12px 20px;
      display: inline-flex;
      align-items: center;
      gap: 12px;
      margin: 20px 0 24px;
      box-shadow: 0 8px 16px rgba(0,0,0,0.05);
    }
    .beach-address i {
      color: #FF7A2F;
      font-size: 1.3rem;
    }
    .btn-group {
      margin-top: 12px;
    }
    .btn {
      display: inline-block;
      background: #FF7A2F;
      color: white;
      padding: 12px 28px;
      border-radius: 50px;
      text-decoration: none;
      font-weight: 700;
      transition: 0.25s;
      box-shadow: 0 6px 14px rgba(0,0,0,0.1);
      border: none;
    }
    .btn-outline {
      background: transparent;
      border: 2px solid #FF7A2F;
      color: #FF7A2F;
      margin-left: 16px;
    }
    .btn-outline:hover {
      background: #FF7A2F;
      color: white;
    }
    .btn:hover {
      transform: translateY(-3px);
      background: #D85F1C;
    }
    .hero-image {
      flex: 1;
      text-align: center;
    }
    .hero-image img {
      max-width: 100%;
      border-radius: 56px;
      box-shadow: 0 30px 35px -15px rgba(0,0,0,0.2);
      width: 100%;
      max-width: 460px;
    }

    /* Секции общие */
    section {
      padding: 75px 0;
    }
    .section-title {
      text-align: center;
      font-size: 2.5rem;
      margin-bottom: 16px;
      color: #236B6B;
    }
    .section-sub {
      text-align: center;
      color: #7C5D3E;
      max-width: 680px;
      margin: 0 auto 45px auto;
    }

    /* Меню (пляжное меню от пользователя) */
    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 35px;
    }
    .menu-card {
      background: rgba(255, 255, 245, 0.95);
      border-radius: 36px;
      overflow: hidden;
      transition: all 0.25s;
      box-shadow: 0 15px 25px -12px rgba(0,0,0,0.1);
      border: 1px solid #FDE2BE;
      backdrop-filter: blur(2px);
    }
    .menu-card:hover {
      transform: translateY(-8px);
    }
    .menu-img {
      height: 180px;
      background-size: cover;
      background-position: center;
    }
    .menu-info {
      padding: 20px 20px 26px;
    }
    .menu-info h3 {
      font-size: 1.5rem;
      font-weight: 700;
      color: #3E5C3A;
    }
    .menu-desc {
      color: #8B6948;
      margin: 8px 0;
      font-size: 0.9rem;
    }
    .price {
      font-weight: 800;
      font-size: 1.4rem;
      color: #E26D2C;
      margin-top: 12px;
    }

    /* Пляжные фишки */
    .beach-features {
      background: linear-gradient(115deg, #FEEBC8, #FFE2B5);
    }
    .feat-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 28px;
      justify-content: center;
    }
    .feat-item {
      background: rgba(255, 250, 235, 0.9);
      backdrop-filter: blur(4px);
      padding: 28px 24px;
      border-radius: 48px;
      text-align: center;
      flex: 1;
      min-width: 200px;
      border: 1px solid #FFDCAE;
    }
    .feat-item i {
      font-size: 2.5rem;
      color: #F37B30;
      margin-bottom: 18px;
    }

    /* отзывы */
    .reviews {
      background: #FFF6EA;
    }
    .review-cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
    }
    .review-card {
      background: white;
      border-radius: 36px;
      padding: 28px;
      box-shadow: 0 10px 18px rgba(0,0,0,0.04);
    }
    .stars {
      color: #FFB347;
      letter-spacing: 3px;
      margin-bottom: 14px;
    }
    .review-text {
      font-style: italic;
      margin: 16px 0;
      color: #4B3A2A;
    }
    .review-author {
      font-weight: 700;
      color: #E36C29;
    }

    /* Контакты + геопозиция */
    .contact-summer {
      background: #FAF0E1;
    }
    .contact-flex {
      display: flex;
      flex-wrap: wrap;
      gap: 45px;
      align-items: flex-start;
    }
    .contact-details {
      flex: 1.2;
    }
    .contact-details p {
      margin: 24px 0;
      display: flex;
      align-items: center;
      gap: 18px;
      font-size: 1.05rem;
      background: rgba(255,255,240,0.7);
      padding: 12px 20px;
      border-radius: 60px;
    }
    .contact-details i {
      width: 32px;
      color: #F36F2E;
      font-size: 1.4rem;
    }
    .map-geo {
      flex: 1;
      background: #C8DCC8;
      border-radius: 48px;
      height: 300px;
      background-image: url('https://placehold.co/600x400/CCDDBB/D58648?text=🗺️+Люблинская+76к2+на+карте');
      background-size: cover;
      background-position: center;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      padding-bottom: 20px;
      box-shadow: 0 12px 24px rgba(0,0,0,0.1);
    }
    .geo-badge {
      background: rgba(0,0,0,0.6);
      backdrop-filter: blur(8px);
      border-radius: 48px;
      padding: 8px 22px;
      color: white;
      font-weight: 500;
    }

    .tg-link {
      background: #e9f3e6;
      border-radius: 60px;
      transition: 0.2s;
    }
    .tg-link a {
      text-decoration: none;
      color: #2B734B;
      font-weight: 600;
      margin-left: 8px;
    }

    footer {
      background: #1F3E3E;
      color: #FFE6C7;
      text-align: center;
      padding: 32px 0;
    }
    .footer-icons a {
      color: #FFD9A5;
      margin: 0 12px;
      font-size: 1.6rem;
      transition: 0.2s;
    }
    .footer-icons a:hover {
      color: #FFA559;
    }

    @media (max-width: 800px) {
      .navbar {
        flex-direction: column;
      }
      .hero-text h1 {
        font-size: 2.5rem;
      }
      .btn-outline {
        margin-left: 0;
        margin-top: 12px;
      }
      .section-title {
        font-size: 2rem;
      }
    }
  </style>
</head>
<body>
<div class="beach-bg">
  <!-- Декоративные волны сверху (стилизация) -->
  <div class="wave-top">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 120"><path fill="#FFE8BF" fill-opacity="0.5" d="M0,64L80,69.3C160,75,320,85,480,80C640,75,800,53,960,48C1120,43,1280,53,1360,58.7L1440,64L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"></path></svg>
  </div>

  <header>
    <div class="container">
      <div class="navbar">
        <div class="logo"><i class="fas fa-umbrella-beach"></i> Happy Island</div>
        <ul class="nav-links">
          <li><a href="#home">Пляж</a></li>
          <li><a href="#menu">Меню</a></li>
          <li><a href="#reviews">Отзывы</a></li>
          <li><a href="#contacts">Контакты</a></li>
        </ul>
      </div>
    </div>
  </header>

  <main>
    <!-- Главная секция море/пляж -->
    <section id="home" class="hero-summer">
      <div class="container">
        <div class="hero-flex">
          <div class="hero-text">
            <div class="hero-badge"><i class="fas fa-sun"></i> Лето + кофе = счастье</div>
            <h1>Happy Island <br><span>Кофе у моря</span></h1>
            <div class="beach-address">
              <i class="fas fa-location-dot"></i> <strong>Люблинская улица, 76, корпус 2</strong>
            </div>
            <p>Шезлонги, коктейли, прохладный бриз и лучший кофе в городе. Твой пляжный отдых без выезда из Москвы.</p>
            <div class="btn-group">
              <a href="#menu" class="btn"><i class="fas fa-mug-hot"></i> Смотреть меню</a>
              <a href="https://t.me/HappyIsland_76" target="_blank" class="btn btn-outline"><i class="fab fa-telegram"></i> Telegram канал</a>
            </div>
          </div>
          <div class="hero-image">
            <img src="https://placehold.co/500x500/FEE0B0/E57A30?text=🌊+Море+и+кофе+🌴" alt="Пляж и кофе">
          </div>
        </div>
      </div>
    </section>

    <!-- Меню (то, которое вы прислали, летние позиции) -->
    <section id="menu">
      <div class="container">
        <h2 class="section-title">🏝️ Пляжное меню</h2>
        <div class="section-sub">Свежесть океана, тропические ноты и любимые напитки</div>
        <div class="menu-grid">
          <!-- Карточки меню с пляжным вайбом -->
          <div class="menu-card">
            <div class="menu-img" style="background-image: url('https://placehold.co/500x350/EEDDC5/DD7835?text=Кокосовый+латте');"></div>
            <div class="menu-info">
              <h3>Кокосовый латте</h3>
              <div class="menu-desc">Нежный кофе с кокосовым молоком и сиропом, пенка с кокосовой стружкой.</div>
              <div class="price">320 ₽</div>
            </div>
          </div>
          <div class="menu-card">
            <div class="menu-img" style="background-image: url('https://placehold.co/500x350/EEDDC5/DD7835?text=Манго-маракуйя');"></div>
            <div class="menu-info">
              <h3>Манго-маракуйя лимонад</h3>
              <div class="menu-desc">Тропический взрыв со льдом, базиликом и кусочками маракуйи.</div>
              <div class="price">280 ₽</div>
            </div>
          </div>
          <div class="menu-card">
            <div class="menu-img" style="background-image: url('https://placehold.co/500x350/EEDDC5/DD7835?text=Вафли+Баунти');"></div>
            <div class="menu-info">
              <h3>Вафли "Райский остров"</h3>
              <div class="menu-desc">Хрустящие вафли, кокосовая стружка, белый шоколад, шарик пломбира.</div>
              <div class="price">390 ₽</div>
            </div>
          </div>
          <div class="menu-card">
            <div class="menu-img" style="background-image: url('https://placehold.co/500x350/EEDDC5/DD7835?text=Фисташковый+раф');"></div>
            <div class="menu-info">
              <h3>Фисташковый раф</h3>
              <div class="menu-desc">Шелковистый, соленая фисташка, нежная пенка, корица по желанию.</div>
              <div class="price">340 ₽</div>
            </div>
          </div>
          <div class="menu-card">
            <div class="menu-img" style="background-image: url('https://placehold.co/500x350/EEDDC5/DD7835?text=Ананасовый+смузи');"></div>
            <div class="menu-info">
              <h3>Ананасовый рай</h3>
              <div class="menu-desc">Освежающий смузи с ананасом, мятой и кокосовым молоком.</div>
              <div class="price">310 ₽</div>
            </div>
          </div>
          <div class="menu-card">
            <div class="menu-img" style="background-image: url('https://placehold.co/500x350/EEDDC5/DD7835?text=Айс+кофе+карамель');"></div>
            <div class="menu-info">
              <h3>Айс-карамель латте</h3>
              <div class="menu-desc">Ледяной кофе с соленой карамелью и взбитыми сливками.</div>
              <div class="price">290 ₽</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Пляжные преимущества -->
    <section class="beach-features">
      <div class="container">
        <div class="feat-grid">
          <div class="feat-item"><i class="fas fa-ice-cream"></i><h4>Фруктовый лед</h4><p>Домашние сорбеты и фреши</p></div>
          <div class="feat-item"><i class="fas fa-umbrella-beach"></i><h4>Зона лежаков</h4><p>Настоящий пляжный декор, шезлонги и зонтики</p></div>
          <div class="feat-item"><i class="fas fa-water"></i><h4>Морской бриз</h4><p>Кондиционеры и увлажнители с ароматом океана</p></div>
        </div>
      </div>
    </section>

    <!-- Отзывы -->
    <section id="reviews" class="reviews">
      <div class="container">
        <h2 class="section-title">🏄‍♂️ Гости о Happy Island</h2>
        <div class="section-sub">Окунитесь в атмосферу, которую любят сотни гостей</div>
        <div class="review-cards">
          <div class="review-card"><div class="stars">★★★★★</div><div class="review-text">"Кокосовый латте и атмосфера – как будто я на Бали! Спасибо за классное лето. Адрес супер, Люблинская 76к2 — теперь моё любимое место!"</div><div class="review-author">— Анна, соседка</div></div>
          <div class="review-card"><div class="stars">★★★★★</div><div class="review-text">"Ребята, вы лучшие! Ананасовый смузи спасает в жару, лежаки во дворе, диджеи. Телеграм-канал 🔥 HappyIsland_76, подписывайтесь."</div><div class="review-author">— Максим</div></div>
          <div class="review-card"><div class="stars">★★★★☆</div><div class="review-text">"Шикарное место для завтраков. Вафли — сказка. Единственный минус – всегда много людей, но это показатель качества."</div><div class="review-author">— Елена</div></div>
        </div>
      </div>
    </section>

    <!-- Контакты, геолокация, телеграм, время работы -->
    <section id="contacts" class="contact-summer">
      <div class="container">
        <h2 class="section-title">🧭 Твой остров на карте</h2>
        <div class="section-sub">Приходи к нам, мы всегда рады волне хорошего настроения</div>
        <div class="contact-flex">
          <div class="contact-details">
            <p><i class="fas fa-map-pin"></i> <strong>Люблинская ул., 76, корпус 2</strong> </p>
            <p><i class="fas fa-clock"></i> <strong>Время работы:</strong> 8:30 — 21:00 (ежедневно)</p>
            <p><i class="fas fa-phone-alt"></i> <strong>+7 977 715-49-03</strong> </p>
            <p class="tg-link"><i class="fab fa-telegram"></i> <strong>Telegram канал:</strong> <a href="https://t.me/HappyIsland_76" target="_blank">@HappyIsland_76</a> — </p>
            <p><i class="fas fa-location-dot"></i> <strong>Геопозиция:</strong> 55.6832° N, 37.7355° E (Рядом с метро Люблино)</p>
          </div>
          <div class="map-geo">
            <div class="geo-badge"><i class="fas fa-map-marker-alt"></i> ул. Люблинская 76к2</div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <div class="footer-icons">
        <a href="https://t.me/HappyIsland_76" target="_blank"><i class="fab fa-telegram"></i></a>
        <a href="#"><i class="fab fa-instagram"></i></a>
        <a href="#"><i class="fab fa-vk"></i></a>
      </div>
      <p style="margin-top: 18px;">🌴 Happy Island — пляжная кофейня на Люблинской 76к2, 8:30-21:00. Твой отдых без билетов на море.</p>
      <p style="margin-top: 12px; font-size: 0.85rem;">☎️ +7 977 715-49-03 | подписывайся на Telegram-канал</p>
    </div>
  </footer>
</div>
</body>
</html>
