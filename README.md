<!DOCTYPE htm<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Tabuada com Gmail</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      padding: 20px;
    }
    h1 {
      text-align: center;
      color: #333;
    }
    .container {
      max-width: 400px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    input, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      font-size: 16px;
    }
    #resultado {
      margin-top: 20px;
      background: #e7ffe7;
      padding: 10px;
      border-radius: 5px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h1>Tabuada Online</h1>
  <div class="container">
    <label for="email">Digite seu Gmail:</label>
    <input type="email" id="email" placeholder="exemplo@gmail.com" required>

    <label for="numero">Escolha um número:</label>
    <input type="number" id="numero" placeholder="Ex: 7" required>

    <button onclick="gerarTabuada()">Ver Tabuada</button>

    <div id="resultado"></div>
  </div>

  <script>
    function gerarTabuada() {
      const email = document.getElementById('email').value;
      const numero = parseInt(document.getElementById('numero').value);
      const resultadoDiv = document.getElementById('resultado');

      if (!email.includes('@gmail.com')) {
        resultadoDiv.innerHTML = 'Por favor, insira um Gmail válido.';
        return;
      }

      if (isNaN(numero)) {
        resultadoDiv.innerHTML = 'Por favor, insira um número válido.';
        return;
      }

      let resultado = `Olá ${email}, aqui está a tabuada do ${numero}:<br><br>`;
      for (let i = 1; i <= 10; i++) {
        resultado += `${numero} x ${i} = ${numero * i}<br>`;
      }

      resultadoDiv.innerHTML = resultado;
    }
  </script>

</body>
</html>
