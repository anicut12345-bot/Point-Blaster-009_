<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>Box Clicker Challenge - Mobile Game</title>
    <style>
        /* Prevent zooming and ensure mobile view */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            -webkit-touch-callout: none;
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;
            touch-action: manipulation;
        }
        
        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
            position: fixed;
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #fff;
            font-family: 'Arial Rounded MT Bold', 'Arial', sans-serif;
        }
        
        /* Home Page */
        #home-page {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
            padding: 20px;
            z-index: 10;
            overflow-y: auto;
            -webkit-overflow-scrolling: touch;
        }
        
        .home-header {
            text-align: center;
            margin-top: 20px;
            width: 100%;
        }
        
        .game-title {
            font-size: 2.8rem;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #00ffff, #ff00ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 15px rgba(0, 255, 255, 0.5);
            letter-spacing: 1px;
            line-height: 1.2;
        }
        
        .game-subtitle {
            font-size: 1.2rem;
            color: #a0e7ff;
            margin-bottom: 30px;
            padding: 0 10px;
        }
        
        .game-logo {
            font-size: 4rem;
            margin-bottom: 20px;
            text-shadow: 0 0 20px rgba(0, 255, 255, 0.7);
        }
        
        .start-button-container {
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
            margin: 30px 0;
        }
        
        .start-btn {
            width: 85%;
            max-width: 300px;
            padding: 22px 20px;
            font-size: 1.5rem;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
            letter-spacing: 1px;
            text-transform: uppercase;
        }
        
        #start-game-btn {
            background: linear-gradient(90deg, #00cc66, #00ff88);
            color: #003311;
        }
        
        #select-level-btn {
            background: linear-gradient(90deg, #ffaa00, #ffcc00);
            color: #332200;
        }
        
        #how-to-play-btn {
            background: linear-gradient(90deg, #3366ff, #6699ff);
            color: white;
        }
        
        .level-selection {
            background-color: rgba(0, 0, 0, 0.7);
            border-radius: 20px;
            padding: 20px;
            width: 90%;
            max-width: 500px;
            margin: 20px auto;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 3px solid #4444ff;
            display: none;
            position: relative;
        }
        
        .level-selection h2 {
            color: #00ffff;
            margin-bottom: 20px;
            font-size: 1.8rem;
            text-align: center;
        }
        
        .close-levels-btn {
            position: absolute;
            top: 10px;
            right: 15px;
            background: #ff3366;
            color: white;
            border: none;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            font-size: 1.2rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .levels-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
        }
        
        .level-card {
            background: linear-gradient(135deg, #2a2a5a, #444488);
            border-radius: 15px;
            padding: 15px 10px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            border: 2px solid transparent;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        .level-card:hover, .level-card:active {
            transform: scale(1.05);
        }
        
        .level-card.locked {
            background: linear-gradient(135deg, #444444, #666666);
            cursor: not-allowed;
            opacity: 0.7;
        }
        
        .level-card.unlocked {
            background: linear-gradient(135deg, #2a2a5a, #444488);
            border-color: #00ffff;
        }
        
        .level-card.completed {
            background: linear-gradient(135deg, #006644, #00aa66);
            border-color: #00ff88;
        }
        
        .level-number {
            font-size: 1.8rem;
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .level-target {
            font-size: 0.9rem;
            color: #ffcc00;
        }
        
        .lock-icon {
            font-size: 1.5rem;
            color: #ff6666;
            margin-bottom: 5px;
        }
        
        .instructions-panel {
            background-color: rgba(0, 0, 0, 0.8);
            border-radius: 20px;
            padding: 25px;
            width: 90%;
            max-width: 500px;
            margin: 20px auto;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 3px solid #00ffff;
            display: none;
            position: relative;
        }
        
        .instructions-panel h2 {
            color: #00ffff;
            margin-bottom: 20px;
            font-size: 1.8rem;
            text-align: center;
        }
        
        .close-instructions-btn {
            position: absolute;
            top: 10px;
            right: 15px;
            background: #ff3366;
            color: white;
            border: none;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            font-size: 1.2rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .instructions-content {
            max-height: 300px;
            overflow-y: auto;
            padding-right: 10px;
        }
        
        .instruction-item {
            margin-bottom: 15px;
            padding: 15px;
            background-color: rgba(40, 40, 80, 0.6);
            border-radius: 10px;
            border-left: 4px solid #00ff88;
        }
        
        .instruction-item h3 {
            color: #88ddff;
            margin-bottom: 8px;
            font-size: 1.2rem;
        }
        
        .instruction-item p {
            color: #ccccff;
            line-height: 1.4;
        }
        
        .highlight {
            color: #ffff00;
            font-weight: bold;
        }
        
        .danger {
            color: #ff6666;
            font-weight: bold;
        }
        
        .success {
            color: #00ff88;
            font-weight: bold;
        }
        
        .home-footer {
            text-align: center;
            padding: 20px 0;
            color: #88aaff;
            font-size: 0.9rem;
            width: 100%;
        }
        
        /* Game Page */
        #game-page {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: none;
            flex-direction: column;
            padding: 10px;
            background: linear-gradient(135deg, #0f0c29, #302b63);
            z-index: 20;
        }
        
        .game-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            padding: 10px 5px;
            margin-bottom: 10px;
            background-color: rgba(0, 0, 0, 0.5);
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            border: 2px solid #00ffff;
        }
        
        .game-title-small {
            font-size: 1.5rem;
            font-weight: bold;
            background: linear-gradient(90deg, #00ffff, #ff00ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            padding-left: 10px;
        }
        
        .back-to-home-btn {
            background: linear-gradient(90deg, #3366ff, #6699ff);
            color: white;
            border: none;
            border-radius: 20px;
            padding: 8px 15px;
            font-size: 0.9rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .stats-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            width: 100%;
            margin-bottom: 15px;
        }
        
        .stat-box {
            background-color: rgba(20, 20, 60, 0.7);
            border-radius: 12px;
            padding: 12px;
            text-align: center;
            border: 1px solid #5555ff;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }
        
        .stat-box h3 {
            font-size: 0.9rem;
            margin-bottom: 5px;
            color: #88ddff;
        }
        
        .stat-box .value {
            font-size: 1.5rem;
            font-weight: bold;
            text-shadow: 0 0 8px currentColor;
        }
        
        #time-left {
            color: #ffff00;
        }
        
        #current-level {
            color: #00ff88;
        }
        
        #level-score {
            color: #ff66cc;
        }
        
        #level-target {
            color: #ffaa00;
        }
        
        .level-info {
            width: 100%;
            background-color: rgba(0, 0, 0, 0.4);
            border-radius: 15px;
            padding: 15px;
            margin-bottom: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            border: 2px solid #4444ff;
        }
        
        .level-info h3 {
            color: #88ddff;
            margin-bottom: 8px;
            font-size: 1.2rem;
        }
        
        .target-display {
            font-size: 1.4rem;
            color: #ffff00;
            font-weight: bold;
            margin: 10px 0;
        }
        
        .progress-container {
            width: 100%;
            height: 20px;
            background-color: rgba(60, 60, 100, 0.6);
            border-radius: 10px;
            margin-top: 10px;
            overflow: hidden;
            border: 2px solid #4444ff;
        }
        
        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #00cc66, #00ff88);
            border-radius: 8px;
            width: 0%;
            transition: width 0.3s;
        }
        
        #game-area {
            flex: 1;
            width: 100%;
            background-color: rgba(5, 5, 25, 0.8);
            border-radius: 15px;
            position: relative;
            overflow: hidden;
            margin-bottom: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.6);
            border: 3px solid #5555ff;
            touch-action: manipulation;
        }
        
        .box {
            position: absolute;
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.15s;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: white;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            animation: float 3s ease-in-out infinite;
            touch-action: manipulation;
            -webkit-user-select: none;
            user-select: none;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }
        
        .box:active {
            transform: scale(0.9) !important;
        }
        
        .game-controls {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            width: 100%;
            margin-bottom: 15px;
        }
        
        .game-btn {
            padding: 15px 10px;
            font-size: 1rem;
            font-weight: bold;
            border: none;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 5px;
            touch-action: manipulation;
        }
        
        .game-btn:active {
            transform: translateY(3px);
        }
        
        #start-level-btn {
            background: linear-gradient(90deg, #00cc66, #00ff88);
            color: #003311;
        }
        
        #pause-btn {
            background: linear-gradient(90deg, #ffaa00, #ffcc00);
            color: #332200;
        }
        
        #sound-toggle-btn {
            background: linear-gradient(90deg, #8a2be2, #9370db);
            color: white;
        }
        
        .combo-indicator {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: rgba(0, 0, 0, 0.7);
            padding: 8px 15px;
            border-radius: 10px;
            font-weight: bold;
            color: #ffcc00;
            font-size: 1.2rem;
            display: none;
            border: 2px solid #ffcc00;
            z-index: 5;
        }
        
        /* Game Messages */
        .game-message {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(0, 0, 0, 0.95);
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            z-index: 1000;
            box-shadow: 0 0 50px rgba(0, 255, 255, 0.5);
            border: 3px solid #00ffff;
            width: 90%;
            max-width: 400px;
            display: none;
        }
        
        .game-message h2 {
            font-size: 2rem;
            margin-bottom: 15px;
        }
        
        .game-message p {
            font-size: 1.1rem;
            margin-bottom: 20px;
            line-height: 1.4;
        }
        
        .game-message button {
            margin: 10px 5px;
            background: linear-gradient(90deg, #00cc66, #00ff88);
            color: #003311;
            font-size: 1.1rem;
            padding: 12px 25px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            width: 100%;
            max-width: 200px;
        }
        
        .winner-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            z-index: 2000;
            display: none;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            text-align: center;
            padding: 20px;
        }
        
        .trophy {
            font-size: 8rem;
            animation: bounce 2s infinite, glow 2s infinite alternate;
            margin-bottom: 20px;
        }
        
        .medal {
            font-size: 5rem;
            position: absolute;
            animation: spin 3s linear infinite, glow 2s infinite alternate;
        }
        
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #ffcc00;
            animation: confetti-fall 5s linear infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        @keyframes glow {
            0% { text-shadow: 0 0 10px #ffcc00; }
            100% { text-shadow: 0 0 30px #ffcc00, 0 0 40px #ff9900; }
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        @keyframes confetti-fall {
            0% { transform: translateY(-100px) rotate(0deg); opacity: 1; }
            100% { transform: translateY(1000px) rotate(720deg); opacity: 0; }
        }
        
        .winner-message {
            font-size: 2.2rem;
            color: #ffcc00;
            text-align: center;
            margin-top: 20px;
            animation: pulse 1.5s infinite;
        }
        
        /* Responsive adjustments */
        @media (min-width: 768px) {
            .game-title {
                font-size: 3.5rem;
            }
            
            .start-btn {
                max-width: 400px;
            }
            
            #game-area {
                max-height: 500px;
            }
        }
        
        @media (max-height: 700px) {
            .game-title {
                font-size: 2.2rem;
            }
            
            .game-subtitle {
                font-size: 1rem;
                margin-bottom: 20px;
            }
            
            .start-button-container {
                margin: 15px 0;
            }
            
            .start-btn {
                padding: 18px 20px;
                font-size: 1.3rem;
            }
        }
        
        @media (max-height: 600px) {
            .home-header {
                margin-top: 10px;
            }
            
            .game-title {
                font-size: 2rem;
            }
            
            .game-subtitle {
                font-size: 0.9rem;
                margin-bottom: 15px;
            }
            
            .game-logo {
                font-size: 3rem;
                margin-bottom: 10px;
            }
        }
        
        .pulse {
            animation: pulse 0.5s ease-in-out;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        .shake {
            animation: shake 0.5s ease-in-out;
        }
        
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            10%, 30%, 50%, 70%, 90% { transform: translateX(-5px); }
            20%, 40%, 60%, 80% { transform: translateX(5px); }
        }
        
        /* Hide scrollbar but allow scrolling */
        .instructions-content::-webkit-scrollbar {
            width: 5px;
        }
        
        .instructions-content::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
        }
        
        .instructions-content::-webkit-scrollbar-thumb {
            background: #00ffff;
            border-radius: 10px;
        }
        
        /* Prevent text selection */
        .no-select {
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;
        }
    </style>
</head>
<body class="no-select">
    <!-- Home Page -->
    <div id="home-page">
        <div class="home-header">
            <div class="game-logo">🎮</div>
            <h1 class="game-title">BOX CLICKER CHALLENGE</h1>
            <p class="game-subtitle">Test your speed! Complete 10 levels in 60 seconds each</p>
        </div>
        
        <div class="start-button-container">
            <button id="start-game-btn" class="start-btn">
                🚀 START GAME
            </button>
            <button id="select-level-btn" class="start-btn">
                📊 SELECT LEVEL
            </button>
            <button id="how-to-play-btn" class="start-btn">
                ❓ HOW TO PLAY
            </button>
        </div>
        
        <div class="level-selection" id="level-selection">
            <button class="close-levels-btn" id="close-levels-btn">✕</button>
            <h2>SELECT LEVEL</h2>
            <div class="levels-grid" id="levels-grid">
                <!-- Levels will be generated here -->
            </div>
        </div>
        
        <div class="instructions-panel" id="instructions-panel">
            <button class="close-instructions-btn" id="close-instructions-btn">✕</button>
            <h2>HOW TO PLAY</h2>
            <div class="instructions-content">
                <div class="instruction-item">
                    <h3>🎯 OBJECTIVE</h3>
                    <p>Complete <span class="highlight">10 levels</span>, each with <span class="danger">60 seconds</span> to reach the target score.</p>
                </div>
                <div class="instruction-item">
                    <h3>🕹️ CONTROLS</h3>
                    <p>Tap boxes quickly to earn points. Regular boxes give <span class="highlight">10 points</span>, golden boxes give <span class="success">50 points</span>.</p>
                </div>
                <div class="instruction-item">
                    <h3>🔥 STRATEGY</h3>
                    <p>Create <span class="highlight">combos</span> by tapping boxes rapidly for score multipliers. Watch the timer!</p>
                </div>
                <div class="instruction-item">
                    <h3>🏆 PROGRESSION</h3>
                    <p>Level 1: 1000 points, Level 2: 2000 points, up to Level 10: 10000 points.</p>
                </div>
                <div class="instruction-item">
                    <h3>🎵 SOUND</h3>
                    <p>Toggle sound effects on/off during gameplay. Each box tap has a satisfying sound!</p>
                </div>
            </div>
        </div>
        
        <div class="home-footer">
            <p>Tap fast, think faster! Complete all levels to become the Box Clicker Champion! 🏆</p>
            <p style="margin-top: 10px; font-size: 0.8rem;">Mobile Optimized • No Zoom • Touch Friendly</p>
        </div>
    </div>
    
    <!-- Game Page -->
    <div id="game-page">
        <div class="game-header">
            <div class="game-title-small">BOX CLICKER</div>
            <button class="back-to-home-btn" id="back-to-home-btn">🏠 HOME</button>
        </div>
        
        <div class="stats-container">
            <div class="stat-box">
                <h3>TIME LEFT</h3>
                <div id="time-left" class="value">60s</div>
            </div>
            <div class="stat-box">
                <h3>LEVEL</h3>
                <div id="current-level" class="value">1</div>
            </div>
            <div class="stat-box">
                <h3>SCORE</h3>
                <div id="level-score" class="value">0</div>
            </div>
            <div class="stat-box">
                <h3>TARGET</h3>
                <div id="level-target" class="value">1000</div>
            </div>
        </div>
        
        <div class="level-info">
            <h3>LEVEL <span id="level-number">1</span> CHALLENGE</h3>
            <div class="target-display">Score <span id="target-display">1000</span> points</div>
            <div class="progress-container">
                <div id="progress-bar" class="progress-bar"></div>
            </div>
        </div>
        
        <div id="game-area">
            <div class="combo-indicator" id="combo-indicator">COMBO x1</div>
            <!-- Boxes will appear here -->
        </div>
        
        <div class="game-controls">
            <button id="start-level-btn" class="game-btn">
                <span style="font-size: 1.3rem;">▶️</span>
                <span>START</span>
            </button>
            <button id="pause-btn" class="game-btn">
                <span style="font-size: 1.3rem;">⏸️</span>
                <span>PAUSE</span>
            </button>
            <button id="sound-toggle-btn" class="game-btn">
                <span style="font-size: 1.3rem;" id="sound-icon">🔊</span>
                <span id="sound-text">SOUND ON</span>
            </button>
        </div>
    </div>
    
    <!-- Game Message (Time's Up) -->
    <div class="game-message" id="game-message">
        <h2 id="message-title">TIME'S UP!</h2>
        <p id="message-text">You didn't reach the target score in time!</p>
        <div id="message-stats"></div>
        <button id="try-again-button">TRY AGAIN</button>
        <button id="back-to-home-from-fail">MAIN MENU</button>
    </div>
    
    <!-- Winner Animation -->
    <div class="winner-animation" id="winner-animation">
        <div class="trophy">🏆</div>
        <div class="medal">🥇</div>
        <div class="winner-message" id="winner-message">LEVEL 1 COMPLETE!</div>
        <div id="winner-stats"></div>
        <button id="continue-button">NEXT LEVEL</button>
        <button id="back-to-home-from-win">MAIN MENU</button>
    </div>

    <script>
        // Game variables
        let levelScore = 0;
        let timeLeft = 60;
        let currentLevel = 1;
        let gameActive = false;
        let gamePaused = false;
        let gameInterval;
        let timeInterval;
        let boxes = [];
        let boxSpawnRate = 800;
        let maxBoxesOnScreen = 8;
        let boxLifetime = 2500;
        let combo = 0;
        let comboTimeout;
        let soundEnabled = true;
        
        // Level targets: Level 1 = 1000, Level 2 = 2000, ..., Level 10 = 10000
        const levelTargets = [0, 1000, 2000, 3000, 4000, 5000, 6000, 7000, 8000, 9000, 10000];
        
        // Level colors for boxes
        const levelColors = [
            ['#FF6B6B', '#FF8E8E'], // Level 1
            ['#FFA726', '#FFCC80'], // Level 2
            ['#66BB6A', '#A5D6A7'], // Level 3
            ['#42A5F5', '#90CAF9'], // Level 4
            ['#AB47BC', '#CE93D8'], // Level 5
            ['#FF7043', '#FFAB91'], // Level 6
            ['#26C6DA', '#80DEEA'], // Level 7
            ['#D4E157', '#E6EE9C'], // Level 8
            ['#FFCA28', '#FFE082'], // Level 9
            ['#EF5350', '#EF9A9A']  // Level 10
        ];
        
        // Sound effects using Web Audio API
        let audioContext;
        let clickSoundBuffer;
        let goldenClickSoundBuffer;
        let levelCompleteSoundBuffer;
        let levelFailSoundBuffer;
        
        // DOM elements
        const homePage = document.getElementById('home-page');
        const gamePage = document.getElementById('game-page');
        const levelSelection = document.getElementById('level-selection');
        const instructionsPanel = document.getElementById('instructions-panel');
        const levelsGrid = document.getElementById('levels-grid');
        const gameArea = document.getElementById('game-area');
        const timeLeftElement = document.getElementById('time-left');
        const currentLevelElement = document.getElementById('current-level');
        const levelScoreElement = document.getElementById('level-score');
        const levelTargetElement = document.getElementById('level-target');
        const levelNumberElement = document.getElementById('level-number');
        const targetDisplayElement = document.getElementById('target-display');
        const progressBar = document.getElementById('progress-bar');
        const startGameBtn = document.getElementById('start-game-btn');
        const selectLevelBtn = document.getElementById('select-level-btn');
        const howToPlayBtn = document.getElementById('how-to-play-btn');
        const closeLevelsBtn = document.getElementById('close-levels-btn');
        const closeInstructionsBtn = document.getElementById('close-instructions-btn');
        const startLevelBtn = document.getElementById('start-level-btn');
        const pauseBtn = document.getElementById('pause-btn');
        const soundToggleBtn = document.getElementById('sound-toggle-btn');
        const soundIcon = document.getElementById('sound-icon');
        const soundText = document.getElementById('sound-text');
        const backToHomeBtn = document.getElementById('back-to-home-btn');
        const gameMessage = document.getElementById('game-message');
        const messageTitle = document.getElementById('message-title');
        const messageText = document.getElementById('message-text');
        const messageStats = document.getElementById('message-stats');
        const tryAgainButton = document.getElementById('try-again-button');
        const backToHomeFromFail = document.getElementById('back-to-home-from-fail');
        const winnerAnimation = document.getElementById('winner-animation');
        const winnerMessage = document.getElementById('winner-message');
        const winnerStats = document.getElementById('winner-stats');
        const continueButton = document.getElementById('continue-button');
        const backToHomeFromWin = document.getElementById('back-to-home-from-win');
        const comboIndicator = document.getElementById('combo-indicator');
        
        // Initialize the game
        function initGame() {
            // Load saved data
            loadGameData();
            
            // Set up event listeners
            setupEventListeners();
            
            // Generate level cards
            generateLevelCards();
            
            // Initialize audio
            initAudio();
            
            // Show home page
            showHomePage();
        }
        
        // Load game data from localStorage
        function loadGameData() {
            // Load unlocked levels
            const unlockedLevels = localStorage.getItem('boxClickerMobileUnlockedLevels');
            if (unlockedLevels) {
                window.unlockedLevels = JSON.parse(unlockedLevels);
            } else {
                // Start with level 1 unlocked
                window.unlockedLevels = [1];
                localStorage.setItem('boxClickerMobileUnlockedLevels', JSON.stringify(window.unlockedLevels));
            }
            
            // Load high scores
            const highScores = localStorage.getItem('boxClickerMobileHighScores');
            if (highScores) {
                window.highScores = JSON.parse(highScores);
            } else {
                // Initialize empty high scores
                window.highScores = {};
                for (let i = 1; i <= 10; i++) {
                    window.highScores[i] = { score: 0, timeLeft: 0 };
                }
                localStorage.setItem('boxClickerMobileHighScores', JSON.stringify(window.highScores));
            }
            
            // Load sound preference
            const soundPref = localStorage.getItem('boxClickerMobileSoundEnabled');
            if (soundPref !== null) {
                soundEnabled = soundPref === 'true';
                updateSoundUI();
            }
        }
        
        // Save game data to localStorage
        function saveGameData() {
            localStorage.setItem('boxClickerMobileUnlockedLevels', JSON.stringify(window.unlockedLevels));
            localStorage.setItem('boxClickerMobileHighScores', JSON.stringify(window.highScores));
            localStorage.setItem('boxClickerMobileSoundEnabled', soundEnabled.toString());
        }
        
        // Initialize audio
        function initAudio() {
            try {
                // Create audio context
                audioContext = new (window.AudioContext || window.webkitAudioContext)();
                
                // Create sounds
                createClickSound();
                createGoldenClickSound();
                createLevelCompleteSound();
                createLevelFailSound();
                
                console.log("Audio initialized successfully");
            } catch (e) {
                console.log("Audio initialization failed:", e);
                soundEnabled = false;
                updateSoundUI();
            }
        }
        
        // Create a simple click sound (10 points)
        function createClickSound() {
            if (!audioContext) return;
            
            const duration = 0.1;
            const sampleRate = audioContext.sampleRate;
            const frameCount = Math.floor(duration * sampleRate);
            
            const buffer = audioContext.createBuffer(1, frameCount, sampleRate);
            const data = buffer.getChannelData(0);
            
            // Create a simple "pop" sound
            for (let i = 0; i < frameCount; i++) {
                const t = i / sampleRate;
                data[i] = Math.sin(2 * Math.PI * 800 * t) * Math.exp(-t * 30);
            }
            
            clickSoundBuffer = buffer;
        }
        
        // Create golden click sound (50 points)
        function createGoldenClickSound() {
            if (!audioContext) return;
            
            const duration = 0.2;
            const sampleRate = audioContext.sampleRate;
            const frameCount = Math.floor(duration * sampleRate);
            
            const buffer = audioContext.createBuffer(1, frameCount, sampleRate);
            const data = buffer.getChannelData(0);
            
            // Create a more pleasant "chime" sound
            for (let i = 0; i < frameCount; i++) {
                const t = i / sampleRate;
                data[i] = (Math.sin(2 * Math.PI * 1200 * t) * 0.6 + 
                          Math.sin(2 * Math.PI * 1800 * t) * 0.4) * 
                          Math.exp(-t * 15);
            }
            
            goldenClickSoundBuffer = buffer;
        }
        
        // Create level complete sound
        function createLevelCompleteSound() {
            if (!audioContext) return;
            
            const duration = 1.5;
            const sampleRate = audioContext.sampleRate;
            const frameCount = Math.floor(duration * sampleRate);
            
            const buffer = audioContext.createBuffer(1, frameCount, sampleRate);
            const data = buffer.getChannelData(0);
            
            // Create a victory fanfare
            for (let i = 0; i < frameCount; i++) {
                const t = i / sampleRate;
                let value = 0;
                
                if (t < 0.5) {
                    value = Math.sin(2 * Math.PI * 523.25 * t) * Math.exp(-t * 4);
                } else if (t < 1.0) {
                    value = Math.sin(2 * Math.PI * 659.25 * (t - 0.5)) * Math.exp(-(t - 0.5) * 4);
                } else {
                    value = Math.sin(2 * Math.PI * 783.99 * (t - 1.0)) * Math.exp(-(t - 1.0) * 4);
                }
                
                data[i] = value * 0.5;
            }
            
            levelCompleteSoundBuffer = buffer;
        }
        
        // Create level fail sound
        function createLevelFailSound() {
            if (!audioContext) return;
            
            const duration = 0.8;
            const sampleRate = audioContext.sampleRate;
            const frameCount = Math.floor(duration * sampleRate);
            
            const buffer = audioContext.createBuffer(1, frameCount, sampleRate);
            const data = buffer.getChannelData(0);
            
            // Create a descending "fail" sound
            for (let i = 0; i < frameCount; i++) {
                const t = i / sampleRate;
                const frequency = 400 * (1 - t * 0.8);
                data[i] = Math.sin(2 * Math.PI * frequency * t) * Math.exp(-t * 4);
            }
            
            levelFailSoundBuffer = buffer;
        }
        
        // Play sound effect
        function playSound(buffer, volume = 0.5) {
            if (!soundEnabled || !audioContext || !buffer) return;
            
            try {
                // Resume audio context if suspended
                if (audioContext.state === 'suspended') {
                    audioContext.resume();
                }
                
                const source = audioContext.createBufferSource();
                const gainNode = audioContext.createGain();
                
                source.buffer = buffer;
                gainNode.gain.value = volume;
                
                source.connect(gainNode);
                gainNode.connect(audioContext.destination);
                
                source.start(0);
                
                // Clean up
                source.onended = () => {
                    source.disconnect();
                    gainNode.disconnect();
                };
            } catch (e) {
                console.log("Sound play error:", e);
            }
        }
        
        // Set up event listeners
        function setupEventListeners() {
            // Home page buttons
            startGameBtn.addEventListener('click', () => {
                currentLevel = 1;
                startGame();
            });
            
            selectLevelBtn.addEventListener('click', () => {
                levelSelection.style.display = 'block';
                generateLevelCards();
            });
            
            howToPlayBtn.addEventListener('click', () => {
                instructionsPanel.style.display = 'block';
            });
            
            closeLevelsBtn.addEventListener('click', () => {
                levelSelection.style.display = 'none';
            });
            
            closeInstructionsBtn.addEventListener('click', () => {
                instructionsPanel.style.display = 'none';
            });
            
            // Game page buttons
            startLevelBtn.addEventListener('click', startLevel);
            pauseBtn.addEventListener('click', togglePause);
            soundToggleBtn.addEventListener('click', toggleSound);
            backToHomeBtn.addEventListener('click', showHomePage);
            
            // Game message buttons
            tryAgainButton.addEventListener('click', () => {
                gameMessage.style.display = 'none';
                resetLevel();
                startLevel();
            });
            
            backToHomeFromFail.addEventListener('click', () => {
                gameMessage.style.display = 'none';
                showHomePage();
            });
            
            // Winner animation buttons
            continueButton.addEventListener('click', nextLevel);
            backToHomeFromWin.addEventListener('click', () => {
                winnerAnimation.style.display = 'none';
                showHomePage();
            });
            
            // Prevent zoom on double tap
            document.addEventListener('touchstart', function(event) {
                if (event.touches.length > 1) {
                    event.preventDefault();
                }
            }, { passive: false });
            
            let lastTouchEnd = 0;
            document.addEventListener('touchend', function(event) {
                const now = (new Date()).getTime();
                if (now - lastTouchEnd <= 300) {
                    event.preventDefault();
                }
                lastTouchEnd = now;
            }, false);
            
            // Prevent context menu on long press
            document.addEventListener('contextmenu', function(e) {
                e.preventDefault();
                return false;
            });
        }
        
        // Generate level cards for level selection
        function generateLevelCards() {
            levelsGrid.innerHTML = '';
            
            for (let i = 1; i <= 10; i++) {
                const levelCard = document.createElement('div');
                levelCard.className = 'level-card';
                
                // Check if level is unlocked
                if (window.unlockedLevels.includes(i)) {
                    levelCard.classList.add('unlocked');
                    
                    // Check if level is completed (has a high score)
                    if (window.highScores[i].score > 0) {
                        levelCard.classList.add('completed');
                    }
                    
                    levelCard.addEventListener('click', () => {
                        currentLevel = i;
                        startGame();
                        levelSelection.style.display = 'none';
                    });
                } else {
                    levelCard.classList.add('locked');
                    levelCard.innerHTML = `
                        <div class="lock-icon">🔒</div>
                        <div class="level-number">${i}</div>
                        <div class="level-target">${levelTargets[i]} pts</div>
                    `;
                }
                
                if (!levelCard.classList.contains('locked')) {
                    levelCard.innerHTML = `
                        <div class="level-number">${i}</div>
                        <div class="level-target">${levelTargets[i]} pts</div>
                        ${window.highScores[i].score > 0 ? 
                            `<div style="margin-top: 5px; color: #00ff88; font-size: 0.8rem;">Best: ${window.highScores[i].score}</div>` : 
                            ''}
                    `;
                }
                
                levelsGrid.appendChild(levelCard);
            }
        }
        
        // Show home page
        function showHomePage() {
            homePage.style.display = 'flex';
            gamePage.style.display = 'none';
            levelSelection.style.display = 'none';
            instructionsPanel.style.display = 'none';
            
            // Reset game if it's active
            if (gameActive) {
                resetGame();
            }
            
            // Update level cards
            generateLevelCards();
        }
        
        // Show game page
        function startGame() {
            homePage.style.display = 'none';
            gamePage.style.display = 'flex';
            
            // Reset level for the selected level
            resetLevel();
            updateLevelInfo();
        }
        
        // Start the current level
        function startLevel() {
            if (gameActive) return;
            
            gameActive = true;
            gamePaused = false;
            startLevelBtn.disabled = true;
            startLevelBtn.innerHTML = '<span style="font-size: 1.3rem;">⏳</span><span>RUNNING</span>';
            
            // Resume audio context if needed
            if (audioContext && audioContext.state === 'suspended') {
                audioContext.resume();
            }
            
            // Start timer
            timeInterval = setInterval(() => {
                if (!gamePaused) {
                    timeLeft--;
                    timeLeftElement.textContent = `${timeLeft}s`;
                    
                    // Update time color based on remaining time
                    if (timeLeft <= 10) {
                        timeLeftElement.style.color = "#ff3333";
                        timeLeftElement.classList.add("shake");
                    } else if (timeLeft <= 20) {
                        timeLeftElement.style.color = "#ff9900";
                    } else {
                        timeLeftElement.style.color = "#ffff00";
                    }
                    
                    // Check if time ran out
                    if (timeLeft <= 0) {
                        levelFailed();
                    }
                }
            }, 1000);
            
            // Start spawning boxes
            gameInterval = setInterval(() => {
                if (!gamePaused) {
                    spawnBox();
                }
            }, boxSpawnRate);
            
            // Spawn initial boxes
            for (let i = 0; i < 3; i++) {
                setTimeout(() => spawnBox(), i * 300);
            }
        }
        
        // Reset the current level
        function resetLevel() {
            levelScore = 0;
            timeLeft = 60;
            gameActive = false;
            gamePaused = false;
            boxSpawnRate = 800 - (currentLevel - 1) * 50;
            maxBoxesOnScreen = Math.max(4, 8 - (currentLevel - 1) * 0.5);
            boxLifetime = Math.max(1500, 2500 - (currentLevel - 1) * 100);
            combo = 0;
            
            clearInterval(gameInterval);
            clearInterval(timeInterval);
            clearTimeout(comboTimeout);
            
            updateUI();
            clearBoxes();
            
            startLevelBtn.disabled = false;
            startLevelBtn.innerHTML = '<span style="font-size: 1.3rem;">▶️</span><span>START</span>';
            pauseBtn.innerHTML = '<span style="font-size: 1.3rem;">⏸️</span><span>PAUSE</span>';
            
            // Reset progress bar
            progressBar.style.width = "0%";
            
            // Hide combo indicator
            comboIndicator.style.display = "none";
        }
        
        // Reset the entire game
        function resetGame() {
            resetLevel();
            currentLevel = 1;
            updateLevelInfo();
        }
        
        // Toggle pause/resume
        function togglePause() {
            if (!gameActive) return;
            
            gamePaused = !gamePaused;
            
            if (gamePaused) {
                pauseBtn.innerHTML = '<span style="font-size: 1.3rem;">▶️</span><span>RESUME</span>';
                
                // Pause box animations
                boxes.forEach(box => {
                    box.style.animationPlayState = 'paused';
                });
            } else {
                pauseBtn.innerHTML = '<span style="font-size: 1.3rem;">⏸️</span><span>PAUSE</span>';
                
                // Resume box animations
                boxes.forEach(box => {
                    box.style.animationPlayState = 'running';
                });
            }
        }
        
        // Toggle sound on/off
        function toggleSound() {
            soundEnabled = !soundEnabled;
            updateSoundUI();
            saveGameData();
        }
        
        // Update sound UI
        function updateSoundUI() {
            if (soundEnabled) {
                soundIcon.textContent = '🔊';
                soundText.textContent = 'SOUND ON';
            } else {
                soundIcon.textContent = '🔇';
                soundText.textContent = 'SOUND OFF';
            }
        }
        
        // Level failed (time ran out)
        function levelFailed() {
            gameActive = false;
            clearInterval(gameInterval);
            clearInterval(timeInterval);
            clearTimeout(comboTimeout);
            
            // Play fail sound
            playSound(levelFailSoundBuffer, 0.3);
            
            messageTitle.textContent = "TIME'S UP!";
            messageText.textContent = `You didn't reach the target score for Level ${currentLevel}!`;
            messageTitle.style.color = "#ff3333";
            
            messageStats.innerHTML = `
                <div style="font-size: 1.2rem; margin: 10px 0; color: #00ffff;">Level Score: ${levelScore}</div>
                <div style="margin: 8px 0;">Target Score: ${levelTargets[currentLevel]}</div>
                <div style="margin: 8px 0;">Time Remaining: 0 seconds</div>
            `;
            
            gameMessage.style.display = "block";
        }
        
        // Level completed (reached target score)
        function levelCompleted() {
            gameActive = false;
            clearInterval(gameInterval);
            clearInterval(timeInterval);
            clearTimeout(comboTimeout);
            
            // Play victory sound
            playSound(levelCompleteSoundBuffer, 0.5);
            
            // Save high score if it's better
            if (levelScore > window.highScores[currentLevel].score) {
                window.highScores[currentLevel] = {
                    score: levelScore,
                    timeLeft: timeLeft
                };
                saveGameData();
            }
            
            // Unlock next level if not already unlocked
            if (currentLevel < 10 && !window.unlockedLevels.includes(currentLevel + 1)) {
                window.unlockedLevels.push(currentLevel + 1);
                saveGameData();
            }
            
            // Show winner animation
            showWinnerAnimation();
        }
        
        // Show winner animation
        function showWinnerAnimation() {
            winnerMessage.textContent = `LEVEL ${currentLevel} COMPLETE!`;
            winnerMessage.style.color = "#ffcc00";
            
            winnerStats.innerHTML = `
                <div style="font-size: 1.2rem; margin: 10px 0; color: #00ffff;">Level Score: ${levelScore}</div>
                <div style="margin: 8px 0;">Target Score: ${levelTargets[currentLevel]}</div>
                <div style="margin: 8px 0;">Time Remaining: ${timeLeft} seconds</div>
            `;
            
            // Create confetti
            createConfetti();
            
            // Show animation
            winnerAnimation.style.display = "flex";
        }
        
        // Create confetti for winner animation
        function createConfetti() {
            // Clear existing confetti
            const existingConfetti = document.querySelectorAll('.confetti');
            existingConfetti.forEach(confetti => confetti.remove());
            
            // Create new confetti
            for (let i = 0; i < 50; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                
                // Random position
                confetti.style.left = `${Math.random() * 100}vw`;
                
                // Random color
                const colors = ['#ffcc00', '#ff6666', '#66ff66', '#6666ff', '#ff66ff'];
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                
                // Random size
                const size = 5 + Math.random() * 15;
                confetti.style.width = `${size}px`;
                confetti.style.height = `${size}px`;
                
                // Random animation delay
                confetti.style.animationDelay = `${Math.random() * 5}s`;
                
                winnerAnimation.appendChild(confetti);
            }
        }
        
        // Move to next level
        function nextLevel() {
            if (currentLevel >= 10) {
                // Game completed!
                winnerMessage.textContent = "GAME COMPLETED! 🎉";
                winnerMessage.style.color = "#00ff88";
                winnerStats.innerHTML = `
                    <div style="font-size: 1.2rem; margin: 10px 0; color: #00ffff;">Congratulations!</div>
                    <div style="margin: 8px 0;">You completed all 10 levels!</div>
                    <div style="margin: 8px 0;">You are the ultimate Box Clicker Champion! 🏆</div>
                `;
                continueButton.textContent = "PLAY AGAIN";
                continueButton.onclick = () => {
                    winnerAnimation.style.display = "none";
                    showHomePage();
                };
                return;
            }
            
            // Hide winner animation
            winnerAnimation.style.display = "none";
            
            // Move to next level
            currentLevel++;
            
            // Reset level for the next level
            resetLevel();
            updateLevelInfo();
        }
        
        // Spawn a new box
        function spawnBox() {
            if (!gameActive || gamePaused) return;
            
            // Check if we've reached the maximum boxes on screen
            if (boxes.length >= maxBoxesOnScreen) {
                // Remove the oldest box
                if (boxes.length > 0) {
                    const oldBox = boxes.shift();
                    if (oldBox && oldBox.parentNode) {
                        gameArea.removeChild(oldBox);
                        
                        // Reset combo if a box disappears without being clicked
                        resetCombo();
                    }
                }
            }
            
            // Create new box element
            const box = document.createElement('div');
            box.className = 'box';
            
            // Set random position (within game area)
            const boxSize = 40 + Math.random() * 50; // 40-90px
            const maxX = gameArea.clientWidth - boxSize;
            const maxY = gameArea.clientHeight - boxSize;
            
            const posX = Math.random() * maxX;
            const posY = Math.random() * maxY;
            
            // Set box styles based on current level
            const colorIndex = Math.min(currentLevel - 1, levelColors.length - 1);
            const colors = levelColors[colorIndex];
            
            // Small chance for a golden box (bonus)
            const isGolden = Math.random() < 0.05;
            const boxColors = isGolden ? ['#FFD700', '#FFEC8B'] : colors;
            
            box.style.width = `${boxSize}px`;
            box.style.height = `${boxSize}px`;
            box.style.left = `${posX}px`;
            box.style.top = `${posY}px`;
            box.style.background = `radial-gradient(circle at 30% 30%, ${boxColors[0]}, ${boxColors[1]})`;
            box.style.fontSize = `${Math.max(16, boxSize/3)}px`;
            box.textContent = isGolden ? "+50" : "+10";
            
            if (isGolden) {
                box.style.boxShadow = '0 0 15px #FFD700';
                box.style.border = '2px solid #FFD700';
            }
            
            // Add click event
            box.addEventListener('click', () => clickBox(box, isGolden));
            box.addEventListener('touchstart', (e) => {
                e.preventDefault();
                clickBox(box, isGolden);
            }, { passive: false });
            
            // Add to game area and boxes array
            gameArea.appendChild(box);
            boxes.push(box);
            
            // Remove box after its lifetime expires
            setTimeout(() => {
                if (box.parentNode) {
                    const index = boxes.indexOf(box);
                    if (index > -1) {
                        boxes.splice(index, 1);
                    }
                    
                    // Fade out before removing
                    box.style.opacity = '0';
                    box.style.transform = 'scale(0.5)';
                    
                    setTimeout(() => {
                        if (box.parentNode) {
                            gameArea.removeChild(box);
                            
                            // Reset combo if a box disappears without being clicked
                            resetCombo();
                        }
                    }, 300);
                }
            }, boxLifetime);
        }
        
        // Handle box click
        function clickBox(box, isGolden) {
            if (!gameActive || gamePaused) return;
            
            // Play sound effect
            if (isGolden) {
                playSound(goldenClickSoundBuffer, 0.4);
            } else {
                playSound(clickSoundBuffer, 0.3);
            }
            
            // Increase combo
            combo++;
            updateCombo();
            
            // Calculate points based on combo and golden status
            const basePoints = isGolden ? 50 : 10;
            const comboMultiplier = Math.min(Math.floor(combo / 5) + 1, 5);
            const points = basePoints * comboMultiplier;
            
            // Update score
            levelScore += points;
            
            // Update UI
            levelScoreElement.textContent = levelScore;
            levelScoreElement.classList.add("pulse");
            
            // Update progress bar
            const progress = Math.min(100, (levelScore / levelTargets[currentLevel]) * 100);
            progressBar.style.width = `${progress}%`;
            
            // Check if level target reached
            if (levelScore >= levelTargets[currentLevel]) {
                levelCompleted();
                return;
            }
            
            // Remove pulse animation after it completes
            setTimeout(() => {
                levelScoreElement.classList.remove("pulse");
            }, 300);
            
            // Remove box from boxes array
            const index = boxes.indexOf(box);
            if (index > -1) {
                boxes.splice(index, 1);
            }
            
            // Show points gained
            const pointsPopup = document.createElement('div');
            pointsPopup.textContent = `+${points}`;
            pointsPopup.style.position = 'absolute';
            pointsPopup.style.left = box.style.left;
            pointsPopup.style.top = box.style.top;
            pointsPopup.style.color = isGolden ? '#FFD700' : '#FFFFFF';
            pointsPopup.style.fontSize = '20px';
            pointsPopup.style.fontWeight = 'bold';
            pointsPopup.style.textShadow = '0 0 5px #000';
            pointsPopup.style.zIndex = '5';
            pointsPopup.style.pointerEvents = 'none';
            gameArea.appendChild(pointsPopup);
            
            // Animate points popup
            let popupY = parseInt(box.style.top);
            const popupInterval = setInterval(() => {
                popupY -= 2;
                pointsPopup.style.top = `${popupY}px`;
                pointsPopup.style.opacity = parseFloat(pointsPopup.style.opacity || 1) - 0.02;
                
                if (parseFloat(pointsPopup.style.opacity || 1) <= 0) {
                    clearInterval(popupInterval);
                    if (pointsPopup.parentNode) {
                        pointsPopup.parentNode.removeChild(pointsPopup);
                    }
                }
            }, 30);
            
            // Animate and remove box
            box.style.transform = 'scale(1.2)';
            box.style.opacity = '0.5';
            
            setTimeout(() => {
                if (box.parentNode) {
                    gameArea.removeChild(box);
                }
            }, 150);
            
            // Reset combo timeout
            clearTimeout(comboTimeout);
            comboTimeout = setTimeout(resetCombo, 1500);
        }
        
        // Update combo display
        function updateCombo() {
            if (combo > 1) {
                comboIndicator.textContent = `COMBO x${Math.min(Math.floor(combo / 5) + 1, 5)}`;
                comboIndicator.style.display = "block";
                
                // Color based on combo multiplier
                const multiplier = Math.min(Math.floor(combo / 5) + 1, 5);
                if (multiplier >= 5) {
                    comboIndicator.style.color = "#ff3333";
                    comboIndicator.style.borderColor = "#ff3333";
                } else if (multiplier >= 3) {
                    comboIndicator.style.color = "#ff9900";
                    comboIndicator.style.borderColor = "#ff9900";
                } else {
                    comboIndicator.style.color = "#ffcc00";
                    comboIndicator.style.borderColor = "#ffcc00";
                }
            }
        }
        
        // Reset combo
        function resetCombo() {
            combo = 0;
            comboIndicator.style.display = "none";
        }
        
        // Clear all boxes from game area
        function clearBoxes() {
            // Remove all box elements
            while (gameArea.firstChild) {
                if (gameArea.firstChild.id !== 'combo-indicator') {
                    gameArea.removeChild(gameArea.firstChild);
                } else {
                    break;
                }
            }
            
            // Clear boxes array
            boxes = [];
        }
        
        // Update level information
        function updateLevelInfo() {
            levelNumberElement.textContent = currentLevel;
            levelTargetElement.textContent = levelTargets[currentLevel];
            targetDisplayElement.textContent = levelTargets[currentLevel];
            currentLevelElement.textContent = currentLevel;
            
            // Update level button text
            startLevelBtn.innerHTML = `<span style="font-size: 1.3rem;">▶️</span><span>START LEVEL ${currentLevel}</span>`;
        }
        
        // Update UI elements
        function updateUI() {
            timeLeftElement.textContent = `${timeLeft}s`;
            currentLevelElement.textContent = currentLevel;
            levelScoreElement.textContent = levelScore;
            levelTargetElement.textContent = levelTargets[currentLevel];
            
            // Reset time color
            if (timeLeft > 10) {
                timeLeftElement.style.color = "#ffff00";
            }
            
            // Reset time left
            timeLeft = 60;
            timeLeftElement.textContent = `${timeLeft}s`;
            timeLeftElement.style.color = "#ffff00";
            timeLeftElement.classList.remove("shake");
        }
        
        // Initialize the game when page loads
        window.addEventListener('load', initGame);
        
        // Initialize audio on first user interaction
        document.addEventListener('click', function initAudioOnClick() {
            if (!audioContext) {
                initAudio();
            }
            document.removeEventListener('click', initAudioOnClick);
        });
        
        // Prevent pull-to-refresh on mobile
        document.addEventListener('touchmove', function(e) {
            if (e.scale !== 1) {
                e.preventDefault();
            }
        }, { passive: false });
    </script>
</body>
</html>
