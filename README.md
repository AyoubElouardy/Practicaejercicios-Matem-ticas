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
        
        /* Header Styles */
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
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(231, 76, 60, 0.8), rgba(192, 57, 43, 0.9)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect fill="%23e74c3c" width="100" height="100"/><path fill="%23c0392b" d="M0 0L100 100" stroke-width="0"/></svg>');
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
        
        .btn-math {
            background-color: var(--math-color);
        }
        
        .btn-math:hover {
            background-color: #c0392b;
        }
        
        .btn-algebra {
            background-color: var(--algebra-color);
        }
        
        .btn-algebra:hover {
            background-color: #2980b9;
        }
        
        .btn-geometry {
            background-color: var(--geometry-color);
        }
        
        .btn-geometry:hover {
            background-color: #27ae60;
        }
        
        .btn-calculus {
            background-color: var(--calculus-color);
        }
        
        .btn-calculus:hover {
            background-color: #8e44ad;
        }
        
        .btn-arithmetic {
            background-color: var(--arithmetic-color);
        }
        
        .btn-arithmetic:hover {
            background-color: #d35400;
        }
        
        /* Math Topics Section */
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
        
        .topic-card.algebra {
            border-top-color: var(--algebra-color);
        }
        
        .topic-card.geometry {
            border-top-color: var(--geometry-color);
        }
        
        .topic-card.calculus {
            border-top-color: var(--calculus-color);
        }
        
        .topic-card.arithmetic {
            border-top-color: var(--arithmetic-color);
        }
        
        .topic-icon {
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: white;
        }
        
        .topic-card.algebra .topic-icon {
            background: linear-gradient(135deg, var(--algebra-color), #2980b9);
        }
        
        .topic-card.geometry .topic-icon {
            background: linear-gradient(135deg, var(--geometry-color), #27ae60);
        }
        
        .topic-card.calculus .topic-icon {
            background: linear-gradient(135deg, var(--calculus-color), #8e44ad);
        }
        
        .topic-card.arithmetic .topic-icon {
            background: linear-gradient(135deg, var(--arithmetic-color), #d35400);
        }
        
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
        
        /* Exercise Section */
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
        
        .exercise-navigation {
            display: flex;
            justify-content: space-between;
            margin-top: 2rem;
        }
        
        /* Subject Page */
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
        
        /* Exercise List */
        .exercise-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .exercise-item {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
            cursor: pointer;
            border-left: 4px solid var(--algebra-color);
        }
        
        .exercise-item.geometry {
            border-left-color: var(--geometry-color);
        }
        
        .exercise-item.calculus {
            border-left-color: var(--calculus-color);
        }
        
        .exercise-item.arithmetic {
            border-left-color: var(--arithmetic-color);
        }
        
        .exercise-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .exercise-item h3 {
            margin-bottom: 0.5rem;
            color: var(--dark-color);
        }
        
        .exercise-item p {
            color: #6c757d;
            margin-bottom: 1rem;
        }
        
        .exercise-meta {
            display: flex;
            justify-content: space-between;
            color: #6c757d;
            font-size: 0.9rem;
        }
        
        /* Difficulty Section */
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
        
        .difficulty-basic {
            border-top: 5px solid var(--success-color);
        }
        
        .difficulty-intermediate {
            border-top: 5px solid var(--warning-color);
        }
        
        .difficulty-advanced {
            border-top: 5px solid var(--math-color);
        }
        
        .difficulty-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .difficulty-basic .difficulty-icon {
            color: var(--success-color);
        }
        
        .difficulty-intermediate .difficulty-icon {
            color: var(--warning-color);
        }
        
        .difficulty-advanced .difficulty-icon {
            color: var(--math-color);
        }
        
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
        
        /* Login Modal */
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
        
        /* User Profile */
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
            cursor: pointer;
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
        
        /* Footer */
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
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        /* Responsive Design */
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
            
            .topics-grid, .difficulty-cards, .exercise-list {
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
            
            .exercise-navigation {
                flex-direction: column;
                gap: 1rem;
            }
            
            .exercise-navigation .btn {
                width: 100%;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">Practica<span>Ejercicios</span></div>
            <nav>
                <ul>
                    <li><a href="#" class="nav-link" data-page="home">Inicio</a></li>
                    <li><a href="#" class="nav-link" data-page="math">Matemáticas</a></li>
                    <li><a href="#">Lenguaje</a></li>
                    <li><a href="#">Ciencias</a></li>
                    <li><a href="#">Sociales</a></li>
                </ul>
            </nav>
            <div class="user-menu">
                <div class="user-avatar" id="userAvatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="user-dropdown" id="userDropdown">
                    <div class="user-info" id="userInfo">
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
                    <button class="btn btn-math" id="loginBtn" style="width: 100%;">Iniciar Sesión</button>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content Area -->
    <main id="main-content">
        <!-- Home Page -->
        <section class="subject-page active" id="home-page">
            <!-- Hero Section -->
            <section class="hero">
                <div class="container">
                    <h1>Domina las Matemáticas con Ejercicios Prácticos</h1>
                    <p>Álgebra, geometría, cálculo, aritmética y más. Miles de ejercicios interactivos para todos los niveles.</p>
                    <a href="#" class="btn btn-math nav-link" data-page="math">Comenzar ahora</a>
                    <a href="#" class="btn btn-outline" style="margin-left: 10px;">Ver ejemplos</a>
                </div>
            </section>

            <!-- Math Topics Section -->
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

            <!-- Difficulty Section -->
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
                                <li>Números enteros</li>
                                <li>Potenciación básica</li>
                                <li>Problemas de suma y resta</li>
                                <li>Cálculo de perímetros</li>
                                <li>Tablas de multiplicar</li>
                                <li>Problemas con dinero</li>
                            </ul>
                            <a href="#" class="btn" style="margin-top: 1.5rem;">Comenzar</a>
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
                                <li>Sistemas de ecuaciones</li>
                                <li>Logaritmos</li>
                                <li>Polinomios</li>
                                <li>Funciones lineales y cuadráticas</li>
                                <li>Teorema de Pitágoras</li>
                                <li>Razones trigonométricas</li>
                            </ul>
                            <a href="#" class="btn" style="margin-top: 1.5rem;">Comenzar</a>
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
                                <li>Variable compleja</li>
                                <li>Análisis numérico</li>
                                <li>Topología</li>
                                <li>Teoría de números</li>
                                <li>Geometría diferencial</li>
                                <li>Análisis funcional</li>
                            </ul>
                            <a href="#" class="btn" style="margin-top: 1.5rem;">Comenzar</a>
                        </div>
                    </div>
                </div>
            </section>
        </section>

        <!-- Math Main Page -->
        <section class="subject-page" id="math-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="home"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                
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

        <!-- Algebra Page -->
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
                
                <!-- Algebra Basic Exercises -->
                <div class="exercise-container active" id="algebra-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Básica: Ecuaciones Lineales</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Resuelve la siguiente ecuación para x: <strong>2x + 5 = 13</strong></p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="false">x = 3</div>
                        <div class="option" data-correct="false">x = 5</div>
                        <div class="option" data-correct="true">x = 4</div>
                        <div class="option" data-correct="false">x = 6</div>
                    </div>
                    
                    <button class="btn btn-algebra check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-algebra next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! Has resuelto bien la ecuación.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. La solución correcta es x = 4.</p>
                    </div>
                </div>
                
                <!-- Algebra Intermediate Exercises -->
                <div class="exercise-container" id="algebra-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Intermedia: Sistemas de Ecuaciones</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Resuelve el siguiente sistema de ecuaciones: <strong>2x + y = 5</strong> y <strong>x - y = 1</strong></p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="true">x = 2, y = 1</div>
                        <div class="option" data-correct="false">x = 1, y = 2</div>
                        <div class="option" data-correct="false">x = 3, y = -1</div>
                        <div class="option" data-correct="false">x = 0, y = 5</div>
                    </div>
                    
                    <button class="btn btn-algebra check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-algebra next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! La solución es x = 2, y = 1.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. La solución correcta es x = 2, y = 1.</p>
                    </div>
                </div>
                
                <!-- Algebra Advanced Exercises -->
                <div class="exercise-container" id="algebra-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Avanzada: Ecuaciones Cuadráticas</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Resuelve la ecuación cuadrática: <strong>x² - 5x + 6 = 0</strong></p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="true">x = 2, x = 3</div>
                        <div class="option" data-correct="false">x = 1, x = 5</div>
                        <div class="option" data-correct="false">x = -2, x = -3</div>
                        <div class="option" data-correct="false">x = 0, x = 6</div>
                    </div>
                    
                    <button class="btn btn-algebra check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-algebra next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! Las soluciones son x = 2 y x = 3.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. Las soluciones correctas son x = 2 y x = 3.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Geometry Page -->
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
                
                <!-- Geometry Basic Exercises -->
                <div class="exercise-container active" id="geometry-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Geometría Básica: Área de Figuras</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Calcula el área de un triángulo con base de 6 cm y altura de 4 cm.</p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="false">10 cm²</div>
                        <div class="option" data-correct="false">24 cm²</div>
                        <div class="option" data-correct="true">12 cm²</div>
                        <div class="option" data-correct="false">20 cm²</div>
                    </div>
                    
                    <button class="btn btn-geometry check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-geometry next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! El área del triángulo es base × altura / 2 = 6 × 4 / 2 = 12 cm².</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. La fórmula para el área de un triángulo es base × altura / 2.</p>
                    </div>
                </div>
                
                <!-- Geometry Intermediate Exercises -->
                <div class="exercise-container" id="geometry-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Geometría Intermedia: Teorema de Pitágoras</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>En un triángulo rectángulo, los catetos miden 3 cm y 4 cm. Calcula la hipotenusa.</p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="true">5 cm</div>
                        <div class="option" data-correct="false">7 cm</div>
                        <div class="option" data-correct="false">6 cm</div>
                        <div class="option" data-correct="false">8 cm</div>
                    </div>
                    
                    <button class="btn btn-geometry check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-geometry next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! La hipotenusa es √(3² + 4²) = √25 = 5 cm.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. Usa el teorema de Pitágoras: a² + b² = c².</p>
                    </div>
                </div>
                
                <!-- Geometry Advanced Exercises -->
                <div class="exercise-container" id="geometry-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Geometría Avanzada: Trigonometría</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Calcula el seno de un ángulo de 30°.</p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="true">1/2</div>
                        <div class="option" data-correct="false">√3/2</div>
                        <div class="option" data-correct="false">1</div>
                        <div class="option" data-correct="false">0</div>
                    </div>
                    
                    <button class="btn btn-geometry check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-geometry next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! El seno de 30° es 1/2.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. El seno de 30° es 1/2.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Calculus Page -->
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
                
                <!-- Calculus Basic Exercises -->
                <div class="exercise-container active" id="calculus-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Cálculo Básico: Derivadas</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Calcula la derivada de f(x) = 3x² + 2x - 5</p>
                    </div>
                    
                    <input type="text" class="input-answer" placeholder="Escribe tu respuesta aquí (ej: 6x+2)">
                    
                    <button class="btn btn-calculus check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-calculus next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! La derivada de 3x² es 6x, la derivada de 2x es 2, y la derivada de -5 es 0.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. La derivada correcta es f'(x) = 6x + 2.</p>
                    </div>
                </div>
                
                <!-- Calculus Intermediate Exercises -->
                <div class="exercise-container" id="calculus-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Cálculo Intermedio: Integrales</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Calcula la integral de f(x) = 4x³</p>
                    </div>
                    
                    <input type="text" class="input-answer" placeholder="Escribe tu respuesta aquí (ej: x^4+C)">
                    
                    <button class="btn btn-calculus check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-calculus next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! La integral de 4x³ es x⁴ + C.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. La integral correcta es x⁴ + C.</p>
                    </div>
                </div>
                
                <!-- Calculus Advanced Exercises -->
                <div class="exercise-container" id="calculus-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Cálculo Avanzado: Límites</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Calcula el límite: lim(x→0) (sin(x)/x)</p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="true">1</div>
                        <div class="option" data-correct="false">0</div>
                        <div class="option" data-correct="false">∞</div>
                        <div class="option" data-correct="false">No existe</div>
                    </div>
                    
                    <button class="btn btn-calculus check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-calculus next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! El límite de sin(x)/x cuando x tiende a 0 es 1.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. El límite correcto es 1.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Arithmetic Page -->
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
                
                <!-- Arithmetic Basic Exercises -->
                <div class="exercise-container active" id="arithmetic-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Aritmética Básica: Fracciones</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Simplifica la siguiente fracción: 18/24</p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="false">6/8</div>
                        <div class="option" data-correct="false">9/12</div>
                        <div class="option" data-correct="true">3/4</div>
                        <div class="option" data-correct="false">2/3</div>
                    </div>
                    
                    <button class="btn btn-arithmetic check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-arithmetic next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! 18/24 simplificado es 3/4.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. El máximo común divisor de 18 y 24 es 6, por lo tanto 18÷6=3 y 24÷6=4.</p>
                    </div>
                </div>
                
                <!-- Arithmetic Intermediate Exercises -->
                <div class="exercise-container" id="arithmetic-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Aritmética Intermedia: Porcentajes</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>¿Cuánto es el 20% de 150?</p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="true">30</div>
                        <div class="option" data-correct="false">20</div>
                        <div class="option" data-correct="false">15</div>
                        <div class="option" data-correct="false">25</div>
                    </div>
                    
                    <button class="btn btn-arithmetic check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-arithmetic next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! El 20% de 150 es 30.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. Calcula el 20% de 150: (20/100) × 150 = 30.</p>
                    </div>
                </div>
                
                <!-- Arithmetic Advanced Exercises -->
                <div class="exercise-container" id="arithmetic-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Aritmética Avanzada: Proporciones</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Si 3 kg de manzanas cuestan $12, ¿cuánto cuestan 5 kg?</p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="true">$20</div>
                        <div class="option" data-correct="false">$15</div>
                        <div class="option" data-correct="false">$18</div>
                        <div class="option" data-correct="false">$25</div>
                    </div>
                    
                    <button class="btn btn-arithmetic check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-arithmetic next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! 5 kg cuestan $20.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. Usa la proporción: (12/3) × 5 = $20.</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Login Modal -->
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
                <button type="submit" class="btn btn-math" style="width: 100%;">Iniciar Sesión</button>
                <div class="form-footer">
                    <p>¿No tienes cuenta? <a href="#" id="registerLink">Regístrate aquí</a></p>
                </div>
            </form>
        </div>
    </div>

    <!-- Footer -->
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
                        <li><a href="#" class="nav-link" data-page="home">Inicio</a></li>
                        <li><a href="#" class="nav-link" data-page="math">Matemáticas</a></li>
                        <li><a href="#">Lenguaje</a></li>
                        <li><a href="#">Ciencias</a></li>
                        <li><a href="#">Sociales</a></li>
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
        // Datos de usuario y progreso (simulados)
        let userData = {
            loggedIn: false,
            name: "Invitado",
            email: "",
            completedExercises: 0,
            correctAnswers: 0,
            totalAnswers: 0
        };

        // Datos de ejercicios (50+ por categoría y nivel)
        const exercises = {
            algebra: {
                basic: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Resuelve la ecuación: <strong>${i % 2 === 0 ? `3x - 7 = 8` : `2x + 5 = 13`}</strong>`,
                    options: i % 2 === 0 ? [
                        { text: "x = 4", correct: false },
                        { text: "x = 6", correct: false },
                        { text: "x = 5", correct: true },
                        { text: "x = 3", correct: false }
                    ] : [
                        { text: "x = 3", correct: false },
                        { text: "x = 5", correct: false },
                        { text: "x = 4", correct: true },
                        { text: "x = 6", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! Has resuelto bien la ecuación.`,
                    feedbackIncorrect: `Incorrecto. La solución correcta es ${i % 2 === 0 ? 'x = 5' : 'x = 4'}.`
                })),
                intermediate: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Resuelve el sistema de ecuaciones: <strong>${i % 2 === 0 ? `2x + y = 5 y x - y = 1` : `3x + 2y = 8 y x - y = 2`}</strong>`,
                    options: i % 2 === 0 ? [
                        { text: "x = 2, y = 1", correct: true },
                        { text: "x = 1, y = 2", correct: false },
                        { text: "x = 3, y = -1", correct: false },
                        { text: "x = 0, y = 5", correct: false }
                    ] : [
                        { text: "x = 2, y = 1", correct: false },
                        { text: "x = 3, y = 1", correct: true },
                        { text: "x = 4, y = 2", correct: false },
                        { text: "x = 1, y = 3", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! La solución es ${i % 2 === 0 ? 'x = 2, y = 1' : 'x = 3, y = 1'}.`,
                    feedbackIncorrect: `Incorrecto. La solución correcta es ${i % 2 === 0 ? 'x = 2, y = 1' : 'x = 3, y = 1'}.`
                })),
                advanced: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Resuelve la ecuación cuadrática: <strong>${i % 2 === 0 ? `x² - 5x + 6 = 0` : `x² - 3x - 4 = 0`}</strong>`,
                    options: i % 2 === 0 ? [
                        { text: "x = 2, x = 3", correct: true },
                        { text: "x = 1, x = 5", correct: false },
                        { text: "x = -2, x = -3", correct: false },
                        { text: "x = 0, x = 6", correct: false }
                    ] : [
                        { text: "x = -1, x = 4", correct: true },
                        { text: "x = 1, x = 3", correct: false },
                        { text: "x = -2, x = 2", correct: false },
                        { text: "x = 0, x = 4", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! Las soluciones son ${i % 2 === 0 ? 'x = 2, x = 3' : 'x = -1, x = 4'}.`,
                    feedbackIncorrect: `Incorrecto. Las soluciones correctas son ${i % 2 === 0 ? 'x = 2, x = 3' : 'x = -1, x = 4'}.`
                }))
            },
            geometry: {
                basic: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Calcula el área de un ${i % 2 === 0 ? `triángulo con base de 6 cm y altura de 4 cm` : `círculo con radio de 5 cm (usa π = 3.14)`}`,
                    options: i % 2 === 0 ? [
                        { text: "10 cm²", correct: false },
                        { text: "24 cm²", correct: false },
                        { text: "12 cm²", correct: true },
                        { text: "20 cm²", correct: false }
                    ] : [
                        { text: "31.4 cm²", correct: false },
                        { text: "78.5 cm²", correct: true },
                        { text: "15.7 cm²", correct: false },
                        { text: "62.8 cm²", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! El área es ${i % 2 === 0 ? '12 cm²' : '78.5 cm²'}.`,
                    feedbackIncorrect: `Incorrecto. ${i % 2 === 0 ? 'El área del triángulo es base × altura / 2' : 'El área del círculo es πr²'}.`
                })),
                intermediate: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `En un triángulo rectángulo, los catetos miden ${i % 2 === 0 ? `3 cm y 4 cm` : `5 cm y 12 cm`}. Calcula la hipotenusa.`,
                    options: i % 2 === 0 ? [
                        { text: "5 cm", correct: true },
                        { text: "7 cm", correct: false },
                        { text: "6 cm", correct: false },
                        { text: "8 cm", correct: false }
                    ] : [
                        { text: "13 cm", correct: true },
                        { text: "15 cm", correct: false },
                        { text: "10 cm", correct: false },
                        { text: "17 cm", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! La hipotenusa es ${i % 2 === 0 ? '5 cm' : '13 cm'}.`,
                    feedbackIncorrect: `Incorrecto. Usa el teorema de Pitágoras: a² + b² = c².`
                })),
                advanced: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Calcula el ${i % 2 === 0 ? `seno de un ángulo de 30°` : `coseno de un ángulo de 60°`}.`,
                    options: i % 2 === 0 ? [
                        { text: "1/2", correct: true },
                        { text: "√3/2", correct: false },
                        { text: "1", correct: false },
                        { text: "0", correct: false }
                    ] : [
                        { text: "1/2", correct: true },
                        { text: "√3/2", correct: false },
                        { text: "1", correct: false },
                        { text: "0", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! El valor es 1/2.`,
                    feedbackIncorrect: `Incorrecto. El valor correcto es 1/2.`
                }))
            },
            calculus: {
                basic: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Calcula la derivada de f(x) = ${i % 2 === 0 ? `3x² + 2x - 5` : `4x³ - 3x² + 2x - 1`}`,
                    answer: i % 2 === 0 ? "6x + 2" : "12x² - 6x + 2",
                    feedbackCorrect: `¡Correcto! La derivada es ${i % 2 === 0 ? '6x + 2' : '12x² - 6x + 2'}.`,
                    feedbackIncorrect: `Incorrecto. La derivada correcta es ${i % 2 === 0 ? '6x + 2' : '12x² - 6x + 2'}.`
                })),
                intermediate: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Calcula la integral de f(x) = ${i % 2 === 0 ? `4x³` : `3x²`}`,
                    answer: i % 2 === 0 ? "x^4 + C" : "x^3 + C",
                    feedbackCorrect: `¡Correcto! La integral es ${i % 2 === 0 ? 'x⁴ + C' : 'x³ + C'}.`,
                    feedbackIncorrect: `Incorrecto. La integral correcta es ${i % 2 === 0 ? 'x⁴ + C' : 'x³ + C'}.`
                })),
                advanced: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Calcula el límite: lim(x→0) (${i % 2 === 0 ? `sin(x)/x` : `(1 - cos(x))/x²`})`,
                    options: i % 2 === 0 ? [
                        { text: "1", correct: true },
                        { text: "0", correct: false },
                        { text: "∞", correct: false },
                        { text: "No existe", correct: false }
                    ] : [
                        { text: "1/2", correct: true },
                        { text: "1", correct: false },
                        { text: "0", correct: false },
                        { text: "No existe", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! El límite es ${i % 2 === 0 ? '1' : '1/2'}.`,
                    feedbackIncorrect: `Incorrecto. El límite correcto es ${i % 2 === 0 ? '1' : '1/2'}.`
                }))
            },
            arithmetic: {
                basic: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `Simplifica la fracción: ${i % 2 === 0 ? `18/24` : `15/25`}`,
                    options: i % 2 === 0 ? [
                        { text: "6/8", correct: false },
                        { text: "9/12", correct: false },
                        { text: "3/4", correct: true },
                        { text: "2/3", correct: false }
                    ] : [
                        { text: "5/8", correct: false },
                        { text: "3/5", correct: true },
                        { text: "6/10", correct: false },
                        { text: "4/5", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! La fracción simplificada es ${i % 2 === 0 ? '3/4' : '3/5'}.`,
                    feedbackIncorrect: `Incorrecto. El máximo común divisor da ${i % 2 === 0 ? '3/4' : '3/5'}.`
                })),
                intermediate: Array.from({ length: 50 }, (_, i) => ({
                    id: i + 1,
                    question: `¿Cuánto es el ${i % 2 === 0 ? `20% de 150` : `15% de 200`}?`,
                    options: i % 2 === 0 ? [
                        { text: "30", correct: true },
                        { text: "20", correct: false },
                        { text: "15", correct: false },
                        { text: "25", correct: false }
                    ] : [
                        { text: "30", correct: true },
                        { text: "25", correct: false },
                        { text: "20", correct: false },
                        { text: "35", correct: false }
                    ],
                    feedbackCorrect: `¡Correcto! El resultado es ${i % 2 === 0 ? '30' : '30'}.`,
                    feedbackIncorrect: `Incorrecto. Calcula: ${i % 2 === 0 ? '(20/100) × 150 = 30' : '(15/100)
