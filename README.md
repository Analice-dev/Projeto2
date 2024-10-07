# Projeto2<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cidade Perdida</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="app">
        <div id="passo-0" class="passo ativo">
            <p>Um dia desses, dentro de um livro da biblioteca da escola, eu descobri uma carta antiga sobre uma cidade perdida, escondida por riquezas e belezas naturais. Nessa carta, a autora deixa algumas pistas para encontrar essa cidade e eu decidi segui-las!</p>
            <button onclick="mudarPasso(1)">Rio de Janeiro</button>
            <button onclick="mudarPasso(2)">Pernambuco</button>
        </div>

        <div id="passo-1" class="passo">
            <p>Você começa sua jornada no Rio de Janeiro, subindo o Pico da Tijuca ao amanhecer para encontrar a primeira pista.</p>
            <button onclick="mudarPasso(3)">Procurar a pista no topo do pico</button>
            <button onclick="mudarPasso(0)">Desistir e voltar para casa</button>
        </div>

        <div id="passo-2" class="passo">
            <p>Você começa sua jornada em Pernambuco, explorando a cultura e as belezas naturais, mas precisa tomar uma decisão.</p>
            <button onclick="mudarPasso(0)">Voltar ao início</button>
        </div>

        <div id="passo-3" class="passo">
            <p>Você encontra a pista no topo do Pico da Tijuca! A jornada continua...</p>
            <button onclick="mudarPasso(0)">Recomeçar</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    padding: 20px;
}

#app {
    max-width: 600px;
    margin: 0 auto;
    background-color: #fff;
    padding: 20px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

.passo {
    display: none;
}

.passo.ativo {
    display: block;
}

button {
    padding: 10px;
    margin: 10px;
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
function mudarPasso(passo) {
    // Ocultar todos os passos
    let passos = document.querySelectorAll('.passo');
    passos.forEach(function(p) {
        p.classList.remove('ativo');
    });

    // Mostrar o passo correspondente
    let passoAtivo = document.getElementById('passo-' + passo);
    passoAtivo.classList.add('ativo');
}

// Inicialmente, o "passo-0" será exibido
document.addEventListener('DOMContentLoaded', function() {
    mudarPasso(0);
});
const avanca = document.querySelectorAll('.btn-proximo');

avanca.forEach(button => {
    button.addEventListener('click', function(){
        // Obtém o elemento atual com a classe "ativo"
        const atual = document.querySelector('.ativo');
        
        // Pega o próximo elemento a partir do atual
        const proximo = atual.nextElementSibling;

        // Verifica se existe um próximo elemento
        if (proximo && proximo.classList.contains('passo')) {
            // Remove a classe "ativo" do elemento atual
            atual.classList.remove('ativo');
            
            // Adiciona a classe "ativo" ao próximo elemento
            proximo.classList.add('ativo');
        }
    });
});
<div id="passo-0" class="passo ativo">
    <p>Um dia desses, dentro de um livro da biblioteca da escola, eu descobri uma carta antiga sobre uma cidade perdida, escondida por riquezas e belezas naturais...</p>
    <button class="btn-proximo">Rio de Janeiro</button>
    <button class="btn-proximo">Pernambuco</button>
</div>

<div id="passo-1" class="passo">
    <p>Você começa sua jornada no Rio de Janeiro...</p>
    <button class="btn-proximo">Procurar a pista no topo do pico</button>
    <button class="btn-proximo">Desistir e voltar para casa</button>
</div>

<!-- Continue com os outros passos -->
/* Estilização básica */
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    padding: 20px;
}

#app {
    max-width: 600px;
    margin: 0 auto;
    background-color: #fff;
    padding: 20px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

/* Oculta todas as divs de passos por padrão */
.passo {
    display: none;
}

/* Mostra apenas a div que tem a classe "ativo" */
.passo.ativo {
    display: block;
}

/* Estilo dos botões */
button {
    padding: 10px;
    margin: 10px;
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
