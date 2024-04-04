- 👋 Hi, I’m @bastosdu
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
bastosdu/bastosdu is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Te amo</title>
<style>
    body {
        background-color: #ffc0cb; /* Fundo rosa */
        margin: 0;
        padding: 0;
        overflow: hidden; /* Evita a rolagem da página */
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }
    .container {
        text-align: center;
    }
    #gatinho {
        width: 200px;
        height: 200px;
        position: relative;
        animation: danca 2s infinite;
    }
    @keyframes danca {
        0% { transform: rotate(0deg); }
        25% { transform: rotate(10deg); }
        50% { transform: rotate(0deg); }
        75% { transform: rotate(-10deg); }
        100% { transform: rotate(0deg); }
    }
    #botao {
        padding: 10px 20px;
        font-size: 16px;
        background-color: #3498db;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        animation: piscar 1s infinite;
    }
    @keyframes piscar {
        0% { opacity: 1; }
        50% { opacity: 0; }
        100% { opacity: 1; }
    }
    .coracao {
        color: #e25555; /* Cor do coração */
        position: absolute;
        animation: flutuar 5s infinite linear;
    }
    @keyframes flutuar {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(-20px); }
    }
    .mensagem-te-amo {
        font-family: 'Pacifico', cursive; /* Fonte personalizada */
        font-size: 24px; /* Ajuste o tamanho da fonte */
        color: red;
        margin-left: 20px; /* Espaço à esquerda para separar da imagem */
    }
    @keyframes fogos {
        0% { transform: translateY(0) rotate(0deg); opacity: 1; }
        100% { transform: translateY(-1000px) rotate(360deg); opacity: 0; }
    }
    .fogo {
        position: absolute;
        width: 4px;
        height: 20px;
        background-color: yellow;
        border-radius: 50%;
        animation: fogos 2s ease-out;
    }
</style>
<!-- Link para a fonte personalizada -->
<link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">
</head>
<body>
<div class="container">
    <img id="gatinho" src="https://media.giphy.com/media/SRO0ZwmImic0/giphy.gif" alt="Gatinho Dançando">
    <h1 class="mensagem-te-amo">Te amo</h1>
    <br>
    <button id="botao" onclick="alternarDanca(); soltarFogos()">Clique em mim</button>
</div>

<!-- Corações -->
<div class="coracao" style="top: 20%; left: 10%; font-size: 24px;">&#10084;</div>
<div class="coracao" style="top: 30%; left: 40%; font-size: 36px;">&#10084;</div>
<div class="coracao" style="top: 40%; left: 70%; font-size: 20px;">&#10084;</div>
<div class="coracao" style="top: 60%; left: 20%; font-size: 30px;">&#10084;</div>
<div class="coracao" style="top: 70%; left: 50%; font-size: 28px;">&#10084;</div>
<div class="coracao" style="top: 80%; left: 80%; font-size: 32px;">&#10084;</div>

<script>
    var dancaAtiva = true; // Variável para controlar se a dança está ativa ou não

    function alternarDanca() {
        var gatinho = document.getElementById('gatinho');
        if (dancaAtiva) {
            gatinho.style.animation = 'none'; // Define a animação do gatinho como 'none', que a faz parar
        } else {
            gatinho.style.animation = 'danca 2s infinite'; // Define a animação do gatinho de volta
        }
        dancaAtiva = !dancaAtiva; // Inverte o estado da dança
    }

    function soltarFogos() {
        for (let i = 0; i < 20; i++) {
            setTimeout(function() {
                criarFogo();
            }, i * 100);
        }
    }

    function criarFogo() {
        var fogo = document.createElement('div');
        fogo.classList.add('fogo');
        var posX = Math.random() * window.innerWidth;
        var posY = Math.random() * window.innerHeight;
        fogo.style.left = posX + 'px';
        fogo.style.top = posY + 'px';
        document.body.appendChild(fogo);
        setTimeout(function() {
            fogo.remove();
        }, 2000);
    }

    // Função para criar corações
    function criarCoracoes() {
        for (let i = 0; i < 10; i++) {
            var coracao = document.createElement('div');
            coracao.innerHTML = '&#10084;';
            coracao.classList.add('coracao');
            var posX = Math.random() * window.innerWidth;
            var posY = Math.random() * window.innerHeight;
            coracao.style.left = posX + 'px';
            coracao.style.top = posY + 'px';
            document.body.appendChild(coracao);
        }
    }

    criarCoracoes(); // Chama a função ao carregar a página
</script>
</body>
</html>
