<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contagem Regressiva para o Recesso Forense 2025</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        /* Estilo customizado para usar a fonte Inter */
        body {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="bg-gray-900 text-white flex flex-col items-center justify-center min-h-screen p-4">

    <!-- Container Principal -->
    <div class="text-center w-full max-w-4xl mx-auto">
        <!-- Título -->
        <h1 class="text-3xl md:text-5xl font-bold text-cyan-400 uppercase tracking-wider mb-8">
            Contagem Regressiva para o Recesso Forense 2025
        </h1>

        <!-- Container da Contagem Regressiva -->
        <div id="countdown-container" class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-8">
            <!-- Dias -->
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg">
                <div id="days" class="text-5xl md:text-7xl font-black text-white">00</div>
                <div class="text-sm text-gray-400 uppercase mt-2">Dias</div>
            </div>
            <!-- Horas -->
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg">
                <div id="hours" class="text-5xl md:text-7xl font-black text-white">00</div>
                <div class="text-sm text-gray-400 uppercase mt-2">Horas</div>
            </div>
            <!-- Minutos -->
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg">
                <div id="minutes" class="text-5xl md:text-7xl font-black text-white">00</div>
                <div class="text-sm text-gray-400 uppercase mt-2">Minutos</div>
            </div>
            <!-- Segundos -->
            <div class="bg-gray-800 p-6 rounded-lg shadow-lg">
                <div id="seconds" class="text-5xl md:text-7xl font-black text-white">00</div>
                <div class="text-sm text-gray-400 uppercase mt-2">Segundos</div>
            </div>
        </div>
        
        <!-- Mensagem de Fim -->
        <div id="end-message" class="hidden mt-12">
            <h2 class="text-4xl md:text-6xl font-bold text-green-400">O recesso começou!</h2>
            <p class="text-gray-300 mt-2">Boas festas e bom descanso!</p>
        </div>
    </div>

    <script>
        // Define a data final da contagem regressiva
        const countDownDate = new Date("Dec 20, 2025 00:00:00").getTime();

        // Seleciona os elementos do DOM
        const daysEl = document.getElementById('days');
        const hoursEl = document.getElementById('hours');
        const minutesEl = document.getElementById('minutes');
        const secondsEl = document.getElementById('seconds');
        const countdownContainer = document.getElementById('countdown-container');
        const endMessage = document.getElementById('end-message');

        // Função para adicionar um zero à esquerda se o número for menor que 10
        function formatTime(time) {
            return time < 10 ? `0${time}` : time;
        }

        // Atualiza a contagem a cada 1 segundo
        const countdownInterval = setInterval(() => {
            const now = new Date().getTime();
            const distance = countDownDate - now;

            // Se a contagem terminou
            if (distance < 0) {
                clearInterval(countdownInterval);
                countdownContainer.classList.add('hidden'); // Esconde a contagem
                endMessage.classList.remove('hidden'); // Mostra a mensagem final
                return;
            }

            // Cálculos de tempo
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            // Atualiza o HTML com os valores formatados
            daysEl.innerHTML = formatTime(days);
            hoursEl.innerHTML = formatTime(hours);
            minutesEl.innerHTML = formatTime(minutes);
            secondsEl.innerHTML = formatTime(seconds);

        }, 1000);
    </script>
</body>
</html>
