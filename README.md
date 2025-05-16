<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PAN PIZZA NEO | Cocina del Futuro</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;700;900&family=Rajdhani:wght@500;700&display=swap');
        
        :root {
            --primary: #00f7ff;
            --secondary: #ff00f7;
            --tertiary: #7bff00;
            --dark: #0a0a14;
            --darker: #050510;
            --light: #e0e0ff;
            --neon-glow-primary: 0 0 10px rgba(0, 247, 255, 0.8), 0 0 20px rgba(0, 247, 255, 0.6), 0 0 30px rgba(0, 247, 255, 0.3);
            --neon-glow-secondary: 0 0 10px rgba(255, 0, 247, 0.8), 0 0 20px rgba(255, 0, 247, 0.6), 0 0 30px rgba(255, 0, 247, 0.3);
            --neon-glow-tertiary: 0 0 10px rgba(123, 255, 0, 0.8), 0 0 20px rgba(123, 255, 0, 0.6), 0 0 30px rgba(123, 255, 0, 0.3);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Rajdhani', sans-serif;
            background-color: var(--dark);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(0, 247, 255, 0.03) 0%, transparent 25%),
                radial-gradient(circle at 80% 70%, rgba(255, 0, 247, 0.03) 0%, transparent 25%),
                linear-gradient(to bottom, var(--darker), var(--dark));
            min-height: 100vh;
        }
        
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            background-color: var(--primary);
            border-radius: 50%;
            opacity: 0.6;
            animation: float infinite alternate ease-in-out;
        }
        
        @keyframes float {
            0% { transform: translateY(0) translateX(0); }
            100% { transform: translateY(-100vh) translateX(20px); }
        }
        
        header {
            text-align: center;
            padding: 3rem 2rem;
            position: relative;
            overflow: hidden;
            border-bottom: 1px solid rgba(0, 247, 255, 0.2);
            background: rgba(10, 10, 20, 0.7);
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
            margin-bottom: 3rem;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: 
                linear-gradient(
                    to bottom right, 
                    transparent 45%, 
                    rgba(0, 247, 255, 0.05) 50%, 
                    transparent 55%
                );
            transform: rotate(30deg);
            animation: shine 8s infinite linear;
            z-index: -1;
        }
        
        @keyframes shine {
            0% { transform: rotate(30deg) translate(-30%, -30%); }
            100% { transform: rotate(30deg) translate(30%, 30%); }
        }
        
        h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: 4rem;
            font-weight: 900;
            margin: 0;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: var(--neon-glow-primary);
            letter-spacing: 3px;
            text-transform: uppercase;
            position: relative;
            display: inline-block;
        }
        
        h1::after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 3px;
            animation: pulse 2s infinite ease-in-out;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 0.7; transform: scaleX(0.95); }
            50% { opacity: 1; transform: scaleX(1); }
        }
        
        .tagline {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.5rem;
            letter-spacing: 4px;
            margin-top: 1rem;
            color: var(--tertiary);
            text-shadow: var(--neon-glow-tertiary);
            animation: flicker 4s infinite alternate;
        }
        
        @keyframes flicker {
            0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
                opacity: 1;
                text-shadow: var(--neon-glow-tertiary);
            }
            20%, 22%, 24%, 55% {
                opacity: 0.6;
                text-shadow: none;
            }
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
            gap: 3rem;
            margin-bottom: 5rem;
        }
        
        .pizza-card {
            background: rgba(20, 20, 30, 0.6);
            border-radius: 15px;
            padding: 2rem;
            border: 1px solid rgba(0, 247, 255, 0.3);
            box-shadow: 
                0 0 20px rgba(0, 247, 255, 0.2),
                inset 0 0 15px rgba(0, 247, 255, 0.1);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
        }
        
        .pizza-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                linear-gradient(135deg, transparent 48%, rgba(0, 247, 255, 0.1) 49%, rgba(0, 247, 255, 0.1) 51%, transparent 52%),
                linear-gradient(45deg, transparent 48%, rgba(255, 0, 247, 0.1) 49%, rgba(255, 0, 247, 0.1) 51%, transparent 52%);
            background-size: 20px 20px;
            opacity: 0.3;
            z-index: -1;
            pointer-events: none;
        }
        
        .pizza-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 
                0 0 40px rgba(0, 247, 255, 0.4),
                0 0 60px rgba(255, 0, 247, 0.2),
                inset 0 0 20px rgba(123, 255, 0, 0.1);
            border: 1px solid rgba(0, 247, 255, 0.6);
        }
        
        .pizza-card:nth-child(odd):hover {
            box-shadow: 
                0 0 40px rgba(255, 0, 247, 0.4),
                0 0 60px rgba(0, 247, 255, 0.2),
                inset 0 0 20px rgba(123, 255, 0, 0.1);
        }
        
        .pizza-card::after {
            content: "";
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            border-radius: 17px;
            background: linear-gradient(45deg, var(--primary), var(--secondary), var(--tertiary), var(--secondary), var(--primary));
            background-size: 400%;
            z-index: -2;
            opacity: 0;
            transition: 0.5s;
            animation: borderGlow 6s linear infinite;
        }
        
        .pizza-card:hover::after {
            opacity: 1;
        }
        
        @keyframes borderGlow {
            0% { background-position: 0 0; }
            50% { background-position: 400% 0; }
            100% { background-position: 0 0; }
        }
        
        .pizza-image-container {
            position: relative;
            width: 100%;
            height: 250px;
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 1.5rem;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(0, 247, 255, 0.5);
        }
        
        .pizza-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.8s ease;
        }
        
        .pizza-card:hover .pizza-image {
            transform: scale(1.1);
        }
        
        .pizza-image-container::after {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(to bottom, rgba(0, 247, 255, 0.1), rgba(255, 0, 247, 0.1));
            mix-blend-mode: overlay;
            pointer-events: none;
        }
        
        h2 {
            font-family: 'Orbitron', sans-serif;
            color: var(--primary);
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid rgba(0, 247, 255, 0.3);
            text-shadow: var(--neon-glow-primary);
            letter-spacing: 1px;
        }
        
        .pizza-card:nth-child(odd) h2 {
            color: var(--secondary);
            text-shadow: var(--neon-glow-secondary);
        }
        
        h3 {
            font-family: 'Orbitron', sans-serif;
            color: var(--tertiary);
            margin: 1.8rem 0 1rem;
            font-size: 1.4rem;
            text-shadow: var(--neon-glow-tertiary);
            letter-spacing: 1px;
        }
        
        ul, ol {
            padding-left: 1.8rem;
        }
        
        li {
            margin-bottom: 0.7rem;
            position: relative;
            font-size: 1.1rem;
            color: var(--light);
        }
        
        li::before {
            content: ">";
            color: var(--primary);
            position: absolute;
            left: -1.5rem;
            font-family: 'Orbitron', sans-serif;
            font-weight: bold;
            animation: blink 1.5s infinite;
        }
        
        .pizza-card:nth-child(odd) li::before {
            color: var(--secondary);
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }
        
        footer {
            text-align: center;
            padding: 3rem 2rem;
            margin-top: 5rem;
            border-top: 1px solid rgba(0, 247, 255, 0.3);
            position: relative;
            background: rgba(10, 10, 20, 0.7);
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
        }
        
        footer::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                linear-gradient(
                    90deg,
                    transparent 0%,
                    rgba(0, 247, 255, 0.05) 50%,
                    transparent 100%
                );
            z-index: -1;
        }
        
        footer p {
            margin-bottom: 1rem;
            font-family: 'Orbitron', sans-serif;
            letter-spacing: 1px;
        }
        
        .qr-placeholder {
            display: inline-block;
            width: 120px;
            height: 120px;
            margin-top: 1rem;
            border: 2px solid var(--primary);
            position: relative;
            overflow: hidden;
            box-shadow: var(--neon-glow-primary);
            animation: pulse 2s infinite ease-in-out;
        }
        
        .qr-placeholder::before {
            content: "QR";
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: var(--primary);
            font-family: 'Orbitron', sans-serif;
            font-size: 1.5rem;
            text-shadow: var(--neon-glow-primary);
        }
        
        .cursor-follower {
            position: fixed;
            width: 20px;
            height: 20px;
            background: radial-gradient(circle, var(--primary) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
            transform: translate(-50%, -50%);
            mix-blend-mode: screen;
            z-index: 9999;
            opacity: 0.7;
        }
        
        .scan-line {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to bottom, transparent, var(--tertiary), transparent);
            z-index: 9998;
            opacity: 0.3;
            animation: scan 8s linear infinite;
            pointer-events: none;
            box-shadow: 0 0 10px var(--tertiary);
        }
        
        @keyframes scan {
            0% { top: -5px; }
            100% { top: 100%; }
        }
        
        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 2.5rem;
            }
            
            .tagline {
                font-size: 1.2rem;
            }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>
    <div class="scan-line"></div>
    <div class="cursor-follower" id="cursorFollower"></div>
    
    <header>
        <h1>PAN PIZZA NEO</h1>
        <p class="tagline">REVOLUCIÓN GASTRONÓMICA</p>
    </header>
    
    <div class="container">
        <div class="pizza-card">
            <div class="pizza-image-container">
                <img src="https://truffle-assets.tastemadecontent.net/ee31e5d5-7acd2776-1507_meatza_land1.jpg" alt="Pan Pizza Multicarne" class="pizza-image">
            </div>
            <h2>PAN PIZZA MULTICARNE</h2>
            <h3>INGREDIENTES:</h3>
            <ul>
                <li>Masa de pan especial con levadura bio-activada</li>
                <li>Salsa de tomate infundida con hierbas cuánticas</li>
                <li>Mezcla de carnes premium: pepperoni, jamón y salchicha</li>
                <li>Tocino crujiente de triple cocción</li>
                <li>Queso mozzarella de cultivo celular</li>
                <li>Queso cheddar envejecido orbitalmente</li>
                <li>Champiñones portobello de cultivo vertical</li>
                <li>Aceite de oliva con especias galácticas</li>
            </ul>
            
            <h3>PREPARACIÓN:</h3>
            <ol>
                <li>Preparar la masa en molde antiadherente de alta tecnología</li>
                <li>Fermentar durante 24 horas en cámara de ambiente controlado</li>
                <li>Extender la masa con rodillo de precisión molecular</li>
                <li>Aplicar salsa de tomate con dispensador cuántico</li>
                <li>Distribuir los ingredientes en secuencia algorítmica</li>
                <li>Hornear a 220°C durante 18 minutos en modo convección</li>
                <li>Finalizar con 2 minutos de gratinado por radiación infrarroja</li>
                <li>Decorar con espiral de aceite de trufa negra sintética</li>
            </ol>
        </div>
        
        <div class="pizza-card">
            <div class="pizza-image-container">
                <img src="https://images.unsplash.com/photo-1595708684082-a173bb3a06c5?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Pan Pizza Vegetariana" class="pizza-image">
            </div>
            <h2>PAN PIZZA VEGETARIANA</h2>
            <h3>INGREDIENTES:</h3>
            <ul>
                <li>Masa de pan integral con semillas interestelares</li>
                <li>Salsa de tomate con hierbas de jardín hidropónico</li>
                <li>Queso vegano de almendras modificadas genéticamente</li>
                <li>Pimientos tricolores cultivados en gravedad cero</li>
                <li>Cebolla caramelizada con miel de agave lunar</li>
                <li>Espinacas baby criadas en ambiente controlado</li>
                <li>Aceitunas Kalamata de cultivo biodinámico</li>
                <li>Tomates secados al vacío cuántico</li>
                <li>Albahaca genéticamente optimizada para máximo aroma</li>
            </ul>
            
            <h3>PREPARACIÓN:</h3>
            <ol>
                <li>Preparar la masa en molde de cerámica avanzada</li>
                <li>Fermentar durante 36 horas en ambiente de humedad controlada</li>
                <li>Extender la masa con técnica de levitación acústica</li>
                <li>Aplicar salsa de tomate con patrón fractal</li>
                <li>Organizar los vegetales en formación estelar</li>
                <li>Hornear a 200°C durante 20 minutos en modo eco-sostenible</li>
                <li>Finalizar con 1 minuto de radiación ultravioleta para dorado perfecto</li>
                <li>Decorar con microgreens cultivados en la Estación Espacial</li>
            </ol>
        </div>
    </div>
    
    <footer>
        <p>SISTEMA DE ALIMENTACIÓN DEL FUTURO - VERSIÓN 5.2.1</p>
        <p>CONTACTO: contacto@panpizzaneo.gx | CANAL HOLOGRÁFICO: 1010101010</p>
        <p>© 2187 PAN PIZZA NEO (TODOS LOS UNIVERSOS PARALELOS)</p>
        <div class="qr-placeholder" title="Escanea para visitar PAN PIZZA NEO"></div>
    </footer>
    
    <script>
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                const size = Math.random() * 3 + 1;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                
                particle.style.left = `${Math.random() * 100}%`;
                particle.style.top = `${Math.random() * 100}%`;
                
                const colors = ['var(--primary)', 'var(--secondary)', 'var(--tertiary)'];
                particle.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                
                const duration = Math.random() * 20 + 10;
                particle.style.animationDuration = `${duration}s`;
                
                particle.style.animationDelay = `${Math.random() * 20}s`;
                
                particlesContainer.appendChild(particle);
            }
        }
        
        function initCursorFollower() {
            const cursorFollower = document.getElementById('cursorFollower');
            
            document.addEventListener('mousemove', (e) => {
                cursorFollower.style.left = `${e.clientX}px`;
                cursorFollower.style.top = `${e.clientY}px`;
                
                const target = e.target;
                if (target.closest('.pizza-card, a, button, h1, h2, h3')) {
                    cursorFollower.style.transform = 'translate(-50%, -50%) scale(2.5)';
                    cursorFollower.style.opacity = '0.4';
                } else {
                    cursorFollower.style.transform = 'translate(-50%, -50%) scale(1)';
                    cursorFollower.style.opacity = '0.7';
                }
            });
        }
        
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            initCursorFollower();
        });
    </script>
</body>
</html>
