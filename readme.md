<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🚀 Animated Developer Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            color: #333;
            overflow-x: hidden;
            min-height: 100vh;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Particle Background */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(0) translateX(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) translateX(100px) rotate(360deg);
                opacity: 0;
            }
        }

        .container {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* ==================== HEADER ANIMATIONS ==================== */
        .header {
            text-align: center;
            color: white;
            margin: 80px 0 40px;
            animation: slideInDown 1.2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-80px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header h1 {
            font-size: 4.5em;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(0, 0, 0, 0.3);
            animation: textGlow 2.5s ease-in-out infinite, float 3s ease-in-out infinite;
            letter-spacing: 3px;
        }

        @keyframes textGlow {
            0%, 100% {
                text-shadow: 0 0 20px rgba(255, 255, 255, 0.5),
                             0 0 30px rgba(255, 69, 0, 0.5);
                transform: scale(1);
            }
            50% {
                text-shadow: 0 0 30px rgba(255, 255, 255, 0.8),
                             0 0 50px rgba(255, 69, 0, 0.8),
                             0 0 70px rgba(255, 20, 147, 0.6);
                transform: scale(1.02);
            }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Animated Subtitle */
        .subtitle {
            font-size: 2em;
            color: #fff;
            margin: 20px 0;
            font-weight: 300;
            letter-spacing: 2px;
            animation: fadeInUp 1.5s ease 0.3s both;
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

        /* Shimmer Text Effect */
        .shimmer {
            background: linear-gradient(
                90deg,
                rgba(255, 255, 255, 0.3) 0%,
                rgba(255, 255, 255, 0.8) 50%,
                rgba(255, 255, 255, 0.3) 100%
            );
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shimmer 3s linear infinite;
        }

        @keyframes shimmer {
            0% { background-position: -200% center; }
            100% { background-position: 200% center; }
        }

        /* Pulse Animation */
        .pulse {
            animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.5;
            }
        }

        /* ==================== SECTIONS ==================== */
        .section {
            background: rgba(255, 255, 255, 0.97);
            border-radius: 25px;
            padding: 50px 40px;
            margin: 50px 0;
            box-shadow: 0 20px 80px rgba(0, 0, 0, 0.2);
            animation: slideInUp 1s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section h2 {
            text-align: center;
            margin-bottom: 40px;
            color: #23a6d5;
            font-size: 3em;
            position: relative;
            animation: slideInDown 0.8s ease 0.2s both;
        }

        .section h2::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #FF69B4, #00D4FF);
            margin: 20px auto 0;
            border-radius: 2px;
            animation: expandWidth 0.8s ease 0.4s both;
        }

        @keyframes expandWidth {
            from { width: 0; }
            to { width: 100px; }
        }

        /* ==================== GAME SECTION ==================== */
        .game-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 40px;
            flex-wrap: wrap;
            margin: 40px 0;
        }

        .game-canvas-wrapper {
            position: relative;
            animation: zoomIn 0.8s ease 0.3s both;
        }

        @keyframes zoomIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        #gameCanvas, #pongCanvas {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            border: 4px solid transparent;
            border-image: linear-gradient(45deg, #FF69B4, #00D4FF, #FF69B4) 1;
            border-radius: 15px;
            box-shadow: 0 0 40px rgba(0, 0, 0, 0.5),
                        0 0 60px rgba(255, 105, 180, 0.4),
                        inset 0 0 30px rgba(0, 212, 255, 0.1);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        #gameCanvas:hover, #pongCanvas:hover {
            transform: scale(1.03);
            box-shadow: 0 0 60px rgba(0, 0, 0, 0.6),
                        0 0 80px rgba(255, 105, 180, 0.6),
                        inset 0 0 40px rgba(0, 212, 255, 0.2);
        }

        .game-controls {
            display: flex;
            flex-direction: column;
            gap: 20px;
            animation: slideInRight 0.8s ease 0.4s both;
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .game-stats {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            min-width: 220px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 2px solid rgba(255, 255, 255, 0.2);
        }

        .stat-item {
            font-size: 1.2em;
            margin: 15px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            animation: slideInLeft 0.6s ease both;
        }

        .stat-item:nth-child(1) { animation-delay: 0.6s; }
        .stat-item:nth-child(2) { animation-delay: 0.7s; }
        .stat-item:nth-child(3) { animation-delay: 0.8s; }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .stat-label {
            font-weight: bold;
            margin-right: 10px;
            animation: blink 2s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.6; }
        }

        .stat-value {
            background: rgba(255, 255, 255, 0.3);
            padding: 8px 18px;
            border-radius: 20px;
            font-size: 1.3em;
            font-weight: bold;
            animation: pulse 2s infinite;
        }

        .instructions {
            background: rgba(35, 166, 213, 0.1);
            padding: 25px;
            border-radius: 12px;
            margin-top: 20px;
            border-left: 5px solid #23a6d5;
            animation: slideInUp 0.8s ease 0.5s both;
        }

        .instructions h4 {
            color: #23a6d5;
            margin-bottom: 15px;
            font-size: 1.2em;
            animation: fadeIn 0.6s ease 0.6s both;
        }

        .instructions p {
            color: #555;
            margin: 10px 0;
            animation: fadeIn 0.6s ease both;
        }

        .instructions p:nth-child(2) { animation-delay: 0.7s; }
        .instructions p:nth-child(3) { animation-delay: 0.8s; }
        .instructions p:nth-child(4) { animation-delay: 0.9s; }
        .instructions p:nth-child(5) { animation-delay: 1s; }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* ==================== BUTTONS ==================== */
        button {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            padding: 18px 45px;
            font-size: 1.15em;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            position: relative;
            overflow: hidden;
            animation: slideInUp 0.8s ease 0.7s both;
        }

        button::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        button:hover::before {
            width: 300px;
            height: 300px;
        }

        button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        button:active {
            transform: translateY(-2px);
        }

        /* ==================== TECH SECTION ==================== */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 25px;
            animation: fadeIn 0.8s ease 0.3s both;
        }

        .tech-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            border-radius: 18px;
            text-align: center;
            cursor: pointer;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            border: 2px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            animation: scaleIn 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            position: relative;
            overflow: hidden;
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.7);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .tech-card:nth-child(1) { animation-delay: 0.1s; }
        .tech-card:nth-child(2) { animation-delay: 0.2s; }
        .tech-card:nth-child(3) { animation-delay: 0.3s; }
        .tech-card:nth-child(4) { animation-delay: 0.4s; }
        .tech-card:nth-child(5) { animation-delay: 0.5s; }
        .tech-card:nth-child(6) { animation-delay: 0.6s; }
        .tech-card:nth-child(7) { animation-delay: 0.7s; }
        .tech-card:nth-child(8) { animation-delay: 0.8s; }

        .tech-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: translate(-100%, -100%) rotate(45deg); }
            100% { transform: translate(100%, 100%) rotate(45deg); }
        }

        .tech-card:hover {
            transform: translateY(-15px) scale(1.05);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
        }

        .tech-icon {
            font-size: 3.5em;
            margin-bottom: 15px;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        .tech-card h3 {
            font-size: 1.4em;
            margin-bottom: 10px;
        }

        /* ==================== PROJECTS SECTION ==================== */
        .project-card {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            padding: 35px;
            border-radius: 18px;
            margin-bottom: 25px;
            cursor: pointer;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            border: 2px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            animation: slideInLeft 0.8s ease;
            position: relative;
            overflow: hidden;
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .project-card:nth-child(1) { animation-delay: 0.2s; }
        .project-card:nth-child(2) { animation-delay: 0.4s; }
        .project-card:nth-child(3) { animation-delay: 0.6s; }

        .project-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.2);
            transition: left 0.5s ease;
        }

        .project-card:hover::after {
            left: 100%;
        }

        .project-card:hover {
            transform: translateX(10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        .project-card h3 {
            font-size: 1.6em;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
        }

        .project-card p {
            line-height: 1.8;
            position: relative;
            z-index: 1;
        }

        /* ==================== STATS SECTION ==================== */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 25px;
            animation: fadeIn 0.8s ease 0.3s both;
        }

        .stat-card {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            padding: 40px 30px;
            border-radius: 18px;
            text-align: center;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.3);
            cursor: pointer;
            transition: all 0.3s ease;
            animation: bounceIn 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            position: relative;
            overflow: hidden;
        }

        @keyframes bounceIn {
            0% {
                opacity: 0;
                transform: scale(0.5);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        .stat-card:nth-child(1) { animation-delay: 0.1s; }
        .stat-card:nth-child(2) { animation-delay: 0.2s; }
        .stat-card:nth-child(3) { animation-delay: 0.3s; }
        .stat-card:nth-child(4) { animation-delay: 0.4s; }

        .stat-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.2);
        }

        .stat-card h3 {
            font-size: 3.5em;
            color: #23a6d5;
            margin-bottom: 15px;
            font-weight: bold;
            animation: countUp 2s ease-in-out forwards;
        }

        @keyframes countUp {
            from {
                transform: translateY(30px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .stat-card p {
            color: #555;
            font-size: 1.2em;
            font-weight: bold;
            animation: fadeInUp 1.2s ease 0.5s both;
        }

        /* ==================== FOOTER ==================== */
        .footer {
            text-align: center;
            color: white;
            padding: 60px 20px;
            font-size: 1.15em;
            animation: slideInUp 1s ease 0.8s both;
        }

        .footer h2 {
            font-size: 2.5em;
            margin-bottom: 30px;
            animation: textGlow 2s ease-in-out infinite;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin: 30px 0;
            flex-wrap: wrap;
            animation: fadeIn 1.2s ease 0.9s both;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            transition: all 0.3s ease;
            font-size: 2em;
            cursor: pointer;
            border: 2px solid rgba(255, 255, 255, 0.3);
            animation: popIn 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        @keyframes popIn {
            0% {
                opacity: 0;
                transform: scale(0);
                rotate: -180deg;
            }
            100% {
                opacity: 1;
                transform: scale(1);
                rotate: 0deg;
            }
        }

        .social-link:nth-child(1) { animation-delay: 1s; }
        .social-link:nth-child(2) { animation-delay: 1.1s; }
        .social-link:nth-child(3) { animation-delay: 1.2s; }
        .social-link:nth-child(4) { animation-delay: 1.3s; }

        .social-link:hover {
            background: rgba(255, 255, 255, 0.4);
            transform: scale(1.15);
            box-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
        }

        .footer p {
            animation: fadeInUp 1.2s ease 1s both;
        }

        /* ==================== RESPONSIVE ==================== */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5em;
            }

            .section h2 {
                font-size: 2em;
            }

            .game-container {
                gap: 20px;
            }

            #gameCanvas, #pongCanvas {
                max-width: 100%;
                height: auto;
            }

            .game-controls {
                width: 100%;
            }
        }

        /* Loading Animation */
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Wave Text Animation */
        .wave {
            display: inline-block;
        }

        .wave span {
            display: inline-block;
            animation: wave 1.5s ease-in-out infinite;
        }

        @keyframes wave {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .wave span:nth-child(1) { animation-delay: 0s; }
        .wave span:nth-child(2) { animation-delay: 0.2s; }
        .wave span:nth-child(3) { animation-delay: 0.4s; }
        .wave span:nth-child(4) { animation-delay: 0.6s; }
        .wave span:nth-child(5) { animation-delay: 0.8s; }
    </style>
</head>
<body>
    <!-- Particle Background -->
    <div class="particles" id="particlesContainer"></div>

    <div class="container">
        <!-- Header with Animations -->
        <div class="header">
            <h1>👨‍💻 <span class="shimmer">Sunita Dariyana</span></h1>
            <div class="subtitle">
                <span class="wave">
                    <span>W</span><span>e</span><span>l</span><span>c</span><span>o</span><span>m</span><span>e</span>
                </span>
            </div>
            <p style="font-size: 1.5em; color: white; animation: fadeInUp 1.5s ease 0.5s both; margin-top: 20px;">
                🚀 Full Stack Developer | 💻 Creative Coder | ✨ Tech Innovator
            </p>
        </div>

        <!-- Snake Game Section -->
        <div class="section">
            <h2>🐍 <span class="pulse">Play Snake Game!</span></h2>
            <div class="game-container">
                <div class="game-canvas-wrapper">
                    <canvas id="gameCanvas" width="350" height="350"></canvas>
                    <div class="instructions">
                        <h4>📝 How to Play:</h4>
                        <p>🖱️ Use <strong>Arrow Keys</strong> or <strong>WASD</strong> to move</p>
                        <p>🍎 Eat red apples to grow</p>
                        <p>💥 Don't hit walls or yourself!</p>
                        <p>⏸️ Press <strong>Space</strong> to pause</p>
                    </div>
                </div>
                <div class="game-controls">
                    <div class="game-stats">
                        <div class="stat-item">
                            <span class="stat-label">🎯 Score:</span>
                            <span class="stat-value" id="score">0</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-label">⭐ High Score:</span>
                            <span class="stat-value" id="highScore">0</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-label">🚀 Level:</span>
                            <span class="stat-value" id="level">1</span>
                        </div>
                    </div>
                    <button onclick="startGame()">🎮 Start Game</button>
                    <button onclick="resetGame()">🔄 Reset</button>
                </div>
            </div>
        </div>

        <!-- Pong Game Section -->
        <div class="section">
            <h2>🎾 <span class="pulse">Pong Game</span></h2>
            <div class="game-container">
                <div class="game-canvas-wrapper">
                    <canvas id="pongCanvas" width="700" height="350"></canvas>
                </div>
                <div class="game-controls">
                    <div class="game-stats">
                        <div class="stat-item">
                            <span class="stat-label">⬅️ P1:</span>
                            <span class="stat-value" id="p1Score">0</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-label">➡️ P2:</span>
                            <span class="stat-value" id="p2Score">0</span>
                        </div>
                    </div>
                    <button onclick="startPong()">🎾 Start Pong</button>
                    <button onclick="resetPong()">🔄 Reset</button>
                </div>
            </div>
            <div class="instructions" style="margin-top: 30px;">
                <h4>🎮 How to Play:</h4>
                <p><strong>🟩 Left Player (P1):</strong> Press <strong>W</strong> to move up, <strong>S</strong> to move down</p>
                <p><strong>🟦 Right Player (P2):</strong> Press <strong>↑</strong> to move up, <strong>↓</strong> to move down</p>
                <p><strong>🎯 Objective:</strong> Hit the ball and score! First to 5 wins! 🏆</p>
            </div>
        </div>

        <!-- Tech Stack Section -->
        <div class="section">
            <h2>🛠️ <span class="shimmer">Tech Stack</span></h2>
            <div class="tech-grid">
                <div class="tech-card">
                    <div class="tech-icon">⚛️</div>
                    <h3>React</h3>
                    <p>UI Library</p>
                </div>
                <div class="tech-card">
                    <div class="tech-icon">🟡</div>
                    <h3>JavaScript</h3>
                    <p>Full Stack</p>
                </div>
                <div class="tech-card">
                    <div class="tech-icon">🐍</div>
                    <h3>Python</h3>
                    <p>Backend</p>
                </div>
                <div class="tech-card">
                    <div class="tech-icon">⚡</div>
                    <h3>Node.js</h3>
                    <p>Runtime</p>
                </div>
                <div class="tech-card">
                    <div class="tech-icon">🗄️</div>
                    <h3>MongoDB</h3>
                    <p>Database</p>
                </div>
                <div class="tech-card">
                    <div class="tech-icon">🐘</div>
                    <h3>PostgreSQL</h3>
                    <p>Database</p>
                </div>
                <div class="tech-card">
                    <div class="tech-icon">🐳</div>
                    <h3>Docker</h3>
                    <p>Containers</p>
                </div>
                <div class="tech-card">
                    <div class="tech-icon">☁️</div>
                    <h3>AWS</h3>
                    <p>Cloud</p>
                </div>
            </div>
        </div>

        <!-- Projects Section -->
        <div class="section">
            <h2>📁 <span class="shimmer">Featured Projects</span></h2>
            <div class="project-card">
                <h3>🚀 E-Commerce Platform</h3>
                <p>A full-stack e-commerce solution with React, Node.js, and MongoDB. Real-time inventory, payment integration, and user authentication included!</p>
            </div>
            <div class="project-card">
                <h3>🤖 AI Chatbot</h3>
                <p>Intelligent chatbot powered by machine learning. Built with Python and integrated with React for seamless user interactions.</p>
            </div>
            <div class="project-card">
                <h3>📊 Analytics Dashboard</h3>
                <p>Comprehensive data visualization platform using D3.js. Processes complex datasets and provides real-time insights.</p>
            </div>
        </div>

        <!-- Stats Section -->
        <div class="section">
            <h2>📊 <span class="shimmer">Statistics</span></h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <h3>50+</h3>
                    <p>Projects Completed</p>
                </div>
                <div class="stat-card">
                    <h3>1000+</h3>
                    <p>GitHub Stars</p>
                </div>
                <div class="stat-card">
                    <h3>5+</h3>
                    <p>Years Experience</p>
                </div>
                <div class="stat-card">
                    <h3>100%</h3>
                    <p>Dedication</p>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <h2>Let's Connect! 🤝</h2>
            <div class="social-links">
                <div class="social-link">💼</div>
                <div class="social-link">🐦</div>
                <div class="social-link">📧</div>
                <div class="social-link">💻</div>
            </div>
            <p>Made with ❤️ | Always Learning, Always Growing 🚀</p>
        </div>
    </div>

    <script>
        // Create Floating Particles
        function createParticles() {
            const container = document.getElementById('particlesContainer');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 20 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 15) + 's';
                particle.style.width = (Math.random() * 8 + 2) + 'px';
                particle.style.height = particle.style.width;
                container.appendChild(particle);
            }
        }

        // ==================== SNAKE GAME ====================
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const gridSize = 17;
        const tileCount = canvas.width / gridSize;

        let snake = [{ x: 10, y: 10 }];
        let food = { x: 15, y: 15 };
        let dx = 1;
        let dy = 0;
        let score = 0;
        let highScore = localStorage.getItem('snakeHighScore') || 0;
        let gameRunning = false;
        let gamePaused = false;
        let level = 1;
        let speed = 100;

        document.getElementById('highScore').textContent = highScore;

        function drawGame() {
            // Clear canvas with gradient
            const gradient = ctx.createLinearGradient(0, 0, canvas.width, canvas.height);
            gradient.addColorStop(0, 'rgba(26, 26, 46, 0.8)');
            gradient.addColorStop(1, 'rgba(22, 33, 62, 0.8)');
            ctx.fillStyle = gradient;
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            // Draw animated grid
            ctx.strokeStyle = 'rgba(255, 255, 255, 0.05)';
            ctx.lineWidth = 1;
            for (let i = 0; i <= tileCount; i++) {
                ctx.beginPath();
                ctx.moveTo(i * gridSize, 0);
                ctx.lineTo(i * gridSize, canvas.height);
                ctx.stroke();
                ctx.beginPath();
                ctx.moveTo(0, i * gridSize);
                ctx.lineTo(canvas.width, i * gridSize);
                ctx.stroke();
            }

            // Draw snake with gradient
            snake.forEach((segment, index) => {
                const hue = (index * 10) % 360;
                if (index === 0) {
                    // Head with glow
                    ctx.fillStyle = '#00FF00';
                    ctx.shadowColor = 'rgba(0, 255, 0, 0.8)';
                    ctx.shadowBlur = 15;
                    ctx.shadowOffsetX = 0;
                    ctx.shadowOffsetY = 0;
                } else {
                    ctx.fillStyle = `hsl(${hue}, 100%, 50%)`;
                    ctx.shadowBlur = 8;
                }
                ctx.fillRect(segment.x * gridSize + 2, segment.y * gridSize + 2, gridSize - 4, gridSize - 4);
                ctx.shadowBlur = 0;
            });

            // Draw food with pulsing effect
            const foodSize = gridSize / 3 + (Math.sin(Date.now() / 200) * gridSize / 8);
            ctx.fillStyle = '#FF0000';
            ctx.shadowColor = 'rgba(255, 0, 0, 0.9)';
            ctx.shadowBlur = 20;
            ctx.beginPath();
            ctx.arc(food.x * gridSize + gridSize / 2, food.y * gridSize + gridSize / 2, foodSize, 0, Math.PI * 2);
            ctx.fill();
            ctx.shadowBlur = 0;
        }

        function updateGame() {
            if (!gameRunning || gamePaused) return;

            const head = { x: snake[0].x + dx, y: snake[0].y + dy };

            if (head.x < 0 || head.x >= tileCount || head.y < 0 || head.y >= tileCount ||
                snake.some(segment => segment.x === head.x && segment.y === head.y)) {
                gameRunning = false;
                alert(`🎮 Game Over!\n\nFinal Score: ${score}\nLevel: ${level}`);
                return;
            }

            snake.unshift(head);

            if (head.x === food.x && head.y === food.y) {
                score += 10 * level;
                document.getElementById('score').textContent = score;
                
                if (score % 50 === 0) {
                    level++;
                    speed = Math.max(50, speed - 10);
                    document.getElementById('level').textContent = level;
                }

                food = {
                    x: Math.floor(Math.random() * tileCount),
                    y: Math.floor(Math.random() * tileCount)
                };
            } else {
                snake.pop();
            }
        }

        function gameLoop() {
            updateGame();
            drawGame();
            if (gameRunning) {
                setTimeout(gameLoop, speed);
            }
        }

        function startGame() {
            if (!gameRunning) {
                gameRunning = true;
                gamePaused = false;
                gameLoop();
            }
        }

        function resetGame() {
            snake = [{ x: 10, y: 10 }];
            food = { x: 15, y: 15 };
            dx = 1;
            dy = 0;
            score = 0;
            level = 1;
            speed = 100;
            gameRunning = false;
            gamePaused = false;
            document.getElementById('score').textContent = score;
            document.getElementById('level').textContent = level;
            drawGame();
        }

        document.addEventListener('keydown', (e) => {
            if (e.key === ' ') {
                e.preventDefault();
                gamePaused = !gamePaused;
            }
            if (['ArrowUp', 'ArrowDown', 'ArrowLeft', 'ArrowRight'].includes(e.key)) {
                e.preventDefault();
                if (e.key === 'ArrowUp' && dy === 0) { dx = 0; dy = -1; }
                else if (e.key === 'ArrowDown' && dy === 0) { dx = 0; dy = 1; }
                else if (e.key === 'ArrowLeft' && dx === 0) { dx = -1; dy = 0; }
                else if (e.key === 'ArrowRight' && dx === 0) { dx = 1; dy = 0; }
            }
            if (e.key.toLowerCase() === 'w' && dy === 0) { dx = 0; dy = -1; }
            else if (e.key.toLowerCase() === 's' && dy === 0) { dx = 0; dy = 1; }
            else if (e.key.toLowerCase() === 'a' && dx === 0) { dx = -1; dy = 0; }
            else if (e.key.toLowerCase() === 'd' && dx === 0) { dx = 1; dy = 0; }
        });

        // ==================== PONG GAME ====================
        const pongCanvas = document.getElementById('pongCanvas');
        const pongCtx = pongCanvas.getContext('2d');

        const paddle = {
            width: 12,
            height: 80,
            speed: 7
        };

        const ball = {
            x: pongCanvas.width / 2,
            y: pongCanvas.height / 2,
            radius: 8,
            dx: 5,
            dy: 5
        };

        let player1 = { x: 15, y: pongCanvas.height / 2 - paddle.height / 2, ...paddle, score: 0 };
        let player2 = { x: pongCanvas.width - 27, y: pongCanvas.height / 2 - paddle.height / 2, ...paddle, score: 0 };

        const keys = {};

        document.addEventListener('keydown', (e) => keys[e.key.toLowerCase()] = true);
        document.addEventListener('keyup', (e) => keys[e.key.toLowerCase()] = false);

        function drawPong() {
            // Background
            const gradient = pongCtx.createLinearGradient(0, 0, pongCanvas.width, pongCanvas.height);
            gradient.addColorStop(0, 'rgba(26, 26, 46, 0.8)');
            gradient.addColorStop(1, 'rgba(22, 33, 62, 0.8)');
            pongCtx.fillStyle = gradient;
            pongCtx.fillRect(0, 0, pongCanvas.width, pongCanvas.height);

            // Center line animation
            pongCtx.strokeStyle = 'rgba(255, 255, 255, 0.3)';
            pongCtx.setLineDash([10, 10]);
            pongCtx.lineWidth = 2;
            pongCtx.beginPath();
            pongCtx.moveTo(pongCanvas.width / 2, 0);
            pongCtx.lineTo(pongCanvas.width / 2, pongCanvas.height);
            pongCtx.stroke();
            pongCtx.setLineDash([]);

            // Paddles with glow
            pongCtx.fillStyle = '#00FF00';
            pongCtx.shadowColor = 'rgba(0, 255, 0, 0.8)';
            pongCtx.shadowBlur = 15;
            pongCtx.fillRect(player1.x, player1.y, player1.width, player1.height);
            pongCtx.fillStyle = '#FF69B4';
            pongCtx.shadowColor = 'rgba(255, 105, 180, 0.8)';
            pongCtx.fillRect(player2.x, player2.y, player2.width, player2.height);

            // Ball with glow
            pongCtx.fillStyle = '#00D4FF';
            pongCtx.shadowColor = 'rgba(0, 212, 255, 0.9)';
            pongCtx.shadowBlur = 20;
            pongCtx.beginPath();
            pongCtx.arc(ball.x, ball.y, ball.radius, 0, Math.PI * 2);
            pongCtx.fill();
            pongCtx.shadowBlur = 0;

            // Scores
            pongCtx.fillStyle = 'white';
            pongCtx.font = 'bold 50px Arial';
            pongCtx.fillText(player1.score, pongCanvas.width / 4, 60);
            pongCtx.fillText(player2.score, (3 * pongCanvas.width) / 4 - 40, 60);
        }

        function updatePong() {
            if (keys['w'] && player1.y > 0) player1.y -= player1.speed;
            if (keys['s'] && player1.y + player1.height < pongCanvas.height) player1.y += player1.speed;
            if (keys['arrowup'] && player2.y > 0) player2.y -= player2.speed;
            if (keys['arrowdown'] && player2.y + player2.height < pongCanvas.height) player2.y += player2.speed;

            ball.x += ball.dx;
            ball.y += ball.dy;

            if (ball.y - ball.radius < 0 || ball.y + ball.radius > pongCanvas.height) {
                ball.dy = -ball.dy;
            }

            if (ball.x - ball.radius < player1.x + player1.width &&
                ball.y > player1.y && ball.y < player1.y + player1.height) {
                ball.dx = -ball.dx;
                ball.x = player1.x + player1.width + ball.radius;
            }

            if (ball.x + ball.radius > player2.x &&
                ball.y > player2.y && ball.y < player2.y + player2.height) {
                ball.dx = -ball.dx;
                ball.x = player2.x - ball.radius;
            }

            if (ball.x - ball.radius < 0) {
                player2.score++;
                document.getElementById('p2Score').textContent = player2.score;
                resetBall();
            }
            if (ball.x + ball.radius > pongCanvas.width) {
                player1.score++;
                document.getElementById('p1Score').textContent = player1.score;
                resetBall();
            }
        }

        function resetBall() {
            ball.x = pongCanvas.width / 2;
            ball.y = pongCanvas.height / 2;
            ball.dx = (Math.random() > 0.5 ? 1 : -1) * 5;
            ball.dy = (Math.random() > 0.5 ? 1 : -1) * 5;
        }

        let pongRunning = false;

        function pongLoop() {
            updatePong();
            drawPong();
            if (pongRunning) {
                requestAnimationFrame(pongLoop);
            }
        }

        function startPong() {
            if (!pongRunning) {
                pongRunning = true;
                pongLoop();
            }
        }

        function resetPong() {
            player1.score = 0;
            player2.score = 0;
            document.getElementById('p1Score').textContent = 0;
            document.getElementById('p2Score').textContent = 0;
            pongRunning = false;
            resetBall();
            drawPong();
        }

        // Initialize
        createParticles();
        drawGame();
        drawPong();
    </script>
</body>
</html>
