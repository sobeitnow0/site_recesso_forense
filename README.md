<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contagem Regressiva para o Recesso Forense 2025</title>
    <style>
        body {
            font-family: sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
            text-align: center;
            flex-direction: column;
        }
        h1 {
            font-size: 2em;
            margin-bottom: 20px;
        }
        #countdown {
            font-size: 3em;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>CONTAGEM REGRESSIVA PARA O RECESSO FORENSE/JUDICIAL 2025</h1>
    <div id="countdown"></div>

    <script>
        // Define a data final da contagem regressiva
        const countDownDate = new Date("Dec 20, 2025 00:00:00").getTime();

        // Atualiza a contagem a cada 1 segundo
        const x = setInterval(function() {

            // Pega a data e hora de hoje
            const now = new Date().getTime();

            // Encontra a distância entre agora e a data final
            const distance = countDownDate - now;

            // Cálculos de tempo para dias, horas, minutos e segundos
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            // Exibe o resultado no elemento com id="countdown"
            document.getElementById("countdown").innerHTML = days + "d " + hours + "h "
            + minutes + "m " + seconds + "s ";

            // Se a contagem regressiva terminar, exibe uma mensagem
            if (distance < 0) {
                clearInterval(x);
                document.getElementById("countdown").innerHTML = "O recesso começou!";
            }
        }, 1000);
    </script>
</body>
</html>
