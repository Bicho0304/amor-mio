# Amor-de-mi-vida
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rompecabezas de Amor</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #fbe3e8;
            position: relative;
        }
        #carta-animada {
            width: 150px;
            height: 150px;
            background-image: url('carta-animada.gif');
            background-size: cover;
            margin: 20px auto;
        }
        #mensaje {
            font-size: 20px;
            background-color: #ff6b81;
            color: white;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
            display: inline-block;
            margin-top: 20px;
        }
        #puzzle-container {
            display: grid;
            grid-template-columns: repeat(3, 100px);
            grid-gap: 5px;
            width: 315px;
            margin: 20px auto;
            display: none;
        }
        .puzzle-piece {
            width: 100px;
            height: 100px;
            background-size: 300px 300px;
            opacity: 0;
            transition: opacity 0.8s ease-in-out, transform 0.8s ease-in-out;
            transform: scale(0);
        }
        #mensaje-final {
            font-size: 24px;
            font-weight: bold;
            color: #d10060;
            margin-top: 20px;
            display: none;
            opacity: 0;
            transition: opacity 2s ease-in-out;
        }
        .gif-romantico {
            width: 100px;
            height: 100px;
            position: absolute;
            display: none;
        }
    </style>
</head>
<body>
    <div id="carta-animada"></div>
    <div id="mensaje" onclick="iniciarRompecabezas()">Te llegó una carta, ábrela</div>
    <div id="puzzle-container">
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 50% 10%; border-radius: 50% 50% 0 0;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 20% 30%; border-radius: 50% 50% 0 0;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 80% 30%; border-radius: 50% 50% 0 0;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 30% 50%; border-radius: 0 0 50% 50%;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 70% 50%; border-radius: 0 0 50% 50%;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 50% 80%; border-radius: 0 0 50% 50%;"></div>
    </div>
    <div id="mensaje-final">Gracias por llegar a mi vida<br>
    y<br>
    ser lo mejor que me ha pasado,<br>
    tu alumbras cada uno de mis dias<br>
    con tu sonrisa y tus ocurrencias,<br>
    no puedo dejar de pensar en ti<br>
    la chica mas increible del mundo,<br>
    eres mi reina hermosa<br>
    la mujer y la niña de mis ojos<br>
    <br>
    TE AMO DE AQUI A LA LUNA<br>
    A PASITOS DE TORTUGA</div>
    <img src="corazon1.gif" class="gif-romantico" style="top: 10%; left: 10%;">
    <img src="corazon2.gif" class="gif-romantico" style="top: 10%; right: 10%;">
    <img src="corazon3.gif" class="gif-romantico" style="bottom: 10%; left: 10%;">
    <img src="corazon4.gif" class="gif-romantico" style="bottom: 10%; right: 10%;">
    
    <script>
        function iniciarRompecabezas() {
            document.getElementById("carta-animada").style.display = "none";
            document.getElementById("mensaje").style.display = "none";
            document.getElementById("puzzle-container").style.display = "grid";
            let piezas = document.querySelectorAll(".puzzle-piece");
            
            piezas.forEach((pieza, index) => {
                setTimeout(() => {
                    pieza.style.opacity = "1";
                    pieza.style.transform = "scale(1)";
                }, index * 700);
            });
            
            setTimeout(() => {
                let mensajeFinal = document.getElementById("mensaje-final");
                mensajeFinal.style.display = "block";
                setTimeout(() => {
                    mensajeFinal.style.opacity = "1";
                }, 500);
                
                let gifs = document.querySelectorAll(".gif-romantico");
                gifs.forEach((gif, index) => {
                    setTimeout(() => {
                        gif.style.display = "block";
                    }, index * 500);
                });
            }, piezas.length * 700 + 1000);
        }
    </script>
</body>
</html>
