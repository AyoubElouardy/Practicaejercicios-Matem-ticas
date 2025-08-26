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
        }
        
        .back-button i {
            margin-right: 0.5rem;
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
                    <p>Practica ejercicios de álgebra de diferentes niveles</p>
                </div>
                
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="algebra-basic">Básico</div>
                    <div class="exercise-tab" data-tab="algebra-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="algebra-advanced">Avanzado</div>
                </div>
                
                <!-- Ejercicios de Álgebra Básico -->
                <div class="exercise-container active" id="algebra-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Básica: Ecuaciones Lineales</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 5</span>
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
                
                <!-- Ejercicios de Álgebra Intermedio -->
                <div class="exercise-container" id="algebra-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Intermedia: Sistemas de Ecuaciones</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 5</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Resuelve el siguiente sistema de ecuaciones:<br>
                        <strong>2x + y = 10</strong><br>
                        <strong>x - y = 2</strong></p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="false">x = 3, y = 4</div>
                        <div class="option" data-correct="false">x = 5, y = 3</div>
                        <div class="option" data-correct="true">x = 4, y = 2</div>
                        <div class="option" data-correct="false">x = 6, y = 1</div>
                    </div>
                    
                    <button class="btn btn-algebra check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-algebra next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! La solución es x = 4, y = 2.</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. La solución correcta es x = 4, y = 2.</p>
                    </div>
                </div>
                
                <!-- Ejercicios de Álgebra Avanzado -->
                <div class="exercise-container" id="algebra-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Álgebra Avanzada: Polinomios</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 5</span>
                        </div>
                    </div>
                    
                    <div class="exercise-question">
                        <p>Factoriza el siguiente polinomio: <strong>x² - 5x + 6</strong></p>
                    </div>
                    
                    <div class="options-container">
                        <div class="option" data-correct="false">(x + 2)(x + 3)</div>
                        <div class="option" data-correct="false">(x - 1)(x - 6)</div>
                        <div class="option" data-correct="true">(x - 2)(x - 3)</div>
                        <div class="option" data-correct="false">(x + 1)(x + 6)</div>
                    </div>
                    
                    <button class="btn btn-algebra check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-algebra next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    
                    <div class="exercise-feedback feedback-correct">
                        <p><i class="fas fa-check-circle"></i> ¡Correcto! El polinomio factorizado es (x - 2)(x - 3).</p>
                    </div>
                    
                    <div class="exercise-feedback feedback-incorrect">
                        <p><i class="fas fa-times-circle"></i> Incorrecto. La factorización correcta es (x - 2)(x - 3).</p>
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
                    <p>Practica ejercicios de geometría de diferentes niveles</p>
                </div>
                
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="geometry-basic">Básico</div>
                    <div class="exercise-tab" data-tab="geometry-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="geometry-advanced">Avanzado</div>
                </div>
                
                <!-- Ejercicios de Geometría Básico -->
                <div class="exercise-container active" id="geometry-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Geometría Básica: Área de Figuras</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 5</span>
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
                
                <!-- Más contenedores de ejercicios de geometría (intermedio y avanzado) -->
                <div class="exercise-container" id="geometry-intermediate-exercises">
                    <!-- Contenido de ejercicios de geometría intermedio -->
                </div>
                
                <div class="exercise-container" id="geometry-advanced-exercises">
                    <!-- Contenido de ejercicios de geometría avanzado -->
                </div>
            </div>
        </section>

        <!-- Calculus Page -->
        <section class="subject-page" id="calculus-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="math"><i class="fas fa-arrow-left"></i> Volver a Matemáticas</a>
                
                <div class="section-title">
                    <h2>Cálculo</h2>
                    <p>Practica ejercicios de cálculo de diferentes niveles</p>
                </div>
                
                <!-- Contenido de ejercicios de cálculo -->
            </div>
        </section>

        <!-- Arithmetic Page -->
        <section class="subject-page" id="arithmetic-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="math"><i class="fas fa-arrow-left"></i> Volver a Matemáticas</a>
                
                <div class="section-title">
                    <h2>Aritmética</h2>
                    <p>Practica ejercicios de aritmética de diferentes niveles</p>
                </div>
                
                <!-- Contenido de ejercicios de aritmética -->
            </div>
        </section>
    </main>

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Iniciar Sesión</h2>
                <span class="close-modal">&times;</span>
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
                <p>&copy; 2023 PracticaEjercicios.com - Todos los derechos reservados</p>
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

        // Elementos del DOM
        const mainContent = document.getElementById('main-content');
        const userAvatar = document.getElementById('userAvatar');
        const userDropdown = document.getElementById('userDropdown');
        const userInfo = document.getElementById('userInfo');
        const userName = document.getElementById('userName');
        const userEmail = document.getElementById('userEmail');
        const completedExercises = document.getElementById('completedExercises');
        const correctAnswers = document.getElementById('correctAnswers');
        const loginBtn = document.getElementById('loginBtn');
        const loginModal = document.getElementById('loginModal');
        const closeModal = document.querySelector('.close-modal');
        const loginForm = document.getElementById('loginForm');
        const registerLink = document.getElementById('registerLink');
        const navLinks = document.querySelectorAll('.nav-link');
        const practiceBtns = document.querySelectorAll('.practice-btn');
        const exerciseTabs = document.querySelectorAll('.exercise-tab');
        const exerciseContainers = document.querySelectorAll('.exercise-container');
        
        // Alternar dropdown de usuario
        userAvatar.addEventListener('click', function(e) {
            e.stopPropagation();
            userDropdown.classList.toggle('active');
        });

        userInfo.addEventListener('click', function() {
            userDropdown.classList.toggle('active');
        });

        // Cerrar dropdown al hacer clic fuera
        document.addEventListener('click', function(e) {
            if (!userAvatar.contains(e.target) && !userDropdown.contains(e.target)) {
                userDropdown.classList.remove('active');
            }
        });

        // Abrir modal de inicio de sesión
        loginBtn.addEventListener('click', function() {
            loginModal.style.display = 'flex';
        });

        // Cerrar modal
        closeModal.addEventListener('click', function() {
            loginModal.style.display = 'none';
        });

        // Cerrar modal al hacer clic fuera
        window.addEventListener('click', function(e) {
            if (e.target === loginModal) {
                loginModal.style.display = 'none';
            }
        });

        // Envío del formulario de inicio de sesión
        loginForm.addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            
            // Simular inicio de sesión exitoso
            userData.loggedIn = true;
            userData.name = "Usuario Ejemplo";
            userData.email = email;
            
            // Actualizar interfaz
            userName.textContent = userData.name;
            userEmail.textContent = userData.email;
            loginBtn.textContent = "Cerrar Sesión";
            
            // Cerrar modal
            loginModal.style.display = 'none';
            
            // Cambiar funcionalidad del botón a cerrar sesión
            loginBtn.removeEventListener('click', openLoginModal);
            loginBtn.addEventListener('click', logout);
        });

        // Función para abrir modal de inicio de sesión
        function openLoginModal() {
            loginModal.style.display = 'flex';
        }

        // Función para cerrar sesión
        function logout() {
            userData.loggedIn = false;
            userData.name = "Invitado";
            userData.email = "";
            
            // Actualizar interfaz
            userName.textContent = userData.name;
            userEmail.textContent = "No has iniciado sesión";
            loginBtn.textContent = "Iniciar Sesión";
            
            // Restaurar funcionalidad del botón
            loginBtn.removeEventListener('click', logout);
            loginBtn.addEventListener('click', openLoginModal);
        }

        // Navegación entre páginas
        navLinks.forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const page = this.getAttribute('data-page');
                showPage(page);
            });
        });

        // Botones de práctica
        practiceBtns.forEach(btn => {
            btn.addEventListener('click', function(e) {
                e.preventDefault();
                const subject = this.getAttribute('data-subject');
                showPage(subject + '-page');
            });
        });

        // Cambiar entre pestañas de ejercicios
        exerciseTabs.forEach(tab => {
            tab.addEventListener('click', function() {
                const tabId = this.getAttribute('data-tab');
                
                // Desactivar todas las pestañas
                exerciseTabs.forEach(t => t.classList.remove('active'));
                // Activar la pestaña clickeada
                this.classList.add('active');
                
                // Ocultar todos los contenedores de ejercicios
                const parentContainer = this.closest('.subject-page');
                parentContainer.querySelectorAll('.exercise-container').forEach(container => {
                    container.classList.remove('active');
                });
                
                // Mostrar el contenedor correspondiente
                parentContainer.querySelector(`#${tabId}-exercises`).classList.add('active');
            });
        });

        // Configurar eventos para ejercicios
        function setupExercises() {
            document.querySelectorAll('.check-answer-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const container = this.closest('.exercise-container');
                    const selectedOption = container.querySelector('.option.selected');
                    
                    if (!selectedOption) {
                        alert('Por favor, selecciona una respuesta');
                        return;
                    }
                    
                    const feedbackCorrect = container.querySelector('.feedback-correct');
                    const feedbackIncorrect = container.querySelector('.feedback-incorrect');
                    const nextBtn = container.querySelector('.next-question-btn');
                    
                    // Mostrar retroalimentación
                    if (selectedOption.dataset.correct === 'true') {
                        feedbackCorrect.style.display = 'block';
                        feedbackIncorrect.style.display = 'none';
                        selectedOption.classList.add('correct');
                        
                        // Actualizar estadísticas si el usuario está logueado
                        if (userData.loggedIn) {
                            userData.correctAnswers++;
                            userData.totalAnswers++;
                            userData.completedExercises++;
                            updateUserStats();
                        }
                    } else {
                        feedbackIncorrect.style.display = 'block';
                        feedbackCorrect.style.display = 'none';
                        selectedOption.classList.add('incorrect');
                        
                        // Resaltar la respuesta correcta
                        container.querySelectorAll('.option').forEach(option => {
                            if (option.dataset.correct === 'true') {
                                option.classList.add('correct');
                            }
                        });
                        
                        // Actualizar estadísticas si el usuario está logueado
                        if (userData.loggedIn) {
                            userData.totalAnswers++;
                            userData.completedExercises++;
                            updateUserStats();
                        }
                    }
                    
                    // Ocultar botón de comprobar y mostrar siguiente
                    this.style.display = 'none';
                    nextBtn.style.display = 'inline-block';
                });
            });
            
            // Siguiente pregunta
            document.querySelectorAll('.next-question-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const container = this.closest('.exercise-container');
                    const options = container.querySelectorAll('.option');
                    const feedbackCorrect = container.querySelector('.feedback-correct');
                    const feedbackIncorrect = container.querySelector('.feedback-incorrect');
                    const checkBtn = container.querySelector('.check-answer-btn');
                    const exerciseCounter = container.querySelector('.exercise-counter');
                    
                    // Reiniciar interfaz para nueva pregunta
                    options.forEach(option => {
                        option.classList.remove('selected', 'correct', 'incorrect');
                    });
                    
                    feedbackCorrect.style.display = 'none';
                    feedbackIncorrect.style.display = 'none';
                    
                    checkBtn.style.display = 'inline-block';
                    this.style.display = 'none';
                    
                    // Cambiar número de ejercicio (simulado)
                    let current = parseInt(exerciseCounter.textContent);
                    const maxExercises = parseInt(exerciseCounter.textContent.split(' de ')[1]);
                    exerciseCounter.textContent = current < maxExercises ? current + 1 + ' de ' + maxExercises : '1 de ' + maxExercises;
                    
                    // Cambiar pregunta y opciones (simulado)
                    updateExerciseContent(container, current);
                });
            });
            
            // Seleccionar opción
            document.querySelectorAll('.option').forEach(option => {
                option.addEventListener('click', function() {
                    const container = this.closest('.exercise-container');
                    
                    // Deseleccionar todas las opciones
                    container.querySelectorAll('.option').forEach(opt => opt.classList.remove('selected'));
                    
                    // Seleccionar la opción clickeada
                    this.classList.add('selected');
                });
            });
        }

        // Actualizar contenido del ejercicio
        function updateExerciseContent(container, current) {
            // Esta función cambiaría el contenido del ejercicio según el número
            // En una implementación real, se cargarían datos de un array o API
            const questionElement = container.querySelector('.exercise-question p');
            const options = container.querySelectorAll('.option');
            
            // Simulamos cambios basados en el tipo de ejercicio
            if (container.id.includes('algebra')) {
                if (current % 2 === 0) {
                    questionElement.innerHTML = 'Resuelve la ecuación: <strong>3x - 7 = 8</strong>';
                    options[0].textContent = 'x = 4';
                    options[0].dataset.correct = 'false';
                    options[1].textContent = 'x = 6';
                    options[1].dataset.correct = 'false';
                    options[2].textContent = 'x = 5';
                    options[2].dataset.correct = 'true';
                    options[3].textContent = 'x = 3';
                    options[3].dataset.correct = 'false';
                } else {
                    questionElement.innerHTML = 'Resuelve la ecuación: <strong>2x + 5 = 13</strong>';
                    options[0].textContent = 'x = 3';
                    options[0].dataset.correct = 'false';
                    options[1].textContent = 'x = 5';
                    options[1].dataset.correct = 'false';
                    options[2].textContent = 'x = 4';
                    options[2].dataset.correct = 'true';
                    options[3].textContent = 'x = 6';
                    options[3].dataset.correct = 'false';
                }
            }
            // Se pueden añadir más condiciones para otros tipos de ejercicios
        }

        // Mostrar página específica
        function showPage(pageId) {
            // Ocultar todas las páginas
            document.querySelectorAll('.subject-page').forEach(page => {
                page.classList.remove('active');
            });
            
            // Mostrar la página solicitada
            document.getElementById(pageId).classList.add('active');
            
            // Scroll to top
            window.scrollTo(0, 0);
            
            // Configurar ejercicios si es una página de práctica
            if (pageId.includes('algebra') || pageId.includes('geometry') || 
                pageId.includes('calculus') || pageId.includes('arithmetic')) {
                setTimeout(setupExercises, 100);
            }
        }

        // Actualizar estadísticas de usuario
        function updateUserStats() {
            completedExercises.textContent = userData.completedExercises;
            const accuracy = userData.totalAnswers > 0 ? 
                Math.round((userData.correctAnswers / userData.totalAnswers) * 100) : 0;
            correctAnswers.textContent = `${accuracy}%`;
        }

        // Inicializar eventos
        loginBtn.addEventListener('click', openLoginModal);
        registerLink.addEventListener('click', function(e) {
            e.preventDefault();
            alert('Funcionalidad de registro no implementada en este ejemplo');
        });
        
        // Configurar ejercicios en la página inicial
        setupExercises();
    </script>
</body>
</html>
