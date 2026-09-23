<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Speed Legends | Carros Esportivos</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, sans-serif;
        }

        body {
            background: #0a0a0a;
            color: #fff;
            overflow-x: hidden;
        }

        /* HEADER */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 60px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 0, 0, 0.3);
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 900;
            color: #e10600;
            letter-spacing: 2px;
        }

        .logo span {
            color: #fff;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 40px;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }

        nav a:hover {
            color: #e10600;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 0;
            height: 2px;
            background: #e10600;
            transition: width 0.3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        /* HERO */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a0000 50%, #0a0a0a 100%);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(225, 6, 0, 0.15) 0%, transparent 70%);
            animation: pulse 6s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.2); opacity: 0.8; }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            padding: 0 20px;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 6rem);
            font-weight: 900;
            background: linear-gradient(90deg, #fff, #e10600);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            letter-spacing: 2px;
            animation: slideDown 1s ease-out;
        }

        .hero p {
            font-size: clamp(1rem, 2vw, 1.3rem);
            color: #ccc;
            max-width: 700px;
            margin: 0 auto 40px;
            animation: slideUp 1s ease-out 0.3s both;
        }

        .btn {
            display: inline-block;
            padding: 15px 45px;
            background: #e10600;
            color: #fff;
            text-decoration: none;
            font-weight: 700;
            letter-spacing: 1px;
            border-radius: 50px;
            transition: all 0.3s;
            animation: slideUp 1s ease-out 0.6s both;
            box-shadow: 0 0 30px rgba(225, 6, 0, 0.5);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 40px rgba(225, 6, 0, 0.8);
            background: #ff1a1a;
        }

        @keyframes slideDown {
            from { opacity: 0; transform: translateY(-50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* SECTION */
        section {
            padding: 100px 60px;
        }

        .section-title {
            text-align: center;
            font-size: clamp(2rem, 4vw, 3rem);
            margin-bottom: 20px;
            font-weight: 900;
        }

        .section-title span {
            color: #e10600;
        }

        .section-subtitle {
            text-align: center;
            color: #888;
            margin-bottom: 60px;
            font-size: 1.1rem;
        }

        /* CARDS */
        .cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .card {
            background: linear-gradient(145deg, #141414, #0a0a0a);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid #222;
            transition: all 0.4s;
            position: relative;
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: #e10600;
            box-shadow: 0 20px 50px rgba(225, 6, 0, 0.3);
        }

        .card-image {
            height: 220px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 6rem;
            background: linear-gradient(135deg, #1a0000, #2a0000);
            position: relative;
            overflow: hidden;
        }

        .card-image::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(180deg, transparent 50%, #141414 100%);
        }

        .card-body {
            padding: 25px;
        }

        .card-body h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }

        .card-body .pais {
            color: #e10600;
            font-size: 0.9rem;
            font-weight: 600;
            letter-spacing: 1px;
            text-transform: uppercase;
            margin-bottom: 15px;
        }

        .card-body p {
            color: #999;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .specs {
            display: flex;
            justify-content: space-between;
            padding-top: 20px;
            border-top: 1px solid #222;
        }

        .spec {
            text-align: center;
        }

        .spec-value {
            font-size: 1.3rem;
            font-weight: 900;
            color: #e10600;
        }

        .spec-label {
            font-size: 0.75rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* CATEGORIAS */
        .categorias {
            background: linear-gradient(180deg, #0a0a0a, #141414);
        }

        .cat-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .cat-item {
            padding: 40px 30px;
            background: #141414;
            border-radius: 15px;
            border-left: 4px solid #e10600;
            transition: all 0.3s;
            cursor: pointer;
        }

        .cat-item:hover {
            background: #1a0000;
            transform: translateX(10px);
        }

        .cat-item h4 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: #e10600;
        }

        .cat-item p {
            color: #888;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        /* FOOTER */
        footer {
            background: #050505;
            padding: 40px 60px;
            text-align: center;
            border-top: 1px solid #1a1a1a;
        }

        footer p {
            color: #666;
            font-size: 0.9rem;
        }

        footer .red {
            color: #e10600;
            font-weight: 700;
        }

        /* RESPONSIVO */
        @media (max-width: 768px) {
            header {
                padding: 15px 20px;
            }

            nav ul {
                gap: 15px;
            }

            nav a {
                font-size: 0.85rem;
            }

            section {
                padding: 60px 20px;
            }

            .logo {
                font-size: 1.3rem;
            }
        }

        @media (max-width: 500px) {
            nav {
                display: none;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">SPEED<span>LEGENDS</span></div>
        <nav>
            <ul>
                <li><a href="#home">Início</a></li>
                <li><a href="#lendas">Lendas</a></li>
                <li><a href="#categorias">Categorias</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero" id="home">
        <div class="hero-content">
            <h1>VELOCIDADE PURA</h1>
            <p>Descubra o mundo dos carros esportivos mais icônicos do planeta. Potência, design e adrenalina em cada curva.</p>
            <a href="#lendas" class="btn">EXPLORAR</a>
        </div>
    </section>

    <section id="lendas">
        <h2 class="section-title">Lendas das <span>Pistas</span></h2>
        <p class="section-subtitle">Os carros que marcaram gerações</p>

        <div class="cards">
            <div class="card">
                <div class="card-image">🏎️</div>
                <div class="card-body">
                    <h3>Ferrari F40</h3>
                    <p class="pais">🇮🇹 Itália</p>
                    <p>Considerada a última Ferrari aprovada por Enzo Ferrari. Um ícone dos anos 80 com design brutal e desempenho extremo.</p>
                    <div class="specs">
                        <div class="spec">
                            <div class="spec-value">478</div>
                            <div class="spec-label">Cavalos</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">324</div>
                            <div class="spec-label">km/h</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">3.8s</div>
                            <div class="spec-label">0-100</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-image">🐂</div>
                <div class="card-body">
                    <h3>Lamborghini Aventador</h3>
                    <p class="pais">🇮🇹 Itália</p>
                    <p>Design agressivo e motor V12 aspirado. O touro furioso italiano que domina as ruas com seu visual futurista.</p>
                    <div class="specs">
                        <div class="spec">
                            <div class="spec-value">770</div>
                            <div class="spec-label">Cavalos</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">355</div>
                            <div class="spec-label">km/h</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">2.8s</div>
                            <div class="spec-label">0-100</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-image">🏁</div>
                <div class="card-body">
                    <h3>Porsche 911 GT3</h3>
                    <p class="pais">🇩🇪 Alemanha</p>
                    <p>Precisão alemã e engenharia perfeita. O 911 é um dos esportivos mais equilibrados e icônicos já produzidos.</p>
                    <div class="specs">
                        <div class="spec">
                            <div class="spec-value">510</div>
                            <div class="spec-label">Cavalos</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">318</div>
                            <div class="spec-label">km/h</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">3.4s</div>
                            <div class="spec-label">0-100</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-image">⚡</div>
                <div class="card-body">
                    <h3>McLaren 720S</h3>
                    <p class="pais">🇬🇧 Reino Unido</p>
                    <p>Leveza e tecnologia britânica. Chassi de fibra de carbono e aerodinâmica de Fórmula 1 nas ruas.</p>
                    <div class="specs">
                        <div class="spec">
                            <div class="spec-value">720</div>
                            <div class="spec-label">Cavalos</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">341</div>
                            <div class="spec-label">km/h</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">2.9s</div>
                            <div class="spec-label">0-100</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-image">🇺🇸</div>
                <div class="card-body">
                    <h3>Chevrolet Corvette Z06</h3>
                    <p class="pais">🇺🇸 EUA</p>
                    <p>O muscle car esportivo americano. Motor V8 central-traseiro e um ronco inconfundível.</p>
                    <div class="specs">
                        <div class="spec">
                            <div class="spec-value">670</div>
                            <div class="spec-label">Cavalos</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">315</div>
                            <div class="spec-label">km/h</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">2.7s</div>
                            <div class="spec-label">0-100</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-image">🌀</div>
                <div class="card-body">
                    <h3>Bugatti Chiron</h3>
                    <p class="pais">🇫🇷 França</p>
                    <p>O hipercarro definitivo. Velocidade máxima absurda e luxo incomparável. Um monstro de 16 cilindros.</p>
                    <div class="specs">
                        <div class="spec">
                            <div class="spec-value">1500</div>
                            <div class="spec-label">Cavalos</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">420</div>
                            <div class="spec-label">km/h</div>
                        </div>
                        <div class="spec">
                            <div class="spec-value">2.4s</div>
                            <div class="spec-label">0-100</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="categorias" id="categorias">
        <h2 class="section-title">Tipos de <span>Esportivos</span></h2>
        <p class="section-subtitle">Cada categoria tem sua essência</p>

        <div class="cat-grid">
            <div class="cat-item">
                <h4>🏁 Supercars</h4>
                <p>Alta performance extrema, geralmente com motores V8, V10 ou V12. Exemplos: Ferrari, Lamborghini e McLaren.</p>
            </div>
            <div class="cat-item">
                <h4>💪 Muscle Cars</h4>
                <p>Potência bruta americana, motores grandes e visual imponente. Exemplos: Mustang, Camaro e Challenger.</p>
            </div>
            <div class="cat-item">
                <h4>⚡ Hypercars</h4>
                <p>O topo da cadeia automotiva. Tecnologia híbrida e velocidades acima de 400 km/h. Exemplos: Bugatti e Koenigsegg.</p>
            </div>
            <div class="cat-item">
                <h4>🎯 Track Cars</h4>
                <p>Feitos para as pistas. Foco total em aerodinâmica e leveza. Exemplos: Porsche GT3 RS e Ferrari Pista.</p>
            </div>
            <div class="cat-item">
                <h4>🔋 Elétricos Esportivos</h4>
                <p>O futuro da velocidade. Torque instantâneo e aceleração absurda. Exemplos: Tesla Plaid e Rimac Nevera.</p>
            </div>
            <div class="cat-item">
                <h4>🏎️ GT Cars</h4>
                <p>Grand Tourers: esportivos de luxo feitos para longas viagens com conforto e potência. Exemplos: Aston Martin DB11.</p>
            </div>
        </div>
    </section>

    <footer>
        <p>© 2025 <span class="red">SpeedLegends</span> - Todos os direitos reservados. Feito com paixão por carros.</p>
    </footer>

</body>
</html>
