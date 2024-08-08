<!DOCTYPE html>
<html lang="es">
<head>
       <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>@codewith_muhilan</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <style>
        body {
            
            
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
        }
        input, button {
            display: block;
            width: 100%;
            margin: 10px 0;
            padding: 5px;
        }
        #resultado {
            margin-top: 20px;
            font-weight: bold;
        }
        #generando {
            display: none;
        }
        .barra-progreso {
           width: 200px;
            height: 20px;
            border: 1px solid #ddd;
            overflow: hidden;
            position: relative;
            border-radius: 5px;
        }
        .progreso {
width: 10%; height: 100%;
            background: linear-gradient(90deg, #8f8a8a, #d7d5d5, #fff);
            animation: loader 3s linear infinite; box-shadow: 0 0 25px #00fffc;
        }
        
        
.column {
    display: flex;
    justify-content: center;
    margin: 50px auto;
}
.column div {
    position: relative;
    overflow: hidden;
}
.column figure {
    margin: 0;
}
.column img {
    width: 100%; /* Use 100% for responsiveness */
    height: auto;
    transition: transform 0.3s ease;
}
.column:hover img {
    transform: scale(1.1);
}
@media (min-width: 768px) {
    .column {
        max-width: 80%;
    }
}


    
    /* -- YouTube Link Styles -- */
      

    </style>
</head>
<body>
  



    <h1>Generador de Sensibilidad para Dispositivos Móviles</h1>
    
    <label for="idCuenta">ID de Cuenta (8-10 dígitos):</label>
    <input type="text" id="idCuenta" required minlength="8" maxlength="10" pattern="\d{8,10}">
    
    <button onclick="generarSensibilidad()">Generar Sensibilidad</button>
    
    <div id="generando">
        <p>Generando sensibilidad...</p>
        <div class="barra-progreso">
            <div class="progreso"></div>
        </div>
    </div>
    
    <div id="resultado"></div>

    <script>
        function generarSensibilidad() {
            const idCuenta = document.getElementById('idCuenta').value;
            if (idCuenta.length < 8 || idCuenta.length > 10 || !/^\d+$/.test(idCuenta)) {
                alert('Por favor, ingrese un ID de cuenta válido (8-10 dígitos).');
                return;
            }

            const generando = document.getElementById('generando');
            const resultado = document.getElementById('resultado');
            const progreso = document.querySelector('.progreso');

            generando.style.display = 'block';
            resultado.innerHTML = '';
            
            let tiempoTranscurrido = 0;
            const intervalo = setInterval(() => {
                tiempoTranscurrido += 0.5;
                const porcentajeProgreso = (tiempoTranscurrido / 8) * 100;
                progreso.style.width = porcentajeProgreso + '%';
            }, 500);

            setTimeout(() => {
                clearInterval(intervalo);
                generando.style.display = 'none';
                
                const sensibilidadGeneral = Math.floor(Math.random() * (200 - 160 + 1) + 160);
                const sensibilidadPuntoRojo = Math.floor(Math.random() * (190 - 150 + 1) + 150);
                const sensibilidadMiraX2 = Math.floor(Math.random() * (150 - 100 + 1) + 100);
                const sensibilidadMiraX4 = Math.floor(Math.random() * (150 - 100 + 1) + 100);
                const sensibilidadAwm = Math.floor(Math.random() * (100 - 20 + 1) + 20);
                const sensibilidadCamara = Math.floor(Math.random() * (100 - 20 + 1) + 20);
                const tamanoBotonDisparo = Math.floor(Math.random() * (100 - 40 + 1) + 40);
                const dpi = Math.floor(Math.random() * (600 - 440 + 1) + 440);

                resultado.innerHTML = `
                    <h2>Resultados:</h2>
                    <p>Sensibilidad General: ${sensibilidadGeneral}%</p>
                    <p>Sensibilidad Punto Rojo: ${sensibilidadPuntoRojo}%</p>
                    <p>Sensibilidad Mira X2: ${sensibilidadMiraX2}%</p>
                    <p>Sensibilidad Mira X4: ${sensibilidadMiraX4}%</p>
                    <p>Sensibilidad AWM: ${sensibilidadAwm}%</p>
                    <p>Sensibilidad Cámara: ${sensibilidadCamara}%</p>
                    <p>Tamaño Botón de Disparo: ${tamanoBotonDisparo}%</p>
                    <p>DPI: ${dpi}%</p>
                `;
            }, 8000);
        }
    </script>

 
</body>


<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>@codewith_muhilan</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">

    <style>
        body, html, #app {
            margin: 0;
            width: 100%;
            height: 100%;
        }

        #app {
          overflow: hidden;
          color: #ffffff;
          font-family: 'Montserrat',
          sans-serif;
          text-align: center;
          text-shadow: 0 0 5px 
        #ffffff, 0 0 20px #000,
          0 0 30px #000;
        }
        
        #app h1 {
            --fontSize: 60px;
            --lineHeight: 80px;
            width: auto;
            height: calc(2 * var(--lineHeight));
            line-height: var(--lineHeight);
            margin: calc(50vh - var(--lineHeight)) auto 0;
            font-size: var(--fontSize);
        }

        #app a {
            margin-top: 10px;
            display: inline-block;
            text-decoration: none;
            color: #fd378d;
        }

        #app canvas {
            display: block;
            position: fixed;
            z-index: -1;
            top: 0;
        }

        
    /* -- YouTube Link Styles -- */

    #source-link {
      top: 60px;
    }

    #source-link>i {
      color: rgb(94, 106, 210);
    }

    #yt-link {
      top: 10px;
    }

    #yt-link>i {
      color: rgb(219, 31, 106);

    }

    .meta-link {
      align-items: center;
      backdrop-filter: blur(3px);
      background-color: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 6px;
      box-shadow: 2px 2px 2px rgba(0, 0, 0, 0.1);
      cursor: pointer;
      display: inline-flex;
      gap: 5px;
      left: 10px;
      padding: 10px 20px;
      position: fixed;
      text-decoration: none;
      transition: background-color 600ms, border-color 600ms;
      z-index: 10000;
    }

    .meta-link:hover {
      background-color: rgba(255, 255, 255, 0.1);
      border: 1px solid rgba(255, 255, 255, 0.2);
    }

    .meta-link>i,
    .meta-link>span {
      height: 20px;
      line-height: 20px;
    }

    .meta-link>span {
      color: white;
      font-family: "Rubik", sans-serif;
      transition: color 600ms;
    }


    </style>


</html>
