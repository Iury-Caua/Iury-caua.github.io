<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IntegraMec - Interdisciplinaridade da Engenharia Mecânica</title>
    <link rel="stylesheet" href="css/style.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="container">
            <div class="header-inner">
                <div class="logo">
                    <img id="logo-ufc"src="./images/brasao4_vertical_cor_300dpi.png" alt="ufc Logo">
                    <h1>INTEGRAMEC</h1>
                </div>
                <nav class="nav">
                    <a href="https://iury-caua.github.io/pages/estrutturacurricularmec.pdf" target="_blank">Estrutura Curricular</a>
                    <a href="https://iury-caua.github.io/pages/cidade-interativa.html" target="_blank">Realidade Virtual</a>
                    <a href="https://iury-caua.github.io/pages/participantes.html" target="_blank">Participantes</a>
                    <a href="#reviews">Opiniões</a>
                    <a href="#contact">Contato</a>
                </nav>
                <div class="header-right">
                    <button class="menu-toggle" id="menuToggle" aria-label="Menu">&#9776;</button>
                </div>
            </div>
        </div>
    </header>
    <!-- Mobile Nav -->
    <div class="mobile-nav" id="mobileNav">
        <button class="mobile-nav-close" id="mobileNavClose">&times;</button>
        <a href="https://iury-caua.github.io/pages/estrutturacurricularmec.pdf" target="_blank">Estrutura Curricular</a>
        <a href="https://iury-caua.github.io/pages/cidade-interativa.html" target="_blank">Realidade Virtual</a>
        <a href="https://iury-caua.github.io/pages/participantes.html" target="_blank">Participantes</a>
        <a href="#reviews">Opiniões</a>
        <a href="#contact">Contato</a>
    </div>
    <!-- Hero -->
    <section class="hero">
        <div class="hero-visual">
        </div>
        <div class="container">
            <div class="hero-content">
                <span class="hero-tag">Mecânica em Conexão.</span>
                <h2>O motor da inovação é<br> multidisciplinar.</h2>
                <p>Muito além das engrenagens: A interdisciplinaridade moldando o engenheiro mecânico na UFC.</p>
                <div class="hero-btns">
                    <a href="https://iury-caua.github.io/pages/cidade-interativa.html" class="btn btn-primary">Realidade Virtual</a>
                    <a href="#reviews" class="btn btn-glass">Avaliar</a>
                </div>
            </div>
        </div>
    </section>
    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand">
                    <div class="logo">
                        <img id="logo-ufc"src="images/brasao4_vertical_cor_300dpi.png" alt="ufc Logo">
                        <h3>INTEGRAMEC</h3>
                    </div>
                    <p>Mais que calcular forças, conectar ideias: A interdisciplinaridade na Mecânica da UFC.</p>
                    <div class="social-links">
                        <a href="#">Ig</a>
                        <a href="#">Fb</a>
                        <a href="#">Yt</a>
                        <a href="#">Pi</a>
                    </div>
                </div>
                <div class="footer-links">
                    <h4>Estrutura Curricular</h4>
                    <a href="https://iury-caua.github.io/pages/estrutturacurricularmec.pdf" target="_blank">Eng. Mecânica</a>
                    <a href="#">Eng. Telecomunicações</a>
                    <a href="#">Eng. Produção</a>
                </div>
                <div class="footer-links">
                    <h4>Participantes</h4>
                    <a href="#">Orientador</a>
                    <a href="#">Colaboradores</a>
                    <a href="#">Voluntários</a>
                    <a href="#">Bolsistas</a>
                </div>
                <div class="footer-links">
                    <h4>Contato</h4>
                    <a href="#">Whatsapp</a>
                    <a href="#">Instagram</a>
                    <a href="#">Email</a>
                    <a href="#">Telegram</a>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2026 IntegraMec. Todos os direitos reservados.</p>
                <div class="footer-legal">
                    <a href="#">Privacidade</a>
                    <a href="#">Termos</a>
                    <a href="#">Cookies</a>
                </div>
            </div>
        </div>
    </footer>
    <!-- Back to Top -->
    <button class="back-to-top" id="backToTop" aria-label="Back to top">&#8593;</button>
    <script>
        // Mobile Nav
        document.getElementById('menuToggle').addEventListener('click', () => document.getElementById('mobileNav').classList.add('active'));
        document.getElementById('mobileNavClose').addEventListener('click', () => document.getElementById('mobileNav').classList.remove('active'));
        document.querySelectorAll('.mobile-nav a').forEach(l => l.addEventListener('click', () => document.getElementById('mobileNav').classList.remove('active')));
        // Back to Top
        const btt = document.getElementById('backToTop');
        window.addEventListener('scroll', () => btt.classList.toggle('visible', window.scrollY > 500));
        btt.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));
        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(a => {
            a.addEventListener('click', function(e) {
                e.preventDefault();
                const t = document.querySelector(this.getAttribute('href'));
                if (t) t.scrollIntoView({ behavior: 'smooth', block: 'start' });
            });
        });
        // Scroll Animations
        const obs = new IntersectionObserver((entries) => {
            entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('animate-in'); obs.unobserve(e.target); } });
        }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
        document.querySelectorAll('.product-card, .collection-card, .review-card, .feature-item, .craft-step, .spec-item, .boutique-card').forEach(el => {
            el.classList.add('animate-target');
            obs.observe(el);
        });
        // Animated Watch Hands
        function updateClock() {
            const now = new Date();
            const sec = now.getSeconds();
            const min = now.getMinutes();
            const hr = now.getHours() % 12;
            const secDeg = sec * 6;
            const minDeg = min * 6 + sec * 0.1;
            const hrDeg = hr * 30 + min * 0.5;
            const sh = document.querySelector('.second-hand');
            const mh = document.querySelector('.minute-hand');
            const hh = document.querySelector('.hour-hand');
            if (sh) sh.style.transform = `rotate(${secDeg}deg)`;
            if (mh) mh.style.transform = `rotate(${minDeg}deg)`;
            if (hh) hh.style.transform = `rotate(${hrDeg}deg)`;
        }
        updateClock();
        setInterval(updateClock, 1000);
    </script>
</body>
</html>
