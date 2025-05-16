<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ELEVUM | Digitalizamos Caminos, Monetizamos Rutas</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap" rel="stylesheet">
    <script src="https://kit.fontawesome.com/7ab6c2d60c.js" crossorigin="anonymous"></script>
    <style>
        :root {
            --primary: #A762EB;
            --primary-dark: #8e40e0;
            --secondary: #232323;
            --light: #ffffff;
            --gray: #f4f4f4;
            --dark-gray: #333333;
            --success: #25D366;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
            scroll-behavior: smooth;
        }
        
        body {
            background-color: var(--light);
            color: var(--secondary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animaciones */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        @keyframes slideInLeft {
            from { 
                opacity: 0;
                transform: translateX(-100px); 
            }
            to { 
                opacity: 1;
                transform: translateX(0); 
            }
        }

        @keyframes slideInRight {
            from { 
                opacity: 0;
                transform: translateX(100px); 
            }
            to { 
                opacity: 1;
                transform: translateX(0); 
            }
        }

        .animated {
            animation-duration: 1s;
            animation-fill-mode: both;
        }

        .fadeInUp { animation-name: fadeInUp; }
        .fadeIn { animation-name: fadeIn; }
        .pulse { animation-name: pulse; }
        .slideInLeft { animation-name: slideInLeft; }
        .slideInRight { animation-name: slideInRight; }

        .delay-200 { animation-delay: 0.2s; }
        .delay-400 { animation-delay: 0.4s; }
        .delay-600 { animation-delay: 0.6s; }
        .delay-800 { animation-delay: 0.8s; }

        /* Estilos de componentes */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 2;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--primary);
            color: var(--light);
            padding: 15px 35px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            font-size: 16px;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            border: 2px solid var(--primary);
            box-shadow: 0 5px 15px rgba(167, 98, 235, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .btn::before {
            content: "";
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: 0.5s;
            pointer-events: none;
        }
        
        .btn:hover::before {
            left: 100%;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(167, 98, 235, 0.4);
            background-color: var(--primary-dark);
        }
        
        .btn-outline {
            background-color: transparent;
            color: var(--primary);
        }
        
        .btn-outline:hover {
            background-color: var(--primary);
            color: var(--light);
        }

        .btn-whatsapp {
            background-color: var(--success);
            border-color: var(--success);
        }

        .btn-whatsapp:hover {
            background-color: #1da851;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, rgba(167, 98, 235, 0.95), rgba(126, 58, 190, 0.95)), url('https://images.unsplash.com/photo-1631216244800-244ee5a78df1?q=80&w=1974&auto=format&fit=crop') center/cover no-repeat;
            min-height: 100vh;
            display: flex;
            align-items: center;
            color: var(--light);
            position: relative;
            padding: 50px 0;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 150px;
            background: linear-gradient(to bottom, transparent, var(--light));
            z-index: 1;
        }
        
        .hero-content {
            max-width: 800px;
            padding: 0 20px;
        }
        
        .hero-title {
            font-size: 3.5rem;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 20px;
            text-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .hero-subtitle {
            font-size: 1.8rem;
            font-weight: 600;
            margin-bottom: 40px;
            opacity: 0.9;
        }
        
        .hero-description {
            font-size: 1.2rem;
            margin-bottom: 50px;
            line-height: 1.8;
            opacity: 0.9;
        }

        .stats-container {
            display: flex;
            flex-wrap: wrap;
            margin-top: 50px;
            gap: 30px;
        }
        
        .stat-box {
            background-color: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 10px;
            padding: 20px;
            flex: 1;
            min-width: 180px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 1px solid rgba(255,255,255,0.2);
        }
        
        .stat-box:hover {
            transform: translateY(-5px);
            background-color: rgba(255, 255, 255, 0.15);
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .stat-text {
            font-size: 1rem;
            opacity: 0.8;
        }
        
        /* Features Section */
        .features {
            padding: 100px 0;
            background-color: var(--light);
            position: relative;
            z-index: 2;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 30px;
            color: var(--primary);
        }

        .section-subtitle {
            text-align: center;
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 60px;
            color: var(--dark-gray);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }
        
        .feature-card {
            background-color: var(--light);
            border-radius: 10px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
            border: 1px solid rgba(0,0,0,0.03);
            position: relative;
            overflow: hidden;
        }
        
        .feature-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--primary-dark));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.5s ease;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(167, 98, 235, 0.1);
        }
        
        .feature-card:hover::before {
            transform: scaleX(1);
        }
        
        .feature-icon {
            width: 80px;
            height: 80px;
            background-color: rgba(167, 98, 235, 0.1);
            border-radius: 50%;
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: var(--primary);
            transition: all 0.3s ease;
        }
        
        .feature-card:hover .feature-icon {
            background-color: var(--primary);
            color: var(--light);
            transform: rotateY(360deg);
        }
        
        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--secondary);
        }
        
        .feature-desc {
            font-size: 1rem;
            color: var(--dark-gray);
            line-height: 1.6;
        }

        /* Case Studies */
        .case-studies {
            padding: 100px 0;
            background-color: var(--gray);
            clip-path: polygon(0 5%, 100% 0, 100% 95%, 0 100%);
            margin: 50px 0;
        }

        .cases-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
        }

        .case-card {
            background-color: var(--light);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            width: 100%;
            max-width: 380px;
            transition: all 0.3s ease;
            position: relative;
        }

        .case-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .case-image {
            height: 200px;
            background-size: cover;
            background-position: center;
            position: relative;
        }

        .case-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, transparent, rgba(0,0,0,0.7));
            display: flex;
            align-items: flex-end;
            padding: 20px;
        }

        .case-logo {
            width: 80px;
            height: 80px;
            border-radius: 10px;
            background-color: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            position: absolute;
            top: 20px;
            right: 20px;
        }

        .case-logo img {
            max-width: 80%;
            max-height: 80%;
        }

        .case-company {
            color: var(--light);
            font-size: 1.8rem;
            font-weight: 700;
            text-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }

        .case-content {
            padding: 25px;
        }

        .case-title {
            font-size: 1.2rem;
            margin-bottom: 15px;
            color: var(--secondary);
            font-weight: 700;
        }

        .case-desc {
            color: var(--dark-gray);
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .case-results {
            background-color: rgba(167, 98, 235, 0.05);
            padding: 15px;
            border-left: 3px solid var(--primary);
            margin-bottom: 20px;
        }

        .results-title {
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .case-tag {
            display: inline-block;
            padding: 5px 10px;
            background-color: rgba(167, 98, 235, 0.1);
            color: var(--primary);
            border-radius: 5px;
            margin-right: 5px;
            margin-bottom: 5px;
            font-size: 0.9rem;
        }

        /* Process Section */
        .process {
            padding: 100px 0;
            background-color: var(--light);
        }

        .process-steps {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 50px;
        }

        .process-step {
            width: 100%;
            max-width: 250px;
            margin: 0 20px 40px;
            text-align: center;
            position: relative;
        }

        .process-step::after {
            content: "";
            position: absolute;
            top: 40px;
            right: -30%;
            width: 60%;
            height: 2px;
            background: linear-gradient(90deg, var(--primary), transparent);
            z-index: -1;
        }

        .process-step:last-child::after {
            display: none;
        }

        .step-number {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: var(--primary);
            color: var(--light);
            font-size: 2rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            position: relative;
            z-index: 2;
            box-shadow: 0 10px 20px rgba(167, 98, 235, 0.3);
        }

        .step-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: var(--primary);
        }

        .step-desc {
            color: var(--dark-gray);
            font-size: 0.9rem;
        }

        /* Testimonials */
        .testimonials {
            padding: 100px 0;
            background-color: var(--primary);
            color: var(--light);
            clip-path: polygon(0 0, 100% 5%, 100% 100%, 0 95%);
        }

        .testimonials .section-title {
            color: var(--light);
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .testimonial-card {
            background-color: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 10px;
            padding: 30px;
            border: 1px solid rgba(255,255,255,0.2);
            position: relative;
            transition: all 0.3s ease;
        }

        .testimonial-card:hover {
            transform: translateY(-5px);
            background-color: rgba(255, 255, 255, 0.15);
        }

        .quote-icon {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 2rem;
            opacity: 0.2;
        }

        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
            line-height: 1.8;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
        }

        .author-image {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            margin-right: 15px;
            background-size: cover;
            background-position: center;
            border: 2px solid var(--light);
        }

        .author-info h4 {
            font-weight: 700;
            margin-bottom: 5px;
        }

        .author-info p {
            opacity: 0.7;
            font-size: 0.9rem;
        }

        /* Contact Section */
        .contact {
            padding: 100px 0;
            background-color: var(--light);
            position: relative;
            z-index: 2;
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
            align-items: center;
        }

        .contact-info {
            padding: 0 20px;
        }

        .contact-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .contact-desc {
            margin-bottom: 30px;
            color: var(--dark-gray);
            line-height: 1.8;
        }

        .contact-options {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 30px;
        }

        .contact-option {
            display: flex;
            align-items: center;
        }

        .option-icon {
            width: 40px;
            height: 40px;
            background-color: rgba(167, 98, 235, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            color: var(--primary);
            font-size: 1.2rem;
        }

        .form-container {
            background-color: var(--light);
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            border: 1px solid rgba(0,0,0,0.03);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--secondary);
        }

        .form-input,
        .form-textarea,
        .form-select {
            width: 100%;
            padding: 15px;
            border: 1px solid rgba(0,0,0,0.1);
            border-radius: 5px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-input:focus,
        .form-textarea:focus,
        .form-select:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(167, 98, 235, 0.1);
        }

        .form-submit {
            width: 100%;
            padding: 15px;
            border: none;
            border-radius: 5px;
            background-color: var(--primary);
            color: var(--light);
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .form-submit:hover {
            background-color: var(--primary-dark);
            transform: translateY(-3px);
        }

        /* Footer */
        .footer {
            background-color: var(--secondary);
            color: var(--light);
            padding: 50px 0 20px;
        }

        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            margin-bottom: 30px;
        }

        .footer-column {
            flex: 1;
            min-width: 200px;
            margin-bottom: 30px;
            padding: 0 15px;
        }

        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 15px;
        }

        .footer-desc {
            opacity: 0.7;
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .footer-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-title::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background-color: var(--primary);
        }

        .footer-links {
            list-style: none;
        }

        .footer-link {
            margin-bottom: 10px;
        }

        .footer-link a {
            color: var(--light);
            text-decoration: none;
            opacity: 0.7;
            transition: all 0.3s ease;
        }

        .footer-link a:hover {
            opacity: 1;
            color: var(--primary);
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-link {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: rgba(255,255,255,0.1);
            color: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background-color: var(--primary);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            opacity: 0.7;
            font-size: 0.9rem;
        }

        /* WhatsApp Floating Button */
        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 60px;
            height: 60px;
            background-color: var(--success);
            color: var(--light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            text-decoration: none;
            box-shadow: 0 5px 15px rgba(37, 211, 102, 0.3);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .whatsapp-float:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 20px rgba(37, 211, 102, 0.4);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero-title {
                font-size: 2.5rem;
            }
            
            .hero-subtitle {
                font-size: 1.4rem;
            }
            
            .stats-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .process-step::after {
                display: none;
            }
            
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }

        @media (max-width: 480px) {
            .hero-title {
                font-size: 2rem;
            }
            
            .hero-subtitle {
                font-size: 1.2rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .btn {
                padding: 12px 25px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title animated fadeInUp">ELEVUM</h1>
                <p class="hero-subtitle animated fadeInUp delay-200">Digitalizamos Caminos, Monetizamos Rutas</p>
                <p class="hero-description animated fadeInUp delay-400">Somos fabricantes digitales de leads potenciales de alto valor para la industria del transporte. Convertimos tu presencia online en oportunidades de negocio reales con estrategias diseñadas específicamente para el sector.</p>
                <a href="#contact" class="btn animated fadeInUp delay-600">Genera Leads Calificados</a>
                
                <div class="stats-container animated fadeIn delay-800">
                    <div class="stat-box">
                        <div class="stat-number">+300</div>
                        <div class="stat-text">Leads Generados para Tractomundo</div>
                    </div>
                    <div class="stat-box">
                        <div class="stat-number">250%</div>
                        <div class="stat-text">Crecimiento en Ventas para Estraty</div>
                    </div>
                    <div class="stat-box">
                        <div class="stat-number">200%</div>
                        <div class="stat-text">Más Leads para UltraBlue</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Nuestro Motor Digital de Ventas</h2>
            <p class="section-subtitle">Combinamos estrategia, tecnología y conocimiento del sector transporte para generar leads de alto valor que se convierten en ventas reales.</p>
            
            <div class="features-grid">
                <div class="feature-card animated fadeInUp">
                    <div class="feature-icon">
                        <i class="fas fa-search"></i>
                    </div>
                    <h3 class="feature-title">Identificación de Nichos</h3>
                    <p class="feature-desc">Encontramos oportunidades desatendidas en el mercado del transporte que tu competencia no está aprovechando.</p>
                </div>
                
                <div class="feature-card animated fadeInUp delay-200">
                    <div class="feature-icon">
                        <i class="fas fa-bullseye"></i>
                    </div>
                    <h3 class="feature-title">Campañas Específicas</h3>
                    <p class="feature-desc">Desarrollamos estrategias en Meta, LinkedIn y TikTok especializadas en la industria del transporte.</p>
                </div>
                
                <div class="feature-card animated fadeInUp delay-400">
                    <div class="feature-icon">
                        <i class="fas fa-filter"></i>
                    </div>
                    <h3 class="feature-title">Calificación Inteligente</h3>
                    <p class="feature-desc">Filtramos prospects para entregarte solo leads con alto potencial de conversión y capacidad de compra real.</p>
                </div>
                
                <div class="feature-card animated fadeInUp delay-600">
                    <div class="feature-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3 class="feature-title">Análisis de Conversión</h3>
                    <p class="feature-desc">Optimizamos continuamente basados en datos reales para maximizar tu ROI y reducir el costo por lead.</p>
                </div>
                
                <div class="feature-card animated fadeInUp delay-200">
                    <div class="feature-icon">
                        <i class="fas fa-sync"></i>
                    </div>
                    <h3 class="feature-title">Seguimiento Automatizado</h3>
                    <p class="feature-desc">Implementamos sistemas que mantienen el contacto con tus leads hasta que estén listos para comprar.</p>
                </div>
                
                <div class="feature-card animated fadeInUp delay-400">
                    <div class="feature-icon">
                        <i class="fas fa-handshake"></i>
                    </div>
                    <h3 class="feature-title">Alineación con Ventas</h3>
                    <p class="feature-desc">Trabajamos directamente con tu equipo comercial para desarrollar estrategias que faciliten el cierre de ventas.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Case Studies -->
    <section class="case-studies" id="casos">
        <div class="container">
            <h2 class="section-title">Casos de Éxito</h2>
            <p class="section-subtitle">Empresas del sector transporte que han crecido exponencialmente con nuestras estrategias digitales</p>
            
            <div class="cases-container">
                <div class="case-card animated slideInLeft">
                    <div class="case-image" style="background-image: url('https://images.unsplash.com/photo-1586366461834-d2d65073f766?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80');">
                        <div class="case-overlay">
                            <h3 class="case-company">Tractomundo</h3>
                        </div>
                        <div class="case-logo">
                            <img src="https://via.placeholder.com/80x80/FFFFFF/A762EB?text=TM" alt="Tractomundo Logo">
                        </div>
                    </div>
                    <div class="case-content">
                        <h4 class="case-title">De 0 a 300+ Prospectos en 60 Días</h4>
                        <p class="case-desc">Creamos desde cero la presencia digital para esta refaccionaria y taller de tractocamiones, implementando una estrategia multicanal con énfasis en velocidad y servicio.</p>
                        <div class="case-results">
                            <h5 class="results-title">Resultados:</h5>
                            <ul>
                                <li>+300 prospectos cualificados en 2 meses</li>
                                <li>35 clientes cerrados directamente</li>
                                <li>Videos virales en redes para el sector</li>
                                <li>Posicionamiento como expertos en refacciones</li>
                            </ul>
                        </div>
                        <div class="case-tags">
                            <span class="case-tag">Meta Ads</span>
                            <span class="case-tag">TikTok</span>
                            <span class="case-tag">Contenido Técnico</span>
                            <span class="case-tag">B2B</span>
                        </div>
                    </div>
                </div>
                
                <div class="case-card animated fadeIn delay-400">
                    <div class="case-image" style="background-image: url('https://images.unsplash.com/photo-1580983415623-a6b5aa323a4e?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80');">
                        <div class="case-overlay">
                            <h3 class="case-company">GPSCARGO</h3>
                        </div>
                        <div class="case-logo">
                            <img src="https://via.placeholder.com/80x80/FFFFFF/A762EB?text=GPS" alt="GPSCARGO Logo">
                        </div>
                    </div>
                    <div class="case-content">
                        <h4 class="case-title">Identificación y Dominio de Nicho Desatendido</h4>
                        <p class="case-desc">Desarrollamos una estrategia digital completa para este proveedor de sistemas de rastreo GPS para remolques, identificando un segmento específico con alta necesidad y baja competencia.</p>
                        <div class="case-results">
                            <h5 class="results-title">Resultados:</h5>
                            <ul>
                                <li>Posicionamiento como líder en nicho especializado</li>
                                <li>Generación constante de leads de alto valor</li>
                                <li>Presencia digital optimizada con enfoque técnico</li>
                                <li>Estrategia de contenido educativo especializado</li>
                            </ul>
                        </div>
                        <div class="case-tags">
                            <span class="case-tag">LinkedIn</span>
                            <span class="case-tag">Contenido Técnico</span>
                            <span class="case-tag">SEO</span>
                            <span class="case-tag">B2B</span>
                        </div>
                    </div>
                </div>
                
                <div class="case-card animated slideInRight">
                    <div class="case-image" style="background-image: url('https://images.unsplash.com/photo-1615659127014-ae899d87e824?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80');">
                        <div class="case-overlay">
                            <h3 class="case-company">UltraBlue</h3>
                        </div>
                        <div class="case-logo">
                            <img src="https://via.placeholder.com/80x80/FFFFFF/A762EB?text=UB" alt="UltraBlue Logo">
                        </div>
                    </div>
                    <div class="case-content">
                        <h4 class="case-title">200% Más Leads Cualificados</h4>
                        <p class="case-desc">Implementamos estrategias digitales para este fabricante de AdBlue (urea automotriz) enfocadas en aumentar reconocimiento de marca y generar leads con intención de compra real.</p>
                        <div class="case-results">
                            <h5 class="results-title">Resultados:</h5>
                            <ul>
                                <li>Aumento del 200% en leads generados</li>
                                <li>Posicionamiento como referente de calidad en AdBlue</li>
                                <li>Desarrollo de contenido educativo sobre normativas</li>
                                <li>Nuevos canales de distribución identificados</li>
                            </ul>
                        </div>
                        <div class="case-tags">
                            <span class="case-tag">Meta Ads</span>
                            <span class="case-tag">LinkedIn</span>
                            <span class="case-tag">Contenido Técnico</span>
                            <span class="case-tag">B2B</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Process Section -->
    <section class="process" id="proceso">
        <div class="container">
            <h2 class="section-title">Nuestro Proceso</h2>
            <p class="section-subtitle">Metodología probada para transformar estrategias digitales en leads de alta calidad para la industria del transporte</p>
            
            <div class="process-steps">
                <div class="process-step animated fadeInUp">
                    <div class="step-number">1</div>
                    <h3 class="step-title">Diagnóstico Industrial</h3>
                    <p class="step-desc">Analizamos tu negocio, competencia y oportunidades específicas en el sector transporte</p>
                </div>
                
                <div class="process-step animated fadeInUp delay-200">
                    <div class="step-number">2</div>
                    <h3 class="step-title">Estrategia Digital</h3>
                    <p class="step-desc">Diseñamos un plan personalizado para captar leads cualificados usando los canales óptimos</p>
                </div>
                
                <div class="process-step animated fadeInUp delay-400">
                    <div class="step-number">3</div>
                    <h3 class="step-title">Implementación</h3>
                    <p class="step-desc">Ejecutamos campañas en Meta, LinkedIn y TikTok con mensajes técnicos precisos</p>
                </div>
                
                <div class="process-step animated fadeInUp delay-600">
                    <div class="step-number">4</div>
                    <h3 class="step-title">Optimización</h3>
                    <p class="step-desc">Mejoramos continuamente basados en datos para maximizar resultados</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="testimonials" id="testimonios">
        <div class="container">
            <h2 class="section-title">Lo Que Dicen Nuestros Clientes</h2>
            
            <div class="testimonials-grid">
                <div class="testimonial-card animated fadeIn">
                    <i class="fas fa-quote-right quote-icon"></i>
                    <p class="testimonial-text">"Gracias a ELEVUM multiplicamos nuestras ventas en menos de dos meses. Su entendimiento técnico del sector transporte hace la diferencia, no son una agencia de marketing común."</p>
                    <div class="testimonial-author">
                        <div class="author-image" style="background-image: url('https://randomuser.me/api/portraits/men/45.jpg');"></div>
                        <div class="author-info">
                            <h4>Carlos Méndez</h4>
                            <p>Director Comercial, Tractomundo</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card animated fadeIn delay-200">
                    <i class="fas fa-quote-right quote-icon"></i>
                    <p class="testimonial-text">"Identificaron un nicho de mercado que nadie había visto. Su enfoque en leads cualificados nos permitió optimizar nuestra inversión en marketing significativamente."</p>
                    <div class="testimonial-author">
                        <div class="author-image" style="background-image: url('https://randomuser.me/api/portraits/women/32.jpg');"></div>
                        <div class="author-info">
                            <h4>Laura Gutiérrez</h4>
                            <p>CEO, GPSCARGO</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card animated fadeIn delay-400">
                    <i class="fas fa-quote-right quote-icon"></i>
                    <p class="testimonial-text">"La calidad de los leads es impresionante. No solo aumentó la cantidad sino que realmente están interesados en nuestros productos. El 200% de incremento habla por sí solo."</p>
                    <div class="testimonial-author">
                        <div class="author-image" style="background-image: url('https://randomuser.me/api/portraits/men/32.jpg');"></div>
                        <div class="author-info">
                            <h4>Miguel Sánchez</h4>
                            <p>Director de Marketing, UltraBlue</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="container">
            <h2 class="section-title">Hablemos de tu Negocio</h2>
            <p class="section-subtitle">Descubre cómo podemos ayudarte a generar leads de alto potencial para tu empresa en el sector transporte</p>
            
            <div class="contact-container">
                <div class="contact-info animated fadeInUp">
                    <h3 class="contact-title">¿Por qué trabajar con nosotros?</h3>
                    <p class="contact-desc">Como ingeniero químico con MBA, tengo un entendimiento único del sector industrial y combino este conocimiento con estrategias digitales de alto impacto para generar leads calificados que realmente entienden el valor de tu oferta.</p>
                    
                    <div class="contact-options">
                        <div class="contact-option">
                            <div class="option-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <span>info@elevum.mx</span>
                        </div>
                        
                        <div class="contact-option">
                            <div class="option-icon">
                                <i class="fas fa-phone-alt"></i>
                            </div>
                            <span>+52 (81) 1234 5678</span>
                        </div>
                        
                        <div class="contact-option">
                            <div class="option-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <span>Monterrey, Nuevo León, México</span>
                        </div>
                    </div>
                    
                    <a href="https://wa.me/52812345678?text=Hola,%20me%20interesa%20generar%20leads%20para%20mi%20empresa%20en%20el%20sector%20transporte" class="btn btn-whatsapp">
                        <i class="fab fa-whatsapp"></i> Contáctame por WhatsApp
                    </a>
                </div>
                
                <div class="form-container animated fadeInUp">
                    <form id="leadForm" action="https://formspree.io/f/tu_email@ejemplo.com" method="POST">
                        <div class="form-group">
                            <label class="form-label" for="name">Nombre</label>
                            <input type="text" id="name" name="name" class="form-input" required>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label" for="email">Email</label>
                            <input type="email" id="email" name="email" class="form-input" required>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label" for="phone">Teléfono</label>
                            <input type="tel" id="phone" name="phone" class="form-input">
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label" for="company">Empresa</label>
                            <input type="text" id="company" name="company" class="form-input">
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label" for="industry">¿A qué te dedicas?</label>
                            <select id="industry" name="industry" class="form-select">
                                <option value="">Selecciona...</option>
                                <option value="transporte">Empresa de Transporte</option>
                                <option value="refacciones">Refaccionaria/Autopartes</option>
                                <option value="servicios">Servicios para Transportes</option>
                                <option value="tecnologia">Tecnología para Transporte</option>
                                <option value="fabricante">Fabricante de Equipos</option>
                                <option value="otro">Otro</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label" for="message">¿Cómo puedo ayudarte?</label>
                            <textarea id="message" name="message" class="form-textarea" rows="4" required></textarea>
                        </div>
                        
                        <button type="submit" class="form-submit">
                            <i class="fas fa-paper-plane"></i> Enviar Mensaje
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <div class="footer-logo">ELEVUM</div>
                    <p class="footer-desc">Fabricante digital de leads potenciales para la industria del transporte. Digitalizamos caminos, monetizamos rutas.</p>
                    
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-tiktok"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3 class="footer-title">Enlaces Rápidos</h3>
                    <ul class="footer-links">
                        <li class="footer-link"><a href="#features">Servicios</a></li>
                        <li class="footer-link"><a href="#casos">Casos de Éxito</a></li>
                        <li class="footer-link"><a href="#proceso">Proceso</a></li>
                        <li class="footer-link"><a href="#testimonios">Testimonios</a></li>
                        <li class="footer-link"><a href="#contact">Contacto</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3 class="footer-title">Industrias</h3>
                    <ul class="footer-links">
                        <li class="footer-link"><a href="#">Transportes</a></li>
                        <li class="footer-link"><a href="#">Refacciones</a></li>
                        <li class="footer-link"><a href="#">Insumos Automotrices</a></li>
                        <li class="footer-link"><a href="#">Sistemas GPS</a></li>
                        <li class="footer-link"><a href="#">Mantenimiento</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3 class="footer-title">Contacto</h3>
                    <ul class="footer-links">
                        <li class="footer-link"><i class="fas fa-envelope"></i> info@elevum.mx</li>
                        <li class="footer-link"><i class="fas fa-phone"></i> +52 (81) 1234 5678</li>
                        <li class="footer-link"><i class="fas fa-map-marker-alt"></i> Monterrey, Nuevo León, México</li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2025 ELEVUM. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <!-- WhatsApp Floating Button -->
    <a href="https://wa.me/52812345678?text=Hola,%20me%20interesa%20generar%20leads%20para%20mi%20empresa%20en%20el%20sector%20transporte" class="whatsapp-float">
        <i class="fab fa-whatsapp"></i>
    </a>

    <!-- Animation Script -->
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Animate elements when they come into view
            const animatedElements = document.querySelectorAll('.animated');
            
            function checkInView() {
                animatedElements.forEach(element => {
                    const rect = element.getBoundingClientRect();
                    const windowHeight = window.innerHeight || document.documentElement.clientHeight;
                    
                    if (rect.top <= windowHeight * 0.85 && rect.bottom >= 0) {
                        element.style.visibility = 'visible';
                    }
                });
            }
            
            // Set initial visibility
            animatedElements.forEach(element => {
                element.style.visibility = 'hidden';
            });
            
            // Check elements on load
            checkInView();
            
            // Check elements on scroll
            window.addEventListener('scroll', checkInView);
            
            // Form submission
            const form = document.getElementById('leadForm');
            if (form) {
                form.addEventListener('submit', function(e) {
                    // Replace with your form handling logic
                    // For now, we'll just show an alert
                    // e.preventDefault();
                    // alert('¡Gracias por tu mensaje! Nos pondremos en contacto contigo pronto.');
                });
            }
        });
    </script>
</body>
</html>
