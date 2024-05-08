<!DOCTYPE html>
<html lang="PT-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ChatInter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #000000;
        }
        .chat-container {
            width: 300px;
            margin: 50px auto;
            background-color: #fff;
            border: 1px solid #ccc;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        #chat-messages {
            height: 200px;
            overflow-y: auto;
            border-bottom: 1px solid #ccc;
            margin-bottom: 10px;
        }
        #user-input {
            width: calc(100% - 40px);
            padding: 5px;
            margin-right: 5px;
        }
        #send-button {
            padding: 5px 10px;
            background-color: #ff0000;
            color: #fff;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
        #send-button:hover{
            color: aqua;
            background-color: #000000;
        }
    </style>
</head>
<body>

<div class="chat-container">
    <div id="chat-messages"></div>
    <input type="text" id="user-input" placeholder="Digite sua mensagem...">
    <button id="send-button">Enviar</button>
</div>

<script>
    function addMessage(message, sender) {
        var chatMessages = document.getElementById('chat-messages');
        var messageElement = document.createElement('div');
        messageElement.textContent = sender + ': ' + message;
        chatMessages.appendChild(messageElement);
        chatMessages.scrollTop = chatMessages.scrollHeight;
    }

    function responder(mensagem) {
        switch (mensagem.toLowerCase()) {
            case 'olá':
                addMessage("Olá! Bem-vindo ao nosso restaurante. Como posso ajudar?", "Bot");
                break;
            case 'que tipo de comidas vocês servem ?':
                addMessage("Nós servimos uma variedade de pratos, incluindo pizzas, massas, saladas e sobremesas. Qual é o seu favorito?", "Bot");
                break;
            case 'vocês aceitam cartão de crédito?':
                addMessage("Sim, aceitamos os seguintes cartões de crédito:", "Bot");
                addMessage("1. Visa", "Bot");
                addMessage("2. Mastercard", "Bot");
                addMessage("3. American Express", "Bot");
                addMessage("Por favor, selecione o cartão desejado .", "Bot");
                break;
            case 'qual é o prato do dia?':
                addMessage("Hoje, nosso prato do dia é um delicioso risoto de cogumelos frescos. Você gostaria de experimentar?", "Bot");
                break;
            case 'qual é o horário de funcionamento?':
                addMessage("Estamos abertos todos os dias, das 11h às 22h. Venha nos visitar quando quiser!", "Bot");
                break;
            case 'qual é o prato mais popular do menu?':
                addMessage("Nosso prato mais popular é a nossa pizza especial da casa, com uma combinação única de ingredientes frescos e molho caseiro. É uma explosão de sabor! Você gostaria de experimentar?", "Bot");
                break;
            case 'vocês oferecem opções vegetarianas ou veganas?':
                addMessage("Sim, temos uma variedade de opções vegetarianas e veganas em nosso menu, incluindo pizzas, massas e saladas. Você tem alguma preferência?", "Bot");
                break;
            case 'posso fazer um pedido para viagem?':
                addMessage("Claro! Aceitamos pedidos para viagem. Você pode ligar para nós ou fazer o pedido através do nosso aplicativo móvel. Como podemos ajudá-lo?", "Bot");
                break;
            case 'quanto tempo leva para entregar um pedido?':
                addMessage("O tempo de entrega pode variar dependendo da sua localização e da demanda atual. Normalmente, levamos de 30 a 45 minutos para entregar. Você gostaria de fazer um pedido agora?", "Bot");
                break;
            case 'vocês têm opções de pagamento online?':
                addMessage("Sim, oferecemos opções de pagamento online através do nosso aplicativo móvel ou do nosso site. Aceitamos todos os principais cartões de crédito e também oferecemos pagamento via carteiras digitais. É conveniente e seguro!", "Bot");
                break;
            case 'vocês oferecem opções de entrega gratuita?':
                addMessage("Sim, oferecemos entrega gratuita para pedidos acima de R$50 dentro de um raio de 5 km do nosso restaurante. É uma ótima maneira de aproveitar nossos pratos no conforto da sua casa. Posso ajudar com um pedido?", "Bot");
                break;
            case 'vocês têm promoções especiais para grupos?':
                addMessage("Sim, temos pacotes especiais para grupos que incluem descontos em grandes pedidos. Se você está planejando uma festa ou um evento, entre em contato conosco para mais detalhes sobre nossas ofertas para grupos.", "Bot");
                break;
            case 'posso fazer alterações nos pratos do menu?':
                addMessage("Certamente! Estamos felizes em fazer ajustes nos pratos do nosso menu para atender às suas preferências dietéticas ou restrições alimentares. Basta nos informar sobre as suas necessidades ao fazer o pedido.", "Bot");
                break;
            case 'vocês oferecem opções de catering para eventos?':
                addMessage("Sim, oferecemos serviços de catering para eventos de todos os tamanhos. Desde pequenas reuniões até grandes eventos corporativos, estamos preparados para fornecer uma deliciosa experiência gastronômica para seus convidados. Como podemos ajudar com o seu evento?", "Bot");
                break;
            case 'quais são as opções de sobremesa disponíveis?':
                addMessage("Temos uma variedade de deliciosas sobremesas para satisfazer sua vontade de doces. De cheesecakes a tiramisus, temos algo para todos os gostos. Qual sobremesa você gostaria de adicionar ao seu pedido hoje?", "Bot");
                break;
            default:
                addMessage("Desculpe, não entendi. Pode repetir ou fazer outra pergunta relacionada à comida ou forma de pagamento?", "Bot");
        }
    }

    document.getElementById('send-button').addEventListener('click', function () {
        var userInput = document.getElementById('user-input').value;
        if (userInput.trim() !== '') {
            addMessage(userInput, "Usuário");
            responder(userInput);
            document.getElementById('user-input').value = '';
        }
    });

    document.getElementById('user-input').addEventListener('keypress', function (event) {
        if (event.key === 'Enter') {
            document.getElementById('send-button').click();
        }
    });
</script>

</body>
</html>
