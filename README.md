<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Poison Studios</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #050505;
            color: #fff;
        }

        /* =========================
           BARRA DE NAVEGAÇÃO
        ========================= */

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(5, 5, 5, 0.88);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(145, 45, 255, 0.25);
        }

        nav {
            max-width: 1200px;
            height: 75px;
            margin: auto;
            padding: 0 25px;

            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            font-size: 23px;
            font-weight: 900;
            letter-spacing: 4px;
            color: white;
        }

        .logo span {
            color: #9b35ff;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            color: #ddd;
            text-decoration: none;
            font-size: 14px;
            transition: 0.3s;
        }

        nav a:hover {
            color: #a83cff;
        }

        /* =========================
           HERO
        ========================= */

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 100px 20px 60px;

            background:
                radial-gradient(
                    circle at center,
                    rgba(126, 27, 220, 0.22),
                    transparent 35%
                ),
                linear-gradient(
                    135deg,
                    #050505 0%,
                    #0b0610 50%,
                    #050505 100%
                );

            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: "";
            position: absolute;
            width: 500px;
            height: 500px;
            border-radius: 50%;
            border: 1px solid rgba(159, 48, 255, 0.12);
            box-shadow:
                0 0 80px rgba(130, 25, 230, 0.08),
                inset 0 0 80px rgba(130, 25, 230, 0.08);
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 850px;
        }

        .hero small {
            color: #a83cff;
            letter-spacing: 6px;
            font-size: 12px;
            font-weight: bold;
        }

        .hero h1 {
            margin-top: 18px;
            font-size: clamp(48px, 9vw, 105px);
            letter-spacing: 8px;
            font-weight: 900;
            line-height: 0.95;
        }

        .hero h1 span {
            color: #9d35ff;
        }

        .hero p {
            margin: 28px auto 0;
            max-width: 600px;
            color: #aaa;
            line-height: 1.7;
            font-size: 16px;
        }

        .hero-button {
            display: inline-block;
            margin-top: 35px;
            padding: 14px 30px;

            border: 1px solid #9631f4;
            color: white;
            text-decoration: none;

            letter-spacing: 2px;
            font-size: 12px;
            font-weight: bold;

            transition: 0.3s;
        }

        .hero-button:hover {
            background: #9631f4;
            box-shadow: 0 0 25px rgba(150, 49, 244, 0.4);
        }

        /* =========================
           SEÇÃO SOBRE
        ========================= */

        .about {
            max-width: 1000px;
            margin: auto;
            padding: 110px 25px;
            text-align: center;
        }

        .section-label {
            color: #a83cff;
            font-size: 11px;
            letter-spacing: 5px;
            font-weight: bold;
        }

        .about h2 {
            font-size: 42px;
            margin: 15px 0 25px;
        }

        .about p {
            color: #999;
            line-height: 1.8;
            max-width: 700px;
            margin: auto;
        }

        /* =========================
           COLEÇÃO
        ========================= */

        .collection {
            padding: 100px 25px;
            background: #080808;
        }

        .collection-header {
            max-width: 1200px;
            margin: auto;
            text-align: center;
            margin-bottom: 55px;
        }

        .collection-header h2 {
            font-size: 42px;
            margin-top: 15px;
        }

        .collection-grid {
            max-width: 1200px;
            margin: auto;

            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .card {
            height: 360px;
            position: relative;
            overflow: hidden;

            border: 1px solid rgba(163, 51, 255, 0.22);

            background:
                linear-gradient(
                    145deg,
                    #111 0%,
                    #090909 55%,
                    #150b1d 100%
                );

            display: flex;
            align-items: flex-end;

            transition: 0.4s;
        }

        .card::before {
            content: "";
            position: absolute;
            width: 220px;
            height: 220px;
            border-radius: 50%;

            background: rgba(140, 30, 240, 0.12);
            filter: blur(50px);

            top: -70px;
            right: -50px;

            transition: 0.4s;
        }

        .card:hover {
            transform: translateY(-8px);
            border-color: rgba(163, 51, 255, 0.7);
            box-shadow: 0 15px 40px rgba(111, 24, 190, 0.15);
        }

        .card:hover::before {
            background: rgba(153, 40, 255, 0.23);
        }

        .card-content {
            position: relative;
            z-index: 2;
            padding: 28px;
        }

        .card-number {
            font-size: 11px;
            color: #9d35ff;
            letter-spacing: 3px;
        }

        .card h3 {
            margin-top: 8px;
            font-size: 29px;
            letter-spacing: 2px;
        }

        .card p {
            margin-top: 10px;
            color: #888;
            font-size: 13px;
        }

        /* =========================
           IDENTIDADE
        ========================= */

        .identity {
            padding: 120px 25px;
            text-align: center;

            background:
                radial-gradient(
                    circle,
                    rgba(119, 28, 210, 0.14),
                    transparent 45%
                );
        }

        .identity h2 {
            font-size: 40px;
            margin: 15px 0 20px;
        }

        .identity p {
            max-width: 650px;
            margin: auto;
            color: #999;
            line-height: 1.8;
        }

        .identity-line {
            width: 80px;
            height: 2px;
            background: #9631f4;
            margin: 35px auto;
        }

        /* =========================
           INSTAGRAM
        ========================= */

        .instagram {
            padding: 80px 25px;
            text-align: center;
            background: #080808;
        }

        .instagram h2 {
            margin-top: 15px;
            font-size: 32px;
        }

        .instagram p {
            color: #888;
            margin-top: 12px;
        }

        .instagram a {
            display: inline-block;
            margin-top: 25px;
            color: #a83cff;
            text-decoration: none;
            font-weight: bold;
            letter-spacing: 1px;
            transition: 0.3s;
        }

        .instagram a:hover {
            color: white;
        }

        /* =========================
           RODAPÉ
        ========================= */

        footer {
            border-top: 1px solid rgba(145, 45, 255, 0.18);
            padding: 35px 25px;
            text-align: center;
            background: #030303;
        }

        footer .footer-logo {
            font-size: 18px;
            font-weight: 900;
            letter-spacing: 4px;
        }

        footer .footer-logo span {
            color: #9d35ff;
        }

        footer p {
            margin-top: 12px;
            color: #555;
            font-size: 12px;
        }

        /* =========================
           RESPONSIVO
        ========================= */

        @media (max-width: 800px) {

            nav {
                height: 65px;
            }

            nav ul {
                display: none;
            }

            .hero h1 {
                letter-spacing: 4px;
            }

            .collection-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .card {
                height: 300px;
            }
        }

        @media (max-width: 520px) {

            .logo {
                font-size: 18px;
                letter-spacing: 3px;
            }

            .hero {
                min-height: 90vh;
            }

            .hero h1 {
                font-size: 47px;
            }

            .hero p {
                font-size: 14px;
            }

            .about h2,
            .collection-header h2,
            .identity h2 {
                font-size: 32px;
            }

            .collection-grid {
                grid-template-columns: 1fr;
            }

            .card {
                height: 280px;
            }
        }
    </style>
</head>

<body>

    <!-- =========================
         NAVEGAÇÃO
    ========================== -->

    <header>
        <nav>

            <div class="logo">
                POISON <span>STUDIOS</span>
            </div>

            <ul>
                <li><a href="#inicio">Início</a></li>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#colecao">Coleção</a></li>
                <li><a href="#instagram">Instagram</a></li>
            </ul>

        </nav>
    </header>


    <!-- =========================
         INÍCIO
    ========================== -->

    <section class="hero" id="inicio">

        <div class="hero-content">

            <small>ESTILO • IDENTIDADE • ATITUDE</small>

            <h1>
                POISON<br>
                <span>STUDIOS</span>
            </h1>

            <p>
                Uma identidade criada para quem transforma
                estilo em presença.
            </p>

            <a href="#colecao" class="hero-button">
                CONHEÇA A COLEÇÃO
            </a>

        </div>

    </section>


    <!-- =========================
         SOBRE
    ========================== -->

    <section class="about" id="sobre">

        <span class="section-label">
            SOBRE A MARCA
        </span>

        <h2>
            Mais que roupa.
        </h2>

        <p>
            A Poison Studios nasceu para representar uma forma
            diferente de enxergar a moda. Uma mistura de atitude,
            personalidade e estética urbana, construída para criar
            uma identidade própria.
        </p>

    </section>


    <!-- =========================
         COLEÇÃO
    ========================== -->

    <section class="collection" id="colecao">

        <div class="collection-header">

            <span class="section-label">
                POISON STUDIOS
            </span>

            <h2>
                Nossa coleção
            </h2>

        </div>


        <div class="collection-grid">

            <!-- CAMISAS -->

            <div class="card">

                <div class="card-content">

                    <div class="card-number">
                        01
                    </div>

                    <h3>
                        CAMISAS
                    </h3>

                    <p>
                        Peças que representam a identidade
                        da Poison Studios.
                    </p>

                </div>

            </div>


            <!-- SHORTS -->

            <div class="card">

                <div class="card-content">

                    <div class="card-number">
                        02
                    </div>

                    <h3>
                        SHORTS
                    </h3>

                    <p>
                        Conforto e personalidade em cada detalhe.
                    </p>

                </div>

            </div>


            <!-- CALÇAS -->

            <div class="card">

                <div class="card-content">

                    <div class="card-number">
                        03
                    </div>

                    <h3>
                        CALÇAS
                    </h3>

                    <p>
                        Uma estética urbana com presença.
                    </p>

                </div>

            </div>


            <!-- MOLETONS -->

            <div class="card">

                <div class="card-content">

                    <div class="card-number">
                        04
                    </div>

                    <h3>
                        MOLETONS
                    </h3>

                    <p>
                        Design marcante para os dias frios.
                    </p>

                </div>

            </div>


            <!-- ACESSÓRIOS -->

            <div class="card">

                <div class="card-content">

                    <div class="card-number">
                        05
                    </div>

                    <h3>
                        ACESSÓRIOS
                    </h3>

                    <p>
                        Os detalhes que completam a identidade.
                    </p>

                </div>

            </div>


            <!-- IDENTIDADE -->

            <div class="card">

                <div class="card-content">

                    <div class="card-number">
                        06
                    </div>

                    <h3>
                        POISON
                    </h3>

                    <p>
                        Uma identidade. Uma presença. Uma marca.
                    </p>

                </div>

            </div>

        </div>

    </section>


    <!-- =========================
         IDENTIDADE
    ========================== -->

    <section class="identity">

        <span class="section-label">
            NOSSA IDENTIDADE
        </span>

        <h2>
            Vista sua presença.
        </h2>

        <div class="identity-line"></div>

        <p>
            A Poison Studios representa atitude, autenticidade
            e liberdade para construir seu próprio estilo.
        </p>

    </section>


    <!-- =========================
         INSTAGRAM
    ========================== -->

    <section class="instagram" id="instagram">

        <span class="section-label">
            ACOMPANHE A MARCA
        </span>

        <h2>
            Instagram
        </h2>

        <p>
            Siga a Poison Studios e acompanhe nossas novidades.
        </p>

        <a
            href="https://www.instagram.com/poison_studios01/"
            target="_blank"
            rel="noopener noreferrer"
        >
            @poison_studios01
        </a>

    </section>


    <!-- =========================
         RODAPÉ
    ========================== -->

    <footer>

        <div class="footer-logo">
            POISON <span>STUDIOS</span>
        </div>

        <p>
            © 2026 Poison Studios. Todos os direitos reservados.
        </p>

    </footer>

</body>
</html>
