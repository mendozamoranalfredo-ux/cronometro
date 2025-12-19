# cronometro
tiempo para casarnos
index.html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Cuenta regresiva 07/04/2031</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #020617;
      color: #e5e7eb;
      font-family: Arial, sans-serif;
    }

    .contenedor {
      text-align: center;
      padding: 40px 50px;
      background: #020617;
      border-radius: 14px;
      box-shadow: 0 0 40px rgba(0,0,0,0.6);
    }

    h1 {
      font-size: 2rem;
      margin-bottom: 20px;
    }

    .contador {
      font-size: 1.6rem;
      letter-spacing: 1px;
    }
  </style>
</head>
<body>

  <div class="contenedor">
    <h1>⏳ Cuenta regresiva</h1>
    <div class="contador" id="contador"></div>
  </div>

  <script>
    // Fecha objetivo: 07 de abril de 2031 - 00:00
    const fechaObjetivo = new Date("2031-04-07T00:00:00");

    function actualizarContador() {
      const ahora = new Date();
      const diferencia = fechaObjetivo - ahora;

      if (diferencia <= 0) {
        document.getElementById("contador").innerText =
          "🎉 Llegó el momento";
        return;
      }

      const totalSegundos = Math.floor(diferencia / 1000);
      const segundos = totalSegundos % 60;

      const totalMinutos = Math.floor(totalSegundos / 60);
      const minutos = totalMinutos % 60;

      const totalHoras = Math.floor(totalMinutos / 60);
      const horas = totalHoras % 24;

      const dias = Math.floor(totalHoras / 24);

      document.getElementById("contador").innerText =
        `${dias} días | ${horas} horas | ${minutos} minutos | ${segundos} segundos`;
    }

    setInterval(actualizarContador, 1000);
    actualizarContador();
  </script>

</body>
</html>
