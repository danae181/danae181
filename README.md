<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Generador de Código QR</title>
    <script src="qrcode.min.js"></script> <!-- Asegúrate de incluir el archivo JS de la biblioteca -->
</head>
<body>
    <h2>Generador de Código QR</h2>
    <div id="codigo-qr"></div>

    <script>
        // Texto para el código QR (puedes poner la URL del formulario o cualquier otro texto)
        const textoQR = `
            <!DOCTYPE html>
            <html lang="es">
            <head>
                <meta charset="UTF-8">
                <meta name="viewport" content="width=device-width, initial-scale=1.0">
                <title>Encuesta de Satisfacción del Servicio</title>
                <style>
                    /* Estilos para el mensaje de confirmación */
                    #mensaje-confirmacion {
                        display: none;
                        margin-top: 20px;
                        padding: 10px;
                        background-color: #c9f6ff;
                        border: 1px solid #4fc3f7;
                        border-radius: 5px;
                        text-align: center;
                        animation: slideInLeft 1s forwards;
                    }
                </style>
            </head>
            <body>
                <h2>Encuesta de Satisfacción del Servicio</h2>
                <form action="#" method="POST" id="encuesta-form">
                    <label for="nombre">Nombre:</label><br>
                    <input type="text" id="nombre" name="nombre" required><br><br>
                    
                    <label for="edad">Edad:</label><br>
                    <input type="number" id="edad" name="edad" required><br><br>
                    
                    <label for="educacion">Nivel Educativo:</label><br>
                    <select id="educacion" name="educacion">
                        <option value="Primaria">Primaria</option>
                        <option value="Secundaria">Secundaria</option>
                        <option value="Preparatoria">Preparatoria</option>
                        <option value="Universidad">Universidad</option>
                        <option value="Posgrado">Posgrado</option>
                    </select><br><br>
                    
                    <label for="calificacion">Calificación del Servicio:</label><br>
                    <input type="range" id="calificacion" name="calificacion" min="1" max="10" step="1" required><br><br>
                    
                    <button type="submit">Enviar Encuesta</button>
                </form>
            </body>
            </html>
        `;

        // Generar el código QR
        const codigoQR = qrcode(0, 'M');
        codigoQR.addData(textoQR);
        codigoQR.make();

        // Mostrar el código QR en el elemento 'codigo-qr'
        const codigoQRDOM = codigoQR.createImgTag(5, 10); // Tamaño y margen opcionales
        document.getElementById('codigo-qr').innerHTML = codigoQRDOM;
    </script>
</body>
</html>
