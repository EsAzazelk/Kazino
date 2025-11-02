<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FoCoin Casino 🎰</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
            color: white;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            padding: 20px;
            background: rgba(0, 0, 0, 0.7);
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            position: relative;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 10px;
        }
        
        .logo-icon {
            font-size: 2.5rem;
            color: gold;
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            text-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
            color: gold;
        }
        
        .user-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(0, 0, 0, 0.6);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        
        .balance {
            font-size: 1.5rem;
            font-weight: bold;
            color: gold;
        }
        
        .auth-section, .game-section {
            background: rgba(0, 0, 0, 0.7);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
        }
        
        .game-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .game-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            transition: transform 0.3s, background 0.3s;
            cursor: pointer;
        }
        
        .game-card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.2);
        }
        
        .game-icon {
            font-size: 3rem;
            margin-bottom: 15px;
        }
        
        .game-title {
            font-size: 1.3rem;
            margin-bottom: 10px;
        }
        
        .game-desc {
            font-size: 0.9rem;
            opacity: 0.8;
            margin-bottom: 15px;
        }
        
        .btn {
            background: linear-gradient(to right, #ff8a00, #da1b60);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .btn:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .btn-secondary {
            background: linear-gradient(to right, #4776E6, #8E54E9);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        
        input {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            border: none;
            background: rgba(255, 255, 255, 0.9);
            font-size: 1rem;
        }
        
        .hidden {
            display: none;
        }
        
        .game-area {
            text-align: center;
            padding: 20px;
        }
        
        .result {
            font-size: 1.5rem;
            margin: 20px 0;
            min-height: 40px;
        }
        
        .dice-container, .slot-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }
        
        .dice, .slot {
            width: 80px;
            height: 80px;
            background: white;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2.5rem;
            color: #333;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .bet-controls {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            margin: 20px 0;
        }
        
        .bet-amount {
            font-size: 1.2rem;
            font-weight: bold;
            color: gold;
            min-width: 80px;
        }
        
        .bet-btn {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            font-size: 1.2rem;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .bet-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
        }
        
        .stat-value {
            font-size: 1.8rem;
            font-weight: bold;
            color: gold;
            margin: 10px 0;
        }
        
        @keyframes win {
            0% { background-color: rgba(255, 215, 0, 0.3); }
            50% { background-color: rgba(255, 215, 0, 0.7); }
            100% { background-color: rgba(255, 215, 0, 0.3); }
        }
        
        .win-animation {
            animation: win 1s ease-in-out 3;
        }
        
        .tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .tab {
            padding: 10px 20px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
        }
        
        .tab.active {
            border-bottom: 3px solid gold;
            color: gold;
        }
        
        .history-list {
            max-height: 200px;
            overflow-y: auto;
            margin-top: 15px;
        }
        
        .history-item {
            padding: 10px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            justify-content: space-between;
        }
        
        .win {
            color: #4CAF50;
        }
        
        .loss {
            color: #F44336;
        }
        
        @media (max-width: 768px) {
            .game-grid {
                grid-template-columns: 1fr;
            }
            
            .user-info {
                flex-direction: column;
                gap: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <div class="logo-icon">₣</div>
                <h1>FoCoin Casino</h1>
            </div>
            <p>Ваше виртуальное казино с FoCoin!</p>
        </header>
        
        <div class="user-info">
            <div>
                <span id="username-display">Гость</span>
            </div>
            <div class="balance">
                Баланс: <span id="balance">0</span> ₣
            </div>
            <div>
                <button id="logout-btn" class="btn btn-secondary hidden">Выйти</button>
            </div>
        </div>
        
        <div id="auth-section" class="auth-section">
            <div class="tabs">
                <div class="tab active" id="login-tab">Вход</div>
                <div class="tab" id="register-tab">Регистрация</div>
            </div>
            
            <div id="login-form">
                <div class="form-group">
                    <label for="login-username">Имя пользователя</label>
                    <input type="text" id="login-username" placeholder="Введите имя пользователя">
                </div>
                <div class="form-group">
                    <label for="login-password">Пароль</label>
                    <input type="password" id="login-password" placeholder="Введите пароль">
                </div>
                <button id="login-btn" class="btn">Войти</button>
            </div>
            
            <div id="register-form" class="hidden">
                <div class="form-group">
                    <label for="register-username">Имя пользователя</label>
                    <input type="text" id="register-username" placeholder="Придумайте имя пользователя">
                </div>
                <div class="form-group">
                    <label for="register-password">Пароль</label>
                    <input type="password" id="register-password" placeholder="Придумайте пароль">
                </div>
                <div class="form-group">
                    <label for="register-email">Email</label>
                    <input type="email" id="register-email" placeholder="Введите ваш email">
                </div>
                <button id="register-btn" class="btn">Зарегистрироваться</button>
            </div>
        </div>
        
        <div id="game-section" class="game-section hidden">
            <h2>Выберите игру</h2>
            
            <div class="game-grid">
                <div class="game-card" data-game="dice">
                    <div class="game-icon">🎲</div>
                    <div class="game-title">Игра в кости</div>
                    <div class="game-desc">Бросьте кости против компьютера. Большая сумма побеждает!</div>
                    <button class="btn">Играть</button>
                </div>
                
                <div class="game-card" data-game="slots">
                    <div class="game-icon">🎰</div>
                    <div class="game-title">Игровой автомат</div>
                    <div class="game-desc">Соберите три одинаковых символа для выигрыша!</div>
                    <button class="btn">Играть</button>
                </div>
                
                <div class="game-card" data-game="stats">
                    <div class="game-icon">📊</div>
                    <div class="game-title">Статистика</div>
                    <div class="game-desc">Просмотр вашей игровой статистики и истории</div>
                    <button class="btn">Открыть</button>
                </div>
            </div>
            
            <div id="dice-game" class="game-area hidden">
                <h2>🎲 Игра в кости</h2>
                <p>Бросьте кости против компьютера. У кого сумма больше, тот побеждает!</p>
                
                <div class="bet-controls">
                    <button class="bet-btn" id="decrease-bet">-</button>
                    <div class="bet-amount" id="current-bet">10</div>
                    <button class="bet-btn" id="increase-bet">+</button>
                </div>
                
                <div class="dice-container">
                    <div class="dice" id="player-dice1">?</div>
                    <div class="dice" id="player-dice2">?</div>
                </div>
                <p>Ваши кости</p>
                
                <div class="dice-container">
                    <div class="dice" id="computer-dice1">?</div>
                    <div class="dice" id="computer-dice2">?</div>
                </div>
                <p>Кости компьютера</p>
                
                <div class="result" id="dice-result"></div>
                
                <button id="roll-dice" class="btn">Бросить кости</button>
                <button id="back-from-dice" class="btn btn-secondary">Назад</button>
            </div>
            
            <div id="slots-game" class="game-area hidden">
                <h2>🎰 Игровой автомат</h2>
                <p>Соберите три одинаковых символа для выигрыша!</p>
                
                <div class="bet-controls">
                    <button class="bet-btn" id="decrease-slot-bet">-</button>
                    <div class="bet-amount" id="current-slot-bet">5</div>
                    <button class="bet-btn" id="increase-slot-bet">+</button>
                </div>
                
                <div class="slot-container">
                    <div class="slot" id="slot1">🍒</div>
                    <div class="slot" id="slot2">🍋</div>
                    <div class="slot" id="slot3">🍊</div>
                </div>
                
                <div class="result" id="slots-result"></div>
                
                <button id="spin-slots" class="btn">Крутить</button>
                <button id="back-from-slots" class="btn btn-secondary">Назад</button>
            </div>
            
            <div id="stats-game" class="game-area hidden">
                <h2>📊 Статистика</h2>
                
                <div class="stats">
                    <div class="stat-card">
                        <div>Всего игр</div>
                        <div class="stat-value" id="total-games">0</div>
                    </div>
                    <div class="stat-card">
                        <div>Побед</div>
                        <div class="stat-value" id="wins">0</div>
                    </div>
                    <div class="stat-card">
                        <div>Поражений</div>
                        <div class="stat-value" id="losses">0</div>
                    </div>
                    <div class="stat-card">
                        <div>Выигрыш</div>
                        <div class="stat-value" id="total-win">0</div> ₣
                    </div>
                </div>
                
                <h3>История игр</h3>
                <div class="history-list" id="game-history">
                    <!-- История будет заполнена динамически -->
                </div>
                
                <button id="back-from-stats" class="btn btn-secondary">Назад</button>
            </div>
        </div>
    </div>

    <script>
        // Система аккаунтов
        const users = JSON.parse(localStorage.getItem('focoinUsers')) || {};
        let currentUser = JSON.parse(localStorage.getItem('focoinCurrentUser')) || null;
        
        // DOM элементы
        const authSection = document.getElementById('auth-section');
        const gameSection = document.getElementById('game-section');
        const loginForm = document.getElementById('login-form');
        const registerForm = document.getElementById('register-form');
        const loginTab = document.getElementById('login-tab');
        const registerTab = document.getElementById('register-tab');
        const loginBtn = document.getElementById('login-btn');
        const registerBtn = document.getElementById('register-btn');
        const logoutBtn = document.getElementById('logout-btn');
        const usernameDisplay = document.getElementById('username-display');
        const balanceDisplay = document.getElementById('balance');
        
        // Инициализация при загрузке
        document.addEventListener('DOMContentLoaded', () => {
            updateUI();
            
            // Обработчики вкладок авторизации
            loginTab.addEventListener('click', () => {
                loginTab.classList.add('active');
                registerTab.classList.remove('active');
                loginForm.classList.remove('hidden');
                registerForm.classList.add('hidden');
            });
            
            registerTab.addEventListener('click', () => {
                registerTab.classList.add('active');
                loginTab.classList.remove('active');
                registerForm.classList.remove('hidden');
                loginForm.classList.add('hidden');
            });
            
            // Обработчики кнопок авторизации
            loginBtn.addEventListener('click', handleLogin);
            registerBtn.addEventListener('click', handleRegister);
            logoutBtn.addEventListener('click', handleLogout);
            
            // Инициализация игр
            initGames();
        });
        
        // Обновление интерфейса в зависимости от состояния авторизации
        function updateUI() {
            if (currentUser) {
                authSection.classList.add('hidden');
                gameSection.classList.remove('hidden');
                logoutBtn.classList.remove('hidden');
                usernameDisplay.textContent = currentUser.username;
                balanceDisplay.textContent = currentUser.balance;
            } else {
                authSection.classList.remove('hidden');
                gameSection.classList.add('hidden');
                logoutBtn.classList.add('hidden');
                usernameDisplay.textContent = 'Гость';
                balanceDisplay.textContent = '0';
            }
        }
        
        // Обработка входа
        function handleLogin() {
            const username = document.getElementById('login-username').value;
            const password = document.getElementById('login-password').value;
            
            if (!username || !password) {
                alert('Пожалуйста, заполните все поля');
                return;
            }
            
            if (users[username] && users[username].password === password) {
                currentUser = users[username];
                localStorage.setItem('focoinCurrentUser', JSON.stringify(currentUser));
                updateUI();
            } else {
                alert('Неверное имя пользователя или пароль');
            }
        }
        
        // Обработка регистрации
        function handleRegister() {
            const username = document.getElementById('register-username').value;
            const password = document.getElementById('register-password').value;
            const email = document.getElementById('register-email').value;
            
            if (!username || !password || !email) {
                alert('Пожалуйста, заполните все поля');
                return;
            }
            
            if (users[username]) {
                alert('Пользователь с таким именем уже существует');
                return;
            }
            
            // Создание нового пользователя
            users[username] = {
                username,
                password,
                email,
                balance: 1000, // Начальный баланс
                stats: {
                    totalGames: 0,
                    wins: 0,
                    losses: 0,
                    totalWin: 0
                },
                gameHistory: []
            };
            
            localStorage.setItem('focoinUsers', JSON.stringify(users));
            alert('Регистрация успешна! Теперь вы можете войти в систему.');
            
            // Переключение на вкладку входа
            loginTab.click();
            
            // Очистка полей
            document.getElementById('register-username').value = '';
            document.getElementById('register-password').val
