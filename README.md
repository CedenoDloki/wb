<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Me perdonas?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f2f2f2;
            margin: 0;
            padding: 0;
        }
        h1 {
            margin-top: 20vh;
            color: #333;
        }
        .message {
            font-size: 18px;
            margin: 20px 0;
            color: #555;
        }
        .buttons {
            margin-top: 20px;
        }
        .button {
            display: inline-block;
            padding: 10px 20px;
            margin: 10px;
            font-size: 16px;
            color: #fff;
            background-color: #007BFF;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            text-decoration: none;
        }
        .button:hover {
            background-color: #0056b3;
        }
        .button.no {
            position: absolute;
        }
    </style>
</head>
<body>
    <h1>¿Me perdonas por irme del gym?</h1>
    <div class="message"></div>
    <div class="buttons">
        <button class="button yes">Sí</button>
        <button class="button no">No</button>
    </div>

    <script>
        const messages = [
            "Por favor, no seas tan duro conmigo.",
            "¡Prometo mejorar!",
            "Eres muy importante para mí.",
            "No puedo imaginar mi vida sin tu perdón.",
            "¡Haré lo que sea necesario para compensarte!",
            "Solo necesito una oportunidad más.",
            "Sé que cometí un error, pero estoy dispuesto a aprender de él.",
            "Lo siento mucho, de verdad no fue mi intención.",
            "Reconozco que me equivoqué, y quiero arreglar las cosas.",
            "Perdón por lo sucedido, quiero hacerlo mejor la próxima vez.",
            "Entiendo que estés molesto/a, pero espero que me des otra oportunidad.",
            "No siempre tomo las mejores decisiones, pero estoy trabajando en eso.",
            "Lamento haber causado molestias. Intentaré ser más cuidadoso/a.",
            "Por favor, permíteme demostrar que puedo hacerlo mejor.",
            "Sé que fallé, pero estoy comprometido/a a mejorar.",
            "No esperaba que esto te afectara así. Perdóname, por favor."
        ];

        document.addEventListener('DOMContentLoaded', () => {
            const noButton = document.querySelector('.button.no');
            const yesButton = document.querySelector('.button.yes');
            const messageElement = document.querySelector('.message');
            const buttonsContainer = document.querySelector('.buttons');
            const h1Element = document.querySelector('h1');
            
            let messageIndex = 0;

            // Guardamos la posición original del botón "No"
            let initialPosition = { top: noButton.offsetTop, left: noButton.offsetLeft };

            // Evento cuando el usuario hace clic en "Sí"
            yesButton.addEventListener('click', () => {
                buttonsContainer.style.display = 'none';
                h1Element.style.display = 'none';
                
                messageElement.textContent = "¡Gracias por tu perdón, lo contaré todooooooooooooo! 🥰 Algún día voy a tener tus brazotes";

                messageElement.style.fontSize = '24px';
                
                yesButton.style.display = 'none';
            });

            // Evento para mover el botón "No"
            noButton.addEventListener('mouseover', () => {
                noButton.style.top = Math.random() * (window.innerHeight - 50) + "px";
                noButton.style.left = Math.random() * (window.innerWidth - 100) + "px";
            });

            // Evento cuando se hace clic en "No"
            noButton.addEventListener('click', () => {
                if (messageIndex < messages.length) {
                    messageElement.textContent = messages[messageIndex];
                    messageIndex++;
                } else {
                    messageElement.textContent = "¡Gracias por intentar escucharme!";
                }
            });
        });
    </script>
</body>
</html>
