<!DOCTYPE html>
<html lang="sw">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nayom - Ubunifu wa Vifaa wa Kioo</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #f0f4f8 0%, #e6eef7 100%);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(10px);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(44, 90, 160, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #2c5aa0;
            display: flex;
            align-items: center;
        }

        .logo::before {
            content: "🔷";
            margin-right: 10px;
            font-size: 2rem;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #2c5aa0;
            font-weight: 600;
            transition: all 0.3s ease;
            padding: 8px 15px;
            border-radius: 30px;
        }

        .nav-links a:hover {
            background-color: rgba(44, 90, 160, 0.1);
            color: #1e3d6f;
        }

        .hero {
            background: linear-gradient(135deg, rgba(44, 90, 160, 0.9) 0%, rgba(100, 149, 237, 0.85) 100%);
            color: white;
            padding: 120px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 C50,0 50,100 100,100 L100,0 Z" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: 100% 100%;
            opacity: 0.3;
            z-index: 0;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease;
            position: relative;
            z-index: 1;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease 0.3s;
            animation-fill-mode: both;
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-button {
            display: inline-block;
            background-color: white;
            color: #2c5aa0;
            padding: 15px 40px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease 0.6s;
            animation-fill-mode: both;
            position: relative;
            z-index: 1;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            border: 2px solid rgba(44, 90, 160, 0.2);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
            background-color: #f0f7ff;
        }

        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.8rem;
            color: #2c5aa0;
            margin-bottom: 60px;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: "";
            display: block;
            width: 70%;
            height: 4px;
            background: linear-gradient(to right, #2c5aa0, #6495ed);
            margin: 15px auto 0;
            border-radius: 2px;
        }

        .about {
            background-color: #f8fbff;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(5px);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            border: 1px solid rgba(44, 90, 160, 0.1);
        }

        .about-text h3 {
            color: #2c5aa0;
            margin-bottom: 20px;
            font-size: 1.8rem;
            position: relative;
            padding-bottom: 10px;
        }

        .about-text h3::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 3px;
            background: #2c5aa0;
            border-radius: 2px;
        }

        .about-image {
            background: linear-gradient(135deg, #2c5aa0 0%, #6495ed 100%);
            height: 400px;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 4rem;
            box-shadow: 0 8px 30px rgba(44, 90, 160, 0.25);
            position: relative;
            overflow: hidden;
        }

        .about-image::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            right: -50%;
            bottom: -50%;
            background: linear-gradient(
                45deg,
                transparent 33%,
                rgba(255, 255, 255, 0.1) 50%,
                transparent 66%
            );
            transform: rotate(45deg);
            animation: shine 3s linear infinite;
            z-index: 1;
        }

        .services {
            background-color: white;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }

        .service-card {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(5px);
            padding: 40px 30px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.4s ease;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.08);
            border: 1px solid rgba(44, 90, 160, 0.1);
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(to right, #2c5aa0, #6495ed);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 35px rgba(44, 90, 160, 0.2);
        }

        .service-icon {
            font-size: 3.5rem;
            margin-bottom: 25px;
            background: linear-gradient(135deg, #2c5aa0, #6495ed);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .service-card h3 {
            color: #2c5aa0;
            margin-bottom: 20px;
            font-size: 1.5rem;
        }

        .contact {
            background: linear-gradient(135deg, #e6eef7 0%, #d4e4ff 100%);
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }

        .contact-info {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(5px);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            border: 1px solid rgba(44, 90, 160, 0.1);
        }

        .contact-item {
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            padding: 15px;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.5);
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            background: rgba(255, 255, 255, 0.8);
            transform: translateX(5px);
        }

        .contact-item span {
            font-size: 1.5rem;
            margin-right: 15px;
            background: linear-gradient(135deg, #2c5aa0, #6495ed);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .contact-item h4 {
            color: #2c5aa0;
            margin-bottom: 5px;
        }

        .contact-item p, .contact-item a {
            color: #333;
            text-decoration: none;
        }

        .contact-item a:hover {
            color: #2c5aa0;
            text-decoration: underline;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 30px;
            justify-content: center;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 55px;
            height: 55px;
            background: linear-gradient(135deg, #2c5aa0, #6495ed);
            color: white;
            font-size: 1.8rem;
            border-radius: 50%;
            transition: all 0.3s ease;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(44, 90, 160, 0.3);
        }

        .social-links a:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 8px 20px rgba(44, 90, 160, 0.4);
        }

        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: linear-gradient(135deg, #25D366, #128C7E);
            color: white;
            width: 65px;
            height: 65px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.2rem;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
            transition: all 0.4s ease;
            z-index: 1000;
            text-decoration: none;
            border: 2px solid white;
        }

        .whatsapp-float:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.4);
        }

        footer {
            background: linear-gradient(135deg, #1e3d6f 0%, #2c5aa0 100%);
            color: white;
            text-align: center;
            padding: 40px 0;
            position: relative;
        }

        footer::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(to right, #6495ed, #2c5aa0);
        }

        footer p {
            margin: 10px 0;
            position: relative;
            z-index: 1;
        }

        footer p:first-child {
            font-size: 1.2rem;
            font-weight: 600;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes shine {
            0% {
                transform: rotate(45deg) translateY(-100%);
            }
            100% {
                transform: rotate(45deg) translateY(100%);
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                flex-direction: column;
                gap: 10px;
                background: rgba(255, 255, 255, 0.95);
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                padding: 20px;
                box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
                border-top: 1px solid rgba(44, 90, 160, 0.1);
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
            }
            
            .social-links {
                flex-wrap: wrap;
            }
            
            .section-title {
                font-size: 2.3rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <div class="logo">Nayom Glass Design</div>
            <ul class="nav-links">
                <li><a href="#home">Nyumbani</a></li>
                <li><a href="#about">Kuhusu</a></li>
                <li><a href="#services">Huduma</a></li>
                <li><a href="#contact">Mawasiliano</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="container">
            <h1>Karibu Nayom Glass Design</h1>
            <p>Ubunifu wa kipekee wa vifaa kwa kutumia glass material</p>
            <a href="#contact" class="cta-button">Wasiliana Nasi</a>
        </div>
    </section>

    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">Kuhusu Sisi</h2>
            <div class="about-content">
                <div class="about-text">
                    <h3>Nayom Glass Design</h3>
                    <p>Jina langu ni <strong>Khunnaina Mussa</strong> kutoka Zanzibar. Ninayefuga kampuni ya <strong>Nayom</strong> ambayo hujishughulisha na ubunifu wa vifaa mbalimbali kwa kutumia glass material.</p>
                    <p>Tunatoa suluhisho za kipekee za ubora wa hali ya juu za vifaa vya glass ambavyo vinavutia na kuwa na manufaa kwenye nyumba na ofisi zako.</p>
                    <p>Uzoefu wetu na maarifa katika fani ya glass design hutufanya wabunifu wazuri katika kazi yetu.</p>
                </div>
                <div class="about-image">
                    <div>🔷</div>
                </div>
            </div>
        </div>
    </section>

    <section id="services" class="services">
        <div class="container">
            <h2 class="section-title">Huduma Zetu</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">🪟</div>
                    <h3>Ubunifu wa Dirisha</h3>
                    <p>Dirisha za kipekee za glass zenye mvuto na ubora wa hali ya juu kwa nyumba na ofisi zako.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🚪</div>
                    <h3>Milango ya Glass</h3>
                    <p>Milango ya kipekee ya glass yanayotoa muonekano wa kisasa na uvivu.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🪞</div>
                    <h3>Vioo vya MAPambo</h3>
                    <p>Vioo vya kimapambo viliyoboresha muonekano wa nyumba yako.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🍷</div>
                    <h3>Vifaa vya Glass</h3>
                    <p>Vifaa mbalimbali vya glass vya kila siku vilivyoboreshwa kwa kiwango cha juu.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🏠</div>
                    <h3>Ufungaji wa Glass</h3>
                    <p>Ufungaji wa kitaaluma wa vifaa vyote vya glass kwenye eneo lako.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">✨</div>
                    <h3>Ukarimu wa Vifaa</h3>
                    <p>Tunakarimia vifaa vya glass vilivyovunjika au kuhitaji matengenezo.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Wasiliana Nasi</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <div class="contact-item">
                        <span>📞</span>
                        <div>
                            <h4>Simu</h4>
                            <a href="tel:+255755765946">0755 765 946</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>📱</span>
                        <div>
                            4>WhatsApp</h4>
                            <a href="https://wa.me/255755765946" target="_blank">0755 765 946</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>✉️</span>
                        <div>
                            <h4>Email</h4>
                            <a href="mailto:khunnainayussuf@gmail.com">khunnainayussuf@gmail.com</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>📍</span>
                        <div>
                            <h4>Mahali</h4>
                            <p>Zanzibar, Tanzania</p>
                        </div>
                    </div>
                    <div class="social-links">
                        <a href="https://instagram.com/Nnaynah_08" target="_blank" title="Instagram">
                            📸
                        </a>
                        <a href="https://youtube.com/@Nnaynah_08" target="_blank" title="YouTube">
                            ▶️
                        </a>
                        <a href="https://tiktok.com/@Nnayna" target="_blank" title="TikTok">
                            🎵
                        </a>
                    </div>
                </div>
                <div class="contact-info">
                    <h3 style="color: #2c5aa0; margin-bottom: 20px;">Sisi Tupo Hapa Kukusaidia</h3>
                    <p>Tupo tayari kujibu maswali yako yote kuhusu ubunifu wa vifaa kwa kutumia glass material. Wasiliana nasi kupitia njia yoyote uliyopenda.</p>
                    <p style="margin-top: 20px;">Tunafanya kazi siku zote za wiki na tunajibu maswali haraka iwezekanavyo.</p>
                    <div style="margin-top: 30px; text-align: center;">
                        <div style="font-size: 4rem;">🔷</div>
                        <p style="font-weight: bold; color: #2c5aa0; margin-top: 10px;">Nayom Glass Design</p>
                        <p style="color: #666;">Khunnaina Mussa - Mwenye Kampuni</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2025 Nayom Glass Design. Haki zote zimehifadhiwa.</p>
            <p>Imetengenezwa na Khunnaina Mussa - Zanzibar</p>
        </div>
    </footer>

    <a href="https://wa.me/255755765946" class="whatsapp-float" target="_blank" title="Chat WhatsApp">
        💬
    </a>
</body>
</html>
