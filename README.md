<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Matemáticas - PracticaEjercicios.com</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #4a6fa5;
            --secondary-color: #166088;
            --accent-color: #4cb5f5;
            --light-color: #f8f9fa;
            --dark-color: #343a40;
            --success-color: #28a745;
            --warning-color: #ffc107;
            --danger-color: #dc3545;
            --math-color: #e74c3c;
            --algebra-color: #3498db;
            --geometry-color: #2ecc71;
            --calculus-color: #9b59b6;
            --arithmetic-color: #f39c12;
        }
        
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
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        header {
            background: linear-gradient(135deg, var(--math-color), #c0392b);
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
        }
        
        .logo span {
            color: var(--accent-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 1.5rem;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--accent-color);
        }
        
        .hero {
            background: linear-gradient(rgba(231, 76, 60, 0.8), rgba(192, 57, 43, 0.9)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100"><rect fill="%23e74c3c" width="100" height="100"/><path fill="%23c0392b" d="M0 0L100 100" stroke-width="0"/></svg>');
            background-size: cover;
            color: white;
            padding: 4rem 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: #3a9bd5;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid white;
        }
        
        .btn-outline:hover {
            background: white;
            color: var(--math-color);
        }
        
        .btn-math { background-color: var(--math-color); }
        .btn-math:hover { background-color: #c0392b; }
        .btn-algebra { background-color: var(--algebra-color); }
        .btn-algebra:hover { background-color: #2980b9; }
        .btn-geometry { background-color: var(--geometry-color); }
        .btn-geometry:hover { background-color: #27ae60; }
        .btn-calculus { background-color: var(--calculus-color); }
        .btn-calculus:hover { background-color: #8e44ad; }
        .btn-arithmetic { background-color: var(--arithmetic-color); }
        .btn-arithmetic:hover { background-color: #d35400; }
        
        .topics {
            padding: 4rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--dark-color);
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            margin-bottom: 0.5rem;
        }
        
        .section-title p {
            color: #6c757d;
        }
        
        .topics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .topic-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
            border-top: 5px solid var(--math-color);
        }
        
        .topic-card:hover {
            transform: translateY(-5px);
        }
        
        .topic-card.algebra { border-top-color: var(--algebra-color); }
        .topic-card.geometry { border-top-color: var(--geometry-color); }
        .topic-card.calculus { border-top-color: var(--calculus-color); }
        .topic-card.arithmetic { border-top-color: var(--arithmetic-color); }
        
        .topic-icon {
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: white;
        }
        
        .topic-card.algebra .topic-icon { background: linear-gradient(135deg, var(--algebra-color), #2980b9); }
        .topic-card.geometry .topic-icon { background: linear-gradient(135deg, var(--geometry-color), #27ae60); }
        .topic-card.calculus .topic-icon { background: linear-gradient(135deg, var(--calculus-color), #8e44ad); }
        .topic-card.arithmetic .topic-icon { background: linear-gradient(135deg, var(--arithmetic-color), #d35400); }
        
        .topic-content {
            padding: 1.5rem;
        }
        
        .topic-content h3 {
            margin-bottom: 0.5rem;
            color: var(--dark-color);
        }
        
        .topic-content p {
            color: #6c757d;
            margin-bottom: 1rem;
        }
        
        .exercises {
            padding: 4rem 0;
            background-color: #f8f9fa;
        }
        
        .exercise-tabs {
            display: flex;
            flex-wrap: wrap;
            margin-bottom: 2rem;
            border-bottom: 1px solid #ddd;
        }
        
        .exercise-tab {
            padding: 0.8rem 1.5rem;
            cursor: pointer;
            background-color: #eee;
            margin-right: 0.5rem;
            border-radius: 5px 5px 0 0;
            transition: all 0.3s;
        }
        
        .exercise-tab.active {
            background-color: white;
            border: 1px solid #ddd;
            border-bottom: none;
            color: var(--math-color);
            font-weight: 600;
        }
        
        .exercise-container {
            background-color: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            margin-bottom: 2rem;
            display: none;
        }
        
        .exercise-container.active {
            display: block;
        }
        
        .exercise-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .exercise-title {
            font-size: 1.5rem;
            color: var(--dark-color);
        }
        
        .exercise-progress {
            display: flex;
            align-items: center;
            background-color: #f0f2f5;
            padding: 0.5rem 1rem;
            border-radius: 50px;
        }
        
        .exercise-question {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }
        
        .options-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1rem;
            margin-bottom: 1.5rem;
        }
        
        .option {
            background-color: #f8f9fa;
            padding: 1rem;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            border: 2px solid transparent;
        }
        
        .option:hover {
            border-color: var(--accent-color);
        }
        
        .option.selected {
            border-color: var(--primary-color);
            background-color: #e8f4fd;
        }
        
        .option.correct {
            border-color: var(--success-color);
            background-color: #d4edda;
        }
        
        .option.incorrect {
            border-color: var(--danger-color);
            background-color: #f8d7da;
        }
        
        .input-answer {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
            margin-bottom: 1rem;
        }
        
        .exercise-feedback {
            padding: 1rem;
            border-radius: 8px;
            margin-top: 1rem;
            display: none;
        }
        
        .feedback-correct {
            background-color: #d4edda;
            border-left: 4px solid var(--success-color);
        }
        
        .feedback-incorrect {
            background-color: #f8d7da;
            border-left: 4px solid var(--danger-color);
        }
        
        .subject-page {
            display: none;
            padding: 2rem 0;
        }
        
        .subject-page.active {
            display: block;
        }
        
        .back-button {
            display: inline-flex;
            align-items: center;
            margin-bottom: 2rem;
            color: var(--math-color);
            text-decoration: none;
            font-weight: 600;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            background-color: #f8f9fa;
            transition: all 0.3s;
        }
        
        .back-button:hover {
            background-color: #e9ecef;
        }
        
        .back-button i {
            margin-right: 0.5rem;
        }
        
        .difficulty {
            padding: 4rem 0;
            background-color: white;
        }
        
        .difficulty-cards {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .difficulty-card {
            text-align: center;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }
        
        .difficulty-card:hover {
            transform: translateY(-5px);
        }
        
        .difficulty-basic { border-top: 5px solid var(--success-color); }
        .difficulty-intermediate { border-top: 5px solid var(--warning-color); }
        .difficulty-advanced { border-top: 5px solid var(--math-color); }
        
        .difficulty-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .difficulty-basic .difficulty-icon { color: var(--success-color); }
        .difficulty-intermediate .difficulty-icon { color: var(--warning-color); }
        .difficulty-advanced .difficulty-icon { color: var(--math-color); }
        
        .difficulty-card h3 {
            margin-bottom: 1rem;
            color: var(--dark-color);
        }
        
        .difficulty-card ul {
            list-style: none;
            text-align: left;
            margin-top: 1rem;
            max-height: 200px;
            overflow-y: auto;
        }
        
        .difficulty-card ul li {
            margin-bottom: 0.5rem;
            padding-left: 1.5rem;
            position: relative;
        }
        
        .difficulty-card ul li:before {
            content: "•";
            color: var(--math-color);
            font-weight: bold;
            position: absolute;
            left: 0;
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background-color: white;
            border-radius: 10px;
            width: 100%;
            max-width: 400px;
            padding: 2rem;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.2);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .close-modal {
            font-size: 1.5rem;
            cursor: pointer;
            color: #6c757d;
            background: none;
            border: none;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--dark-color);
        }
        
        .form-group input {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        
        .form-footer {
            text-align: center;
            margin-top: 1.5rem;
        }
        
        .user-menu {
            position: relative;
        }
        
        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--accent-color);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
        
        .user-dropdown {
            position: absolute;
            top: 100%;
            right: 0;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            width: 200px;
            padding: 1rem;
            margin-top: 0.5rem;
            display: none;
        }
        
        .user-dropdown.active {
            display: block;
            animation: fadeIn 0.3s;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }
        
        .user-details {
            margin-left: 0.5rem;
        }
        
        .user-name {
            font-weight: 600;
            color: var(--dark-color);
        }
        
        .user-email {
            font-size: 0.8rem;
            color: #6c757d;
        }
        
        .user-stats {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
        }
        
        .stat {
            text-align: center;
        }
        
        .stat-value {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary-color);
        }
        
        .stat-label {
            font-size: 0.8rem;
            color: #6c757d;
        }
        
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 3rem 0 1rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-column ul li a {
            color: #adb5bd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid #495057;
            color: #adb5bd;
            font-size: 0.9rem;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 1rem;
                justify-content: center;
                flex-wrap: wrap;
            }
            
            nav ul li {
                margin: 0.5rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .topics-grid, .difficulty-cards {
                grid-template-columns: 1fr;
            }
            
            .options-container {
                grid-template-columns: 1fr;
            }
            
            .exercise-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .exercise-progress {
                margin-top: 1rem;
            }
            
            .exercise-tabs {
                flex-direction: column;
            }
            
            .exercise-tab {
                margin-bottom: 0.5rem;
                border-radius: 5px;
            }
            
            .exercise-tab.active {
                border: 1px solid #ddd;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">Practica<span>Ejercicios</span></div>
            <nav>
                <ul>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios/" class="nav-link" data-page="home">Inicio</a></li>
                    <li><a href="#" class="nav-link" data-page="math">Matemáticas</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Lengua-Castellana/">Lenguaje</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" class="nav-link" data-page="science">Ciencias</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" class="nav-link" data-page="social">Sociales</a></li>
                </ul>
            </nav>
            <div class="user-menu">
                <div class="user-avatar" id="userAvatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="user-dropdown" id="userDropdown">
                    <div class="user-info">
                        <div class="user-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="user-details">
                            <div class="user-name" id="userName">Invitado</div>
                            <div class="user-email" id="userEmail">No has iniciado sesión</div>
                        </div>
                    </div>
                    <div class="user-stats">
                        <div class="stat">
                            <div class="stat-value" id="completedExercises">0</div>
                            <div class="stat-label">Completados</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value" id="correctAnswers">0%</div>
                            <div class="stat-label">Precisión</div>
                        </div>
                    </div>
                    <button class="btn btn-math" id="loginBtn">Iniciar Sesión</button>
                </div>
            </div>
        </div>
    </header>

    <main id="main-content">
        <section class="subject-page active" id="home-page">
            <section class="hero">
                <div class="container">
                    <h1>Domina las Matemáticas con Ejercicios Prácticos</h1>
                    <p>Álgebra, geometría, cálculo, aritmética y más. Miles de ejercicios interactivos para todos los niveles.</p>
                    <a href="#" class="btn btn-math nav-link" data-page="math">Comenzar ahora</a>
                    <a href="#" class="btn btn-outline">Ver ejemplos</a>
                </div>
            </section>
            <section class="topics">
                <div class="container">
                    <div class="section-title">
                        <h2>Temas de Matemáticas</h2>
                        <p>Explora nuestros ejercicios por área de matemáticas</p>
                    </div>
                    <div class="topics-grid">
                        <div class="topic-card algebra">
                            <div class="topic-icon">∑</div>
                            <div class="topic-content">
                                <h3>Álgebra</h3>
                                <p>Ecuaciones, polinomios, sistemas de ecuaciones y más.</p>
                                <a href="#" class="btn btn-algebra practice-btn" data-subject="algebra">Practicar</a>
                            </div>
                        </div>
                        <div class="topic-card geometry">
                            <div class="topic-icon">π</div>
                            <div class="topic-content">
                                <h3>Geometría</h3>
                                <p>Ángulos, polígonos, trigonometría y teoremas.</p>
                                <a href="#" class="btn btn-geometry practice-btn" data-subject="geometry">Practicar</a>
                            </div>
                        </div>
                        <div class="topic-card calculus">
                            <div class="topic-icon">∫</div>
                            <div class="topic-content">
                                <h3>Cálculo</h3>
                                <p>Derivadas, integrales, límites y aplicaciones.</p>
                                <a href="#" class="btn btn-calculus practice-btn" data-subject="calculus">Practicar</a>
                            </div>
                        </div>
                        <div class="topic-card arithmetic">
                            <div class="topic-icon">%</div>
                            <div class="topic-content">
                                <h3>Aritmética</h3>
                                <p>Operaciones básicas, fracciones, porcentajes y proporciones.</p>
                                <a href="#" class="btn btn-arithmetic practice-btn" data-subject="arithmetic">Practicar</a>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            <section class="difficulty">
                <div class="container">
                    <div class="section-title">
                        <h2>Ejercicios por Nivel</h2>
                        <p>Selecciona ejercicios según tu nivel de conocimiento</p>
                    </div>
                    <div class="difficulty-cards">
                        <div class="difficulty-card difficulty-basic">
                            <div class="difficulty-icon"><i class="fas fa-star"></i></div>
                            <h3>Nivel Básico</h3>
                            <p>Ejercicios para principiantes y estudiantes de primaria</p>
                            <ul>
                                <li>Operaciones básicas</li>
                                <li>Problemas sencillos de álgebra</li>
                                <li>Geometría elemental</li>
                                <li>Fracciones y decimales</li>
                            </ul>
                            <a href="#" class="btn">Comenzar</a>
                        </div>
                        <div class="difficulty-card difficulty-intermediate">
                            <div class="difficulty-icon"><i class="fas fa-star-half-alt"></i></div>
                            <h3>Nivel Intermedio</h3>
                            <p>Ejercicios para estudiantes de secundaria</p>
                            <ul>
                                <li>Ecuaciones de primer y segundo grado</li>
                                <li>Geometría analítica</li>
                                <li>Trigonometría básica</li>
                                <li>Estadística y probabilidad</li>
                            </ul>
                            <a href="#" class="btn">Comenzar</a>
                        </div>
                        <div class="difficulty-card difficulty-advanced">
                            <div class="difficulty-icon"><i class="fas fa-stars"></i></div>
                            <h3>Nivel Avanzado</h3>
                            <p>Ejercicios para bachillerato y universidad</p>
                            <ul>
                                <li>Cálculo diferencial e integral</li>
                                <li>Álgebra lineal</li>
                                <li>Geometría avanzada</li>
                                <li>Ecuaciones diferenciales</li>
                            </ul>
                            <a href="#" class="btn">Comenzar</a>
                        </div>
                    </div>
                </div>
            </section>
        </section>
        <section class="subject-page" id="math-page">
            <div class="container">
                <a href="https://ayoubelouardy.github.io/Practicaejercicios/" class="back-button nav-link" data-page="home"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Matemáticas</h2>
                    <p>Selecciona un área de matemáticas para practicar</p>
                </div>
                <div class="topics-grid">
                    <div class="topic-card algebra">
                        <div class="topic-icon">∑</div>
                        <div class="topic-content">
                            <h3>Álgebra</h3>
                            <p>Ecuaciones, polinomios, sistemas de ecuaciones y más.</p>
                            <a href="#" class="btn btn-algebra practice-btn" data-subject="algebra">Practicar</a>
                        </div>
                    </div>
                    <div class="topic-card geometry">
                        <div class="topic-icon">π</div>
                        <div class="topic-content">
                            <h3>Geometría</h3>
                            <p>Ángulos, polígonos, trigonometría y teoremas.</p>
                            <a href="#" class="btn btn-geometry practice-btn" data-subject="geometry">Practicar</a>
                        </div>
                    </div>
                    <div class="topic-card calculus">
                        <div class="topic-icon">∫</div>
                        <div class="topic-content">
                            <h3>Cálculo</h3>
                            <p>Derivadas, integrales, límites y aplicaciones.</p>
                            <a href="#" class="btn btn-calculus practice-btn" data-subject="calculus">Practicar</a>
                        </div>
                    </div>
                    <div class="topic-card arithmetic">
                        <div class="topic-icon">%</div>
                        <div class="topic-content">
                            <h3>Aritmética</h3>
                            <p>Operaciones básicas, fracciones, porcentajes y proporciones.</p>
                            <a href="#" class="btn btn-arithmetic practice-btn" data-subject="arithmetic">Practicar</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="algebra-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="math"><i class="fas fa-arrow-left"></i> Volver a Matemáticas</a>
                <div class="section-title">
                    <h2>Álgebra</h2>
                    <p>Practica con más de 50 ejercicios de álgebra de diferentes niveles</p>
                </div>
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="algebra-basic">Básico</div>
                    <div class="exercise-tab" data-tab="algebra-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="algebra-advanced">Avanzado</div>
                </div>
                <div class="exercise-container active" id="algebra-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Básica: Ecuaciones Lineales</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-algebra check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-algebra next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="algebra-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Intermedia: Sistemas de Ecuaciones</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-algebra check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-algebra next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="algebra-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Avanzada: Ecuaciones Cuadráticas</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-algebra check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-algebra next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="geometry-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="math"><i class="fas fa-arrow-left"></i> Volver a Matemáticas</a>
                <div class="section-title">
                    <h2>Geometría</h2>
                    <p>Practica con más de 50 ejercicios de geometría de diferentes niveles</p>
                </div>
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="geometry-basic">Básico</div>
                    <div class="exercise-tab" data-tab="geometry-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="geometry-advanced">Avanzado</div>
                </div>
                <div class="exercise-container active" id="geometry-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Geometría Básica: Área de Figuras</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-geometry check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-geometry next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="geometry-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Geometría Intermedia: Teorema de Pitágoras</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-geometry check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-geometry next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="geometry-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Geometría Avanzada: Trigonometría</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-geometry check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-geometry next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="calculus-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="math"><i class="fas fa-arrow-left"></i> Volver a Matemáticas</a>
                <div class="section-title">
                    <h2>Cálculo</h2>
                    <p>Practica con más de 50 ejercicios de cálculo de diferentes niveles</p>
                </div>
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="calculus-basic">Básico</div>
                    <div class="exercise-tab" data-tab="calculus-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="calculus-advanced">Avanzado</div>
                </div>
                <div class="exercise-container active" id="calculus-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Cálculo Básico: Derivadas</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <input type="text" class="input-answer" placeholder="Escribe tu respuesta aquí">
                    <button class="btn btn-calculus check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-calculus next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="calculus-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Cálculo Intermedio: Integrales</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <input type="text" class="input-answer" placeholder="Escribe tu respuesta aquí">
                    <button class="btn btn-calculus check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-calculus next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="calculus-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Cálculo Avanzado: Límites</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-calculus check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-calculus next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="arithmetic-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="math"><i class="fas fa-arrow-left"></i> Volver a Matemáticas</a>
                <div class="section-title">
                    <h2>Aritmética</h2>
                    <p>Practica con más de 50 ejercicios de aritmética de diferentes niveles</p>
                </div>
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="arithmetic-basic">Básico</div>
                    <div class="exercise-tab" data-tab="arithmetic-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="arithmetic-advanced">Avanzado</div>
                </div>
                <div class="exercise-container active" id="arithmetic-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Aritmética Básica: Fracciones</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-arithmetic check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-arithmetic next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="arithmetic-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Aritmética Intermedia: Porcentajes</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-arithmetic check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-arithmetic next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="arithmetic-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Aritmética Avanzada: Proporciones</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-arithmetic check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-arithmetic next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="language-page">
            <div class="container">
                <a href="https://ayoubelouardy.github.io/Practicaejercicios/" class="back-button nav-link" data-page="home"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Lenguaje</h2>
                    <p>Próximamente: Ejercicios de lenguaje</p>
                </div>
            </div>
        </section>
        <section class="subject-page" id="science-page">
            <div class="container">
                <a href="https://ayoubelouardy.github.io/Practicaejercicios/" class="back-button nav-link" data-page="home"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Ciencias</h2>
                    <p>Próximamente: Ejercicios de ciencias</p>
                </div>
            </div>
        </section>
        <section class="subject-page" id="social-page">
            <div class="container">
                <a href="https://ayoubelouardy.github.io/Practicaejercicios/" class="back-button nav-link" data-page="home"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Sociales</h2>
                    <p>Próximamente: Ejercicios de sociales</p>
                </div>
            </div>
        </section>
    </main>

    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Iniciar Sesión</h2>
                <button class="close-modal">&times;</button>
            </div>
            <form id="loginForm">
                <div class="form-group">
                    <label for="email">Correo electrónico</label>
                    <input type="email" id="email" required placeholder="tu@email.com">
                </div>
                <div class="form-group">
                    <label for="password">Contraseña</label>
                    <input type="password" id="password" required placeholder="Tu contraseña">
                </div>
                <button type="submit" class="btn btn-math">Iniciar Sesión</button>
                <div class="form-footer">
                    <p>¿No tienes cuenta? <a href="#" id="registerLink">Regístrate aquí</a></p>
                </div>
            </form>
        </div>
    </div>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>PracticaEjercicios</h3>
                    <p>Plataforma educativa con miles de ejercicios gratuitos para estudiantes de todos los niveles.</p>
                </div>
                <div class="footer-column">
                    <h3>Enlaces rápidos</h3>
                    <ul>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios/" class="nav-link" data-page="home">Inicio</a></li>
                        <li><a href="#" class="nav-link" data-page="math">Matemáticas</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Lengua-Castellana/">Lenguaje</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" class="nav-link" data-page="science">Ciencias</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" class="nav-link" data-page="social">Sociales</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Matemáticas</h3>
                    <ul>
                        <li><a href="#" class="practice-btn" data-subject="algebra">Álgebra</a></li>
                        <li><a href="#" class="practice-btn" data-subject="geometry">Geometría</a></li>
                        <li><a href="#" class="practice-btn" data-subject="calculus">Cálculo</a></li>
                        <li><a href="#" class="practice-btn" data-subject="arithmetic">Aritmética</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contacto</h3>
                    <ul>
                        <li><i class="fas fa-envelope"></i> info@practicaejercicios.com</li>
                        <li><i class="fas fa-phone"></i> +34 912 345 678</li>
                        <li><i class="fas fa-map-marker-alt"></i> Madrid, España</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 PracticaEjercicios.com - Todos los derechos reservados</p>
            </div>
        </div>
    </footer>

    <script>
        // User data (simulated)
        let userData = {
            loggedIn: false,
            name: "Invitado",
            email: "",
            completedExercises: 0,
            correctAnswers: 0,
            totalAnswers: 0
        };

        // Generadores de ejercicios únicos
        function generateAlgebraBasicExercise(id) {
            const a = Math.floor(Math.random() * 10) + 1; // Coeficiente de x
            const b = Math.floor(Math.random() * 20) - 10; // Término constante
            const c = Math.floor(Math.random() * 20) - 10; // Resultado
            const x = (c - b) / a; // Solución
            if (!Number.isInteger(x) || x < -10 || x > 10) return generateAlgebraBasicExercise(id); // Asegurar solución entera razonable
            const question = `Resuelve la ecuación: <strong>${a}x ${b >= 0 ? '+' : ''} ${b} = ${c}</strong>`;
            const correctAnswer = `x = ${x}`;
            const options = [
                { text: correctAnswer, correct: true },
                { text: `x = ${x + Math.floor(Math.random() * 4) - 2}`, correct: false },
                { text: `x = ${x + Math.floor(Math.random() * 4) - 2}`, correct: false },
                { text: `x = ${x + Math.floor(Math.random() * 4) - 2}`, correct: false }
            ].sort(() => Math.random() - 0.5); // Mezclar opciones
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! La solución es ${correctAnswer}.`,
                feedbackIncorrect: `Incorrecto. La solución correcta es ${correctAnswer}.`
            };
        }

        function generateAlgebraIntermediateExercise(id) {
            const a1 = Math.floor(Math.random() * 5) + 1;
            const b1 = Math.floor(Math.random() * 5) + 1;
            const c1 = Math.floor(Math.random() * 10) + 1;
            const a2 = Math.floor(Math.random() * 5) + 1;
            const b2 = Math.floor(Math.random() * 5) + 1;
            const c2 = Math.floor(Math.random() * 10) + 1;
            const det = a1 * b2 - a2 * b1;
            if (det === 0) return generateAlgebraIntermediateExercise(id); // Evitar sistemas sin solución única
            const x = (c1 * b2 - c2 * b1) / det;
            const y = (a1 * c2 - a2 * c1) / det;
            if (!Number.isInteger(x) || !Number.isInteger(y) || Math.abs(x) > 10 || Math.abs(y) > 10) return generateAlgebraIntermediateExercise(id); // Soluciones enteras
            const question = `Resuelve el sistema: <strong>${a1}x + ${b1}y = ${c1}, ${a2}x + ${b2}y = ${c2}</strong>`;
            const correctAnswer = `x = ${x}, y = ${y}`;
            const options = [
                { text: correctAnswer, correct: true },
                { text: `x = ${x + 1}, y = ${y - 1}`, correct: false },
                { text: `x = ${x - 1}, y = ${y + 1}`, correct: false },
                { text: `x = ${x + 2}, y = ${y - 2}`, correct: false }
            ].sort(() => Math.random() - 0.5);
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! La solución es ${correctAnswer}.`,
                feedbackIncorrect: `Incorrecto. La solución correcta es ${correctAnswer}.`
            };
        }

        function generateAlgebraAdvancedExercise(id) {
            const a = Math.floor(Math.random() * 5) + 1;
            const b = Math.floor(Math.random() * 10) - 5;
            const c = Math.floor(Math.random() * 10) - 5;
            const discriminant = b * b - 4 * a * c;
            if (discriminant < 0) return generateAlgebraAdvancedExercise(id); // Evitar raíces complejas
            const x1 = (-b + Math.sqrt(discriminant)) / (2 * a);
            const x2 = (-b - Math.sqrt(discriminant)) / (2 * a);
            if (!Number.isInteger(x1) || !Number.isInteger(x2)) return generateAlgebraAdvancedExercise(id); // Soluciones enteras
            const question = `Resuelve: <strong>${a}x² ${b >= 0 ? '+' : ''} ${b}x ${c >= 0 ? '+' : ''} ${c} = 0</strong>`;
            const correctAnswer = `x = ${x1}, x = ${x2}`;
            const options = [
                { text: correctAnswer, correct: true },
                { text: `x = ${x1 + 1}, x = ${x2 - 1}`, correct: false },
                { text: `x = ${x1 - 1}, x = ${x2 + 1}`, correct: false },
                { text: `x = ${x1}, x = ${x2 + 2}`, correct: false }
            ].sort(() => Math.random() - 0.5);
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! Las soluciones son ${correctAnswer}.`,
                feedbackIncorrect: `Incorrecto. Las soluciones correctas son ${correctAnswer}.`
            };
        }

        function generateGeometryBasicExercise(id) {
            const type = Math.random() < 0.5 ? 'triangle' : 'circle';
            if (type === 'triangle') {
                const base = Math.floor(Math.random() * 10) + 2;
                const height = Math.floor(Math.random() * 10) + 2;
                const area = (base * height) / 2;
                const question = `Calcula el área de un triángulo con base de ${base} cm y altura de ${height} cm`;
                const options = [
                    { text: `${area} cm²`, correct: true },
                    { text: `${area + Math.floor(Math.random() * 10)} cm²`, correct: false },
                    { text: `${area - Math.floor(Math.random() * 5)} cm²`, correct: false },
                    { text: `${(base * height)} cm²`, correct: false }
                ].sort(() => Math.random() - 0.5);
                return {
                    id,
                    question,
                    options,
                    feedbackCorrect: `¡Correcto! El área es ${area} cm².`,
                    feedbackIncorrect: `Incorrecto. El área del triángulo es base × altura / 2 = ${area} cm².`
                };
            } else {
                const radius = Math.floor(Math.random() * 10) + 1;
                const area = 3.14 * radius * radius;
                const question = `Calcula el área de un círculo con radio de ${radius} cm (usa π = 3.14)`;
                const options = [
                    { text: `${area.toFixed(2)} cm²`, correct: true },
                    { text: `${(area + Math.random() * 10).toFixed(2)} cm²`, correct: false },
                    { text: `${(area - Math.random() * 5).toFixed(2)} cm²`, correct: false },
                    { text: `${(3.14 * radius).toFixed(2)} cm²`, correct: false }
                ].sort(() => Math.random() - 0.5);
                return {
                    id,
                    question,
                    options,
                    feedbackCorrect: `¡Correcto! El área es ${area.toFixed(2)} cm².`,
                    feedbackIncorrect: `Incorrecto. El área del círculo es πr² = ${area.toFixed(2)} cm².`
                };
            }
        }

        function generateGeometryIntermediateExercise(id) {
            const a = Math.floor(Math.random() * 10) + 2;
            const b = Math.floor(Math.random() * 10) + 2;
            const c = Math.sqrt(a * a + b * b);
            if (!Number.isInteger(c)) return generateGeometryIntermediateExercise(id); // Solución entera
            const question = `En un triángulo rectángulo, los catetos miden ${a} cm y ${b} cm. Calcula la hipotenusa.`;
            const options = [
                { text: `${c} cm`, correct: true },
                { text: `${c + Math.floor(Math.random() * 3)} cm`, correct: false },
                { text: `${c - Math.floor(Math.random() * 3)} cm`, correct: false },
                { text: `${a + b} cm`, correct: false }
            ].sort(() => Math.random() - 0.5);
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! La hipotenusa es ${c} cm.`,
                feedbackIncorrect: `Incorrecto. Usa el teorema de Pitágoras: a² + b² = c².`
            };
        }

        function generateGeometryAdvancedExercise(id) {
            const angles = [30, 45, 60];
            const angle = angles[Math.floor(Math.random() * angles.length)];
            const func = Math.random() < 0.5 ? 'sin' : 'cos';
            const value = func === 'sin' ? 
                (angle === 30 ? '1/2' : angle === 45 ? '√2/2' : '√3/2') : 
                (angle === 30 ? '√3/2' : angle === 45 ? '√2/2' : '1/2');
            const question = `Calcula el ${func} de ${angle}°.`;
            const options = [
                { text: value, correct: true },
                { text: ['1/2', '√3/2', '√2/2', '1', '0'].filter(v => v !== value)[Math.floor(Math.random() * 4)], correct: false },
                { text: ['1/2', '√3/2', '√2/2', '1', '0'].filter(v => v !== value)[Math.floor(Math.random() * 3)], correct: false },
                { text: '0', correct: false }
            ].sort(() => Math.random() - 0.5);
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! El valor es ${value}.`,
                feedbackIncorrect: `Incorrecto. El valor correcto es ${value}.`
            };
        }

        function generateCalculusBasicExercise(id) {
            const a = Math.floor(Math.random() * 5) + 1;
            const b = Math.floor(Math.random() * 5) + 1;
            const c = Math.floor(Math.random() * 10) - 5;
            const question = `Calcula la derivada de f(x) = ${a}x² ${b >= 0 ? '+' : ''} ${b}x ${c >= 0 ? '+' : ''} ${c}`;
            const answer = `${2 * a}x ${b >= 0 ? '+' : ''} ${b}`;
            return {
                id,
                question,
                answer,
                feedbackCorrect: `¡Correcto! La derivada es ${answer}.`,
                feedbackIncorrect: `Incorrecto. La derivada correcta es ${answer}.`
            };
        }

        function generateCalculusIntermediateExercise(id) {
            const a = Math.floor(Math.random() * 5) + 1;
            const n = Math.floor(Math.random() * 3) + 2; // Exponente entre 2 y 4
            const question = `Calcula la integral de f(x) = ${a}x^${n}`;
            const answer = `${(a / (n + 1)).toFixed(2)}x^${n + 1} + C`;
            return {
                id,
                question,
                answer,
                feedbackCorrect: `¡Correcto! La integral es ${answer}.`,
                feedbackIncorrect: `Incorrecto. La integral correcta es ${answer}.`
            };
        }

        function generateCalculusAdvancedExercise(id) {
            const type = Math.random() < 0.5 ? 'sin' : 'cos';
            const question = `Calcula el límite: lim(x→0) (${type === 'sin' ? 'sin(x)/x' : '(1 - cos(x))/x²'})`;
            const options = type === 'sin' ? [
                { text: '1', correct: true },
                { text: '0', correct: false },
                { text: '∞', correct: false },
                { text: 'No existe', correct: false }
            ] : [
                { text: '1/2', correct: true },
                { text: '1', correct: false },
                { text: '0', correct: false },
                { text: 'No existe', correct: false }
            ].sort(() => Math.random() - 0.5);
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! El límite es ${type === 'sin' ? '1' : '1/2'}.`,
                feedbackIncorrect: `Incorrecto. El límite correcto es ${type === 'sin' ? '1' : '1/2'}.`
            };
        }

        function generateArithmeticBasicExercise(id) {
            const num = Math.floor(Math.random() * 50) + 10;
            const den = Math.floor(Math.random() * 50) + 10;
            const gcd = (a, b) => b ? gcd(b, a % b) : a;
            const divisor = gcd(num, den);
            const question = `Simplifica la fracción: ${num}/${den}`;
            const simplified = `${num / divisor}/${den / divisor}`;
            const options = [
                { text: simplified, correct: true },
                { text: `${num}/${den - 1}`, correct: false },
                { text: `${num - 1}/${den}`, correct: false },
                { text: `${num + 1}/${den + 1}`, correct: false }
            ].sort(() => Math.random() - 0.5);
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! La fracción simplificada es ${simplified}.`,
                feedbackIncorrect: `Incorrecto. El máximo común divisor da ${simplified}.`
            };
        }

        function generateArithmeticIntermediateExercise(id) {
            const percent = Math.floor(Math.random() * 50) + 10;
            const total = Math.floor(Math.random() * 100) + 50;
            const result = (percent / 100) * total;
            const question = `¿Cuánto es el ${percent}% de ${total}?`;
            const options = [
                { text: result.toFixed(2), correct: true },
                { text: (result + Math.random() * 10).toFixed(2), correct: false },
                { text: (result - Math.random() * 10).toFixed(2), correct: false },
                { text: (result + Math.random() * 5).toFixed(2), correct: false }
            ].sort(() => Math.random() - 0.5);
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! El resultado es ${result.toFixed(2)}.`,
                feedbackIncorrect: `Incorrecto. Calcula: (${percent}/100) × ${total} = ${result.toFixed(2)}.`
            };
        }

        function generateArithmeticAdvancedExercise(id) {
            const quantity = Math.floor(Math.random() * 10) + 1;
            const cost = Math.floor(Math.random() * 20) + 5;
            const newQuantity = Math.floor(Math.random() * 10) + 1;
            const newCost = (cost / quantity) * newQuantity;
            if (!Number.isInteger(newCost)) return generateArithmeticAdvancedExercise(id); // Solución entera
            const question = `Si ${quantity} kg de frutas cuestan $${cost}, ¿cuánto cuestan ${newQuantity} kg?`;
            const options = [
                { text: `$${newCost}`, correct: true },
                { text: `$${(newCost + Math.floor(Math.random() * 5))}`, correct: false },
                { text: `$${(newCost - Math.floor(Math.random() * 5))}`, correct: false },
                { text: `$${(cost + newQuantity)}`, correct: false }
            ].sort(() => Math.random() - 0.5);
            return {
                id,
                question,
                options,
                feedbackCorrect: `¡Correcto! El costo es $${newCost}.`,
                feedbackIncorrect: `Incorrecto. Usa la proporción: (${cost}/${quantity}) × ${newQuantity} = $${newCost}.`
            };
        }

        // Nueva constante exercises con 50 ejercicios únicos por categoría y nivel
        const exercises = {
            algebra: {
                basic: Array.from({ length: 50 }, (_, i) => generateAlgebraBasicExercise(i + 1)),
                intermediate: Array.from({ length: 50 }, (_, i) => generateAlgebraIntermediateExercise(i + 1)),
                advanced: Array.from({ length: 50 }, (_, i) => generateAlgebraAdvancedExercise(i + 1))
            },
            geometry: {
                basic: Array.from({ length: 50 }, (_, i) => generateGeometryBasicExercise(i + 1)),
                intermediate: Array.from({ length: 50 }, (_, i) => generateGeometryIntermediateExercise(i + 1)),
                advanced: Array.from({ length: 50 }, (_, i) => generateGeometryAdvancedExercise(i + 1))
            },
            calculus: {
                basic: Array.from({ length: 50 }, (_, i) => generateCalculusBasicExercise(i + 1)),
                intermediate: Array.from({ length: 50 }, (_, i) => generateCalculusIntermediateExercise(i + 1)),
                advanced: Array.from({ length: 50 }, (_, i) => generateCalculusAdvancedExercise(i + 1))
            },
            arithmetic: {
                basic: Array.from({ length: 50 }, (_, i) => generateArithmeticBasicExercise(i + 1)),
                intermediate: Array.from({ length: 50 }, (_, i) => generateArithmeticIntermediateExercise(i + 1)),
                advanced: Array.from({ length: 50 }, (_, i) => generateArithmeticAdvancedExercise(i + 1))
            }
        };

        // Navigation handling
        function showPage(pageId) {
            document.querySelectorAll('.subject-page').forEach(page => {
                page.classList.remove('active');
            });
            document.querySelector(`#${pageId}-page`).classList.add('active');
            // Initialize exercises for subject pages
            if (['algebra', 'geometry', 'calculus', 'arithmetic'].includes(pageId)) {
                showSubject(pageId);
            }
        }

        function showSubject(subject) {
            showPage(subject);
            const defaultTab = document.querySelector(`#${subject}-page .exercise-tab.active`);
            if (defaultTab) {
                const tabId = defaultTab.dataset.tab;
                showExerciseTab(subject, tabId);
            }
        }

        function showExerciseTab(subject, tabId) {
            const page = document.querySelector(`#${subject}-page`);
            page.querySelectorAll('.exercise-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            page.querySelectorAll('.exercise-container').forEach(container => {
                container.classList.remove('active');
            });
            page.querySelector(`[data-tab="${tabId}"]`).classList.add('active');
            const container = page.querySelector(`#${tabId}-exercises`);
            container.classList.add('active');
            loadExercise(subject, tabId.split('-')[1], 1); // Load first exercise
        }

        function loadExercise(subject, level, exerciseId) {
            const exercise = exercises[subject][level].find(ex => ex.id === exerciseId);
            const container = document.querySelector(`#${subject}-page #${subject}-${level}-exercises`);
            container.querySelector('.exercise-counter').textContent = exerciseId;
            container.querySelector('.exercise-question').innerHTML = exercise.question;
            container.querySelector('.feedback-correct').textContent = exercise.feedbackCorrect;
            container.querySelector('.feedback-incorrect').textContent = exercise.feedbackIncorrect;
            
            const optionsContainer = container.querySelector('.options-container');
            const inputAnswer = container.querySelector('.input-answer');
            if (exercise.options) {
                optionsContainer.style.display = 'grid';
                if (inputAnswer) inputAnswer.style.display = 'none';
                optionsContainer.innerHTML = exercise.options.map(opt => 
                    `<div class="option" data-correct="${opt.correct}">${opt.text}</div>`
                ).join('');
            } else {
                optionsContainer.style.display = 'none';
                if (inputAnswer) {
                    inputAnswer.style.display = 'block';
                    inputAnswer.value = '';
                }
            }
            
            container.querySelector('.check-answer-btn').style.display = 'block';
            container.querySelector('.next-question-btn').style.display = 'none';
            container.querySelectorAll('.exercise-feedback').forEach(fb => {
                fb.style.display = 'none';
            });
            container.querySelectorAll('.option').forEach(opt => {
                opt.classList.remove('selected', 'correct', 'incorrect');
            });
        }

        // Event listeners
        document.addEventListener('DOMContentLoaded', () => {
            // Initialize home page
            showPage('home');

            // Navigation links
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const page = link.dataset.page;
                    if (['home', 'science', 'social'].includes(page)) {
                        window.location.href = link.getAttribute('href');
                    } else {
                        showPage(page);
                    }
                });
            });

            // Subject practice buttons
            document.querySelectorAll('.practice-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.preventDefault();
                    const subject = btn.dataset.subject;
                    showSubject(subject);
                });
            });

            // Exercise tabs
            document.querySelectorAll('.exercise-tab').forEach(tab => {
                tab.addEventListener('click', (e) => {
                    e.preventDefault();
                    const subject = tab.closest('.subject-page').id.split('-')[0];
                    const tabId = tab.dataset.tab;
                    showExerciseTab(subject, tabId);
                });
            });

            // Check answer buttons
            document.querySelectorAll('.check-answer-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    const container = btn.closest('.exercise-container');
                    const subject = container.closest('.subject-page').id.split('-')[0];
                    const level = container.id.split('-')[1];
                    const exerciseId = parseInt(container.querySelector('.exercise-counter').textContent);
                    const exercise = exercises[subject][level].find(ex => ex.id === exerciseId);
                    
                    let isCorrect = false;
                    if (exercise.options) {
                        const selectedOption = container.querySelector('.option.selected');
                        isCorrect = selectedOption && selectedOption.dataset.correct === 'true';
                    } else {
                        const input = container.querySelector('.input-answer');
                        isCorrect = input && input.value.trim() === exercise.answer;
                    }
                    
                    container.querySelector(isCorrect ? '.feedback-correct' : '.feedback-incorrect').style.display = 'block';
                    container.querySelector(isCorrect ? '.feedback-incorrect' : '.feedback-correct').style.display = 'none';
                    container.querySelector('.check-answer-btn').style.display = 'none';
                    container.querySelector('.next-question-btn').style.display = 'block';
                    
                    if (exercise.options) {
                        container.querySelectorAll('.option').forEach(opt => {
                            opt.classList.add(opt.dataset.correct === 'true' ? 'correct' : 'incorrect');
                        });
                    }
                    
                    userData.completedExercises++;
                    userData.totalAnswers++;
                    if (isCorrect) userData.correctAnswers++;
                    updateUserStats();
                });
            });

            // Option selection
            document.querySelectorAll('.options-container').forEach(container => {
                container.addEventListener('click', (e) => {
                    if (e.target.classList.contains('option')) {
                        container.querySelectorAll('.option').forEach
