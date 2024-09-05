<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aventura Interativa</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            text-align: center;
            padding: 50px;
        }
        .content {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 80%;
            margin: auto;
        }
        .choices {
            margin-top: 20px;
        }
        .choice-btn {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
        }
        .choice-btn:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="content">
        <h1>Aventura Interativa</h1>
        <p id="story">Você acorda em uma floresta misteriosa, sem saber como chegou até aqui. À sua frente, você vê dois caminhos: um leva a uma caverna escura e o outro segue em direção a uma aldeia distante. O que você faz?</p>
        
        <div class="choices">
            <button class="choice-btn" onclick="choosePath('caverna')">Ir para a caverna</button>
            <button class="choice-btn" onclick="choosePath('aldeia')">Seguir para a aldeia</button>
        </div>
    </div>

    <script>
        function choosePath(choice) {
            if (choice === 'caverna') {
                document.getElementById('story').innerHTML = "Você entra na caverna e logo percebe que há um urso gigante dormindo no fundo. Você pode tentar sair sem fazer barulho ou pegar uma espada velha no chão. O que você faz?";
                document.querySelector('.choices').innerHTML = `
                    <button class="choice-btn" onclick="choosePath('fugir')">Sair sem fazer barulho</button>
                    <button class="choice-btn" onclick="choosePath('espada')">Pegar a espada</button>
                `;
            } else if (choice === 'aldeia') {
                document.getElementById('story').innerHTML = "Você segue em direção à aldeia e percebe que os moradores estão sendo atacados por bandidos. Você pode ajudar os aldeões a lutar ou se esconder até que os bandidos se vão. O que você faz?";
                document.querySelector('.choices').innerHTML = `
                    <button class="choice-btn" onclick="choosePath('lutar')">Ajudar os aldeões</button>
                    <button class="choice-btn" onclick="choosePath('esconder')">Se esconder</button>
                `;
            } else if (choice === 'fugir') {
                document.getElementById('story').innerHTML = "Você tenta sair silenciosamente, mas acaba tropeçando em uma pedra. O urso acorda e te vê. Infelizmente, você não consegue escapar. Fim de jogo!";
                document.querySelector('.choices').innerHTML = `
                    <button class="choice-btn" onclick="restart()">Recomeçar</button>
                `;
            } else if (choice === 'espada') {
                document.getElementById('story').innerHTML = "Você pega a espada e, de forma corajosa, ataca o urso. Após uma batalha intensa, você sai vitorioso! Você continua sua jornada. Fim!";
                document.querySelector('.choices').innerHTML = `
                    <button class="choice-btn" onclick="restart()">Recomeçar</button>
                `;
            } else if (choice === 'lutar') {
                document.getElementById('story').innerHTML = "Você ajuda os aldeões a lutar e, juntos, conseguem expulsar os bandidos. A aldeia está a salvo graças a você! Fim!";
                document.querySelector('.choices').innerHTML = `
                    <button class="choice-btn" onclick="restart()">Recomeçar</button>
                `;
            } else if (choice === 'esconder') {
                document.getElementById('story').innerHTML = "Você se esconde atrás de uma árvore e espera até que os bandidos vão embora. A aldeia foi destruída, mas você está a salvo. Fim!";
                document.querySelector('.choices').innerHTML = `
                    <button class="choice-btn" onclick="restart()">Recomeçar</button>
                `;
            }
        }

        function restart() {
            document.getElementById('story').innerHTML = "Você acorda em uma floresta misteriosa, sem saber como chegou até aqui. À sua frente, você vê dois caminhos: um leva a uma caverna escura e o outro segue em direção a uma aldeia distante. O que você faz?";
            document.querySelector('.choices').innerHTML = `
                <button class="choice-btn" onclick="choosePath('caverna')">Ir para a caverna</button>
                <button class="choice-btn" onclick="choosePath('aldeia')">Seguir para a aldeia</button>
            `;
        }
    </script>
</body>
</html>
