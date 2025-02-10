# mi-valentin-
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi Valentín?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            padding: 50px;
            background-color: #ffebee;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            height: 100vh;
            position: relative;
            overflow: hidden;
        }

        /* Fondo de corazón */
        body::before {
            content: "";
            position: absolute;
            width: 200px;
            height: 200px;
            background-color: #d32f2f;
            top: 30%;
            left: 50%;
            transform: translate(-50%, -50%) rotate(-45deg);
            border-radius: 50% 50% 0 0;
            z-index: -1;
        }

        body::after {
            content: "";
            position: absolute;
            width: 200px;
            height: 200px;
            background-color: #d32f2f;
            top: 30%;
            left: 50%;
            transform: translate(-50%, -50%) rotate(-45deg);
            border-radius: 50% 50% 0 0;
            z-index: -1;
            clip-path: polygon(50% 0%, 100% 35%, 100% 100%, 0% 100%, 0% 35%);
        }

        h1 {
            color: #d32f2f;
            font-size: 3em;
        }

        p {
            color: #555;
            font-size: 1.5em;
        }

        img {
            max-width: 100%;
            height: auto;
            border-radius: 15px;
            margin: 20px 0;
        }

        button, input[type="file"] {
            background-color: #d32f2f;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.2em;
            border-radius: 10px;
            cursor: pointer;
            margin: 10px;
            transition: all 0.3s ease;
        }

        button:hover, input[type="file"]:hover {
            background-color: #b71c1c;
        }

        input[type="file"] {
            display: block;
            margin: 20px auto;
            cursor: pointer;
            padding: 10px;
            font-size: 1em;
        }

    </style>
</head>
<body>
    <h1>¡Hola, mi amor!</h1>
    <p>Este 14 de febrero, quiero preguntarte algo muy especial...</p>

    <input type="file" accept="image/*" id="fileInput">
    <img src="https://via.placeholder.com/400" alt="Nuestra foto" id="previewImg">

    <p>¿Quieres ser mi Valentín?</p>
    <button id="yesBtn" onclick="alert('¡Eres la mejor! 💖')">Sí</button>
    <button id="noBtn" onclick="makeYesBigger()">No</button>

    <script>
        let yesBtn = document.getElementById('yesBtn');
        let size = 1.2; // Tamaño inicial del botón "Sí"

        function makeYesBigger() {
            size += 0.5; // Aumenta el tamaño
            yesBtn.style.fontSize = `${size}em`;
            yesBtn.style.padding = `${15 * size / 1.2}px ${30 * size / 1.2}px`;
            alert('¡Intenta de nuevo! 😉');
        }

        document.getElementById('fileInput').addEventListener('change', function(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('previewImg').src = e.target.result;
                }
                reader.readAsDataURL(file);
            }
        });
    </script>
</body>
</html>
