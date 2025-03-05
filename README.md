# Kauaha-one
Só testando 

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cartoon World</title>
    <link href="https://fonts.googleapis.com/css2?family=Comic+Neue:wght@700&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(120deg, #87CEEB, #E0F6FF);
            font-family: 'Comic Neue', cursive;
            min-height: 100vh;
        }

        .header {
            text-align: center;
            padding: 20px;
            background-color: #FFD700;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .cartoon-container {
            display: flex;
            justify-content: space-around;
            padding: 50px;
            flex-wrap: wrap;
        }

        .character {
            width: 200px;
            height: 300px;
            position: relative;
            animation: float 3s ease-in-out infinite;
        }

        .cat {
            background: url('https://i.imgur.com/mXJjz8C.png');
            background-size: contain;
            background-repeat: no-repeat;
        }

        .dog {
            background: url('https://i.imgur.com/LfYvT3Q.png');
            background-size: contain;
            background-repeat: no-repeat;
        }

        .speech-bubble {
            position: absolute;
            background: white;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            width: 160px;
            text-align: center;
            top: -80px;
            left: 50%;
            transform: translateX(-50%);
        }

        .speech-bubble::after {
            content: '';
            position: absolute;
            width: 0;
            height: 0;
            border-left: 20px solid transparent;
            border-right: 20px solid transparent;
            border-top: 30px solid white;
            bottom: -30px;
            left: 50%;
            transform: translateX(-50%);
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }

        .content {
            max-width: 800px;
            margin: 40px auto;
            padding: 20px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 8px 16px rgba(0,0,0,0.1);
        }

        .cloud {
            position: absolute;
            width: 100px;
            height: 40px;
            background: white;
            border-radius: 20px;
            animation: moveCloud 20s linear infinite;
        }

        @keyframes moveCloud {
            from { left: -100px; }
            to { left: 100%; }
        }

        @media (max-width: 768px) {
            .cartoon-container {
                flex-direction: column;
                align-items: center;
            }
            .character {
                margin: 20px 0;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Welcome to Cartoon World! 🌈</h1>
    </header>

    <div class="cartoon-container">
        <div class="character cat">
            <div class="speech-bubble">Hello! 😺</div>
        </div>
        
        <div class="character dog">
            <div class="speech-bubble">Hi there! 🐶</div>
        </div>
    </div>

    <div class="content">
        <h2>About This Project</h2>
        <p>✨ Bem-vindo ao nosso mundo animado! ✨</p>
        <p>Este é um projeto de página web temática de desenho animado, perfeito para:</p>
        <ul>
            <li>Portfólios criativos</li>
            <li>Projetos de animação</li>
            <li>Sites infantis</li>
            <li>Projetos escolares</li>
        </ul>
    </div>

    <script>
        // Adiciona nuvens dinamicamente
        function createClouds() {
            const body = document.querySelector('body');
            for(let i = 0; i < 5; i++) {
                const cloud = document.createElement('div');
                cloud.className = 'cloud';
                cloud.style.top = `${Math.random() * 50 + 10}%`;
                cloud.style.animationDelay = `${Math.random() * 20}s`;
                body.appendChild(cloud);
            }
        }
        
        window.onload = createClouds;
    </script>
</body>
</html>