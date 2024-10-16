<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>xiomarita</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: #000000;
        }
        .hearth {
            height: 150px;
            width: 150px;
            background-color: rgb(255, 0, 212);
            position: relative;
            transform: rotate(45deg);
            box-shadow: -20px 20px 150px #f204b7;
            animation: palpitar 0.5s linear infinite alternate;
            cursor: pointer; /* Para mostrar que es clickable */
        }
        .contenido {
            text-align: center;
        }
        h1, h2 {
            color: white;
            margin: 0; /* Remove any default margin */
            padding: 0; /* Remove any default padding */
        }
        @keyframes palpitar {
            0% {transform: rotate(45deg) scale(1.10);}
            80% {transform: rotate(45deg) scale(1.0);}
            100% {transform: rotate(45deg) scale(0.8);}
        }
        .hearth::before {
            content: "";
            position: absolute;
            height: 150px;
            width: 150px;
            background-color: rgb(255, 0, 212);
            right: 50%;
            border-radius: 50%;
            box-shadow: 20px 20px 150px #f204a3;
        }
        .hearth::after {
            content: "";
            position: absolute;
            height: 150px;
            width: 150px;
            background-color: rgb(255, 0, 212);
            top: -50%;
            border-radius: 50%;
            box-shadow: 20px 20px 150px #f204be;
        }
    </style>
</head>
<body>
    <div class="hearth" id="corazon"></div>
    <div class="contenido">
        <h1>¡Feliz 1er mes mi negrita preciosa!</h1>
        <h2 id="mensaje"></h2>
    </div>
    <script>
        const mensajes = [        
        "gracias por este primer mes tan hermoso",
        "sé que hemos tenido muchos altibajos",
        "pero tenemos las ganas de mejorar por nosotros",
        // (rest of your messages...)
        ];
        let indiceMensaje = 0;
        const corazon = document.getElementById("corazon");
        const mensaje = document.getElementById("mensaje");
        corazon.addEventListener("click", () => {
            mensaje.textContent = mensajes[indiceMensaje];           
            indiceMensaje = (indiceMensaje + 1) % mensajes.length;
        });
    </script>
</body>
</html>

