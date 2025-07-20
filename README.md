# cub1ts-website
Sitio web oficial del canal cub1ts
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>cub1ts - Canal de Tecnología</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: white;
            overflow-x: hidden;
        }

        /* Partículas de fondo */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }

        .particle {
            position: absolute;
            background: #00ffff;
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.3; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 0.8; }
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 2rem;
            border-bottom: 1px solid rgba(0, 255, 255, 0.2);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 5px #00ffff); }
            to { filter: drop-shadow(0 0 20px #ff00ff); }
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #00ffff;
            transform: translateY(-2px);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #00ffff, #ff00ff);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            background: radial-gradient(ellipse at center, rgba(0, 255, 255, 0.1) 0%, transparent 50%);
        }

        .hero-content {
            max-width: 800px;
            padding: 0 2rem;
            animation: fadeInUp 1s ease-out;
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

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #00ffff, #ff00ff, #ffff00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: textShine 3s ease-in-out infinite;
        }

        @keyframes textShine {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.3);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .cta-button:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 10px 30px rgba(0, 255, 255, 0.5);
        }

        /* Stats Section */
        .stats {
            padding: 5rem 2rem;
            text-align: center;
            background: rgba(0, 0, 0, 0.3);
        }

        .stats-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
        }

        .stat-card {
            background: linear-gradient(145deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
            padding: 2rem;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px) rotateY(5deg);
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.2);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #00ffff;
            margin-bottom: 1rem;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.8;
        }

        /* Videos Section */
        .videos {
            padding: 5rem 2rem;
        }

        .videos-container {
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }

        .section-title {
            font-size: 3rem;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .videos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .video-card {
            background: linear-gradient(145deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 255, 255, 0.2);
        }

        .video-card:hover {
            transform: scale(1.05) rotateY(5deg);
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.3);
        }

        .video-thumbnail {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, #1a1a2e, #16213e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: #00ffff;
        }

        .video-info {
            padding: 1.5rem;
        }

        .video-title {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: #00ffff;
        }

        .video-description {
            opacity: 0.8;
            line-height: 1.5;
        }

        /* Contact Section */
        .contact {
            padding: 5rem 2rem;
            background: rgba(0, 0, 0, 0.5);
            text-align: center;
        }

        .contact-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-link {
            display: inline-block;
            width: 60px;
            height: 60px;
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: white;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: scale(1.2) rotate(360deg);
            box-shadow: 0 0 30px rgba(0, 255, 255, 0.8);
        }

        /* Footer */
        footer {
            padding: 2rem;
            text-align: center;
            background: rgba(0, 0, 0, 0.8);
            border-top: 1px solid rgba(0, 255, 255, 0.2);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .stats-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Partículas de fondo -->
    <div class="particles" id="particles"></div>

    <!-- Header -->
    <header>
        <nav>
            <div class="logo">cub1ts</div>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#videos">Videos</a></li>
                <li><a href="#stats">Estadísticas</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <div class="hero-content">
            <h1>cub1ts</h1>
            <p>Explorando el futuro de la tecnología, un video a la vez</p>
            <p>Descubre las últimas tendencias, reviews de productos, tutoriales y análisis profundos del mundo tech</p>
            <a href="https://youtube.com/@cub1ts" target="_blank" class="cta-button">🚀 Suscríbete al Canal</a>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats" id="stats">
        <div class="stats-container">
            <div class="stat-card">
                <div class="stat-number" data-count="1000">0+</div>
                <div class="stat-label">Suscriptores</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-count="50">0+</div>
                <div class="stat-label">Videos</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-count="10000">0+</div>
                <div class="stat-label">Visualizaciones</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-count="95">0%</div>
                <div class="stat-label">Satisfacción</div>
            </div>
        </div>
    </section>

    <!-- Videos Section -->
    <section class="videos" id="videos">
        <div class="videos-container">
            <h2 class="section-title">Contenido Destacado</h2>
            <div class="videos-grid">
                <div class="video-card">
                    <div class="video-thumbnail">📱</div>
                    <div class="video-info">
                        <h3 class="video-title">Reviews de Smartphones</h3>
                        <p class="video-description">Análisis completos de los últimos dispositivos móviles del mercado</p>
                    </div>
                </div>
                <div class="video-card">
                    <div class="video-thumbnail">💻</div>
                    <div class="video-info">
                        <h3 class="video-title">Hardware & Gaming</h3>
                        <p class="video-description">Todo sobre PC gaming, componentes y rendimiento</p>
                    </div>
                </div>
                <div class="video-card">
                    <div class="video-thumbnail">🤖</div>
                    <div class="video-info">
                        <h3 class="video-title">IA & Futuro</h3>
                        <p class="video-description">Explorando las últimas tendencias en inteligencia artificial</p>
                    </div>
                </div>
                <div class="video-card">
                    <div class="video-thumbnail">⚙️</div>
                    <div class="video-info">
                        <h3 class="video-title">Tutoriales Tech</h3>
                        <p class="video-description">Guías paso a paso para dominar la tecnología</p>
                    </div>
                </div>
                <div class="video-card">
                    <div class="video-thumbnail">🔬</div>
                    <div class="video-info">
                        <h3 class="video-title">Innovación</h3>
                        <p class="video-description">Descubriendo las tecnologías que cambiarán el mundo</p>
                    </div>
                </div>
                <div class="video-card">
                    <div class="video-thumbnail">🛡️</div>
                    <div class="video-info">
                        <h3 class="video-title">Ciberseguridad</h3>
                        <p class="video-description">Mantente seguro en el mundo digital</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contacto">
        <div class="contact-container">
            <h2 class="section-title">Conecta Conmigo</h2>
            <p>¿Tienes alguna pregunta o sugerencia? ¡Me encantaría escucharte!</p>
            <div class="social-links">
                <a href="https://youtube.com/@cub1ts" target="_blank" class="social-link">▶️</a>
                <a href="#" class="social-link">📧</a>
                <a href="#" class="social-link">🐦</a>
                <a href="#" class="social-link">📷</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 cub1ts. Todos los derechos reservados. | Explorando el futuro tecnológico</p>
    </footer>

    <script>
        // Crear partículas de fondo
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.width = Math.random() * 4 + 2 + 'px';
                particle.style.height = particle.style.width;
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Animación de contadores
        function animateCounters() {
            const counters = document.querySelectorAll('[data-count]');
            
            counters.forEach(counter => {
                const target = parseInt(counter.getAttribute('data-count'));
                const duration = 2000;
                const increment = target / (duration / 16);
                let current = 0;
                
                const timer = setInterval(() => {
                    current += increment;
                    if (current >= target) {
                        current = target;
                        clearInterval(timer);
                    }
                    
                    if (counter.textContent.includes('%')) {
                        counter.textContent = Math.floor(current) + '%';
                    } else if (target >= 1000) {
                        counter.textContent = Math.floor(current).toLocaleString() + '+';
                    } else {
                        counter.textContent = Math.floor(current) + '+';
                    }
                }, 16);
            });
        }

        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Intersection Observer para animar elementos al entrar en vista
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    if (entry.target.classList.contains('stats')) {
                        animateCounters();
                    }
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observar elementos para animación
        document.querySelectorAll('.stat-card, .video-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(50px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });

        observer.observe(document.querySelector('.stats'));

        // Inicializar
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
        });

        // Efecto parallax suave
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const particles = document.getElementById('particles');
            particles.style.transform = `translateY(${scrolled * 0.3}px)`;
        });
    </script>
</body>
</html>
