<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de IMC</title>
    <h1>Academia dos boleiros</h1>
    <h2>Venha treinar seu físico conosco</h2>
    <h3>Telefone de contato : 3227- 4556</h3>
    <h4>@academiafitnissboleiropg </h4>
    <img src= "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRgGwI7ajK5S5vedLIdE71yKOiGbVzAE5sGWw&s" height="250" width="300">
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
            background-color: #256c81;
        }
        .container {
            max-width: 400px;
            margin: auto;
            padding: 20px;
            border: 1px solid #159791;
            border-radius: 10px;
            box-shadow: 2px 2px 10px rgba(164, 19, 177, 0.1);
        }
        input, select, button {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
            border: 10px solid #979513;
            border-radius: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Calculadora de IMC</h2>
        <label for="peso">Peso (kg):</label>
        <input type="number" id="peso" placeholder="Digite seu peso" required>
        
        <label for="altura">Altura (m):</label>
        <input type="number" id="altura" placeholder="Digite sua altura" step="0.01" required>
        
        <label for="sexo">Sexo:</label>
        <select id="sexo">
            <option value="masculino">Masculino</option>
            <option value="feminino">Feminino</option>
        </select>
        
        <button onclick="calcularIMC()">Calcular IMC</button>
        <h3 id="resultado"></h3>
    </div>

    <script>
        function calcularIMC() {
            let peso = parseFloat(document.getElementById('peso').value);
            let altura = parseFloat(document.getElementById('altura').value);
            let sexo = document.getElementById('sexo').value;
            
            if (!peso || !altura) {
                document.getElementById('resultado').innerText = "Por favor, preencha todos os campos corretamente.";
                return;
            }
            
            let imc = peso / (altura * altura);
            let classificacao = "";
            
            if (imc < 18.5) {
                classificacao = "Abaixo do peso";
            } else if (imc < 24.9) {
                classificacao = "Peso normal";
            } else if (imc < 29.9) {
                classificacao = "Sobrepeso";
            } else {
                classificacao = "Obesidade";
            }
            
            document.getElementById('resultado').innerText = `Seu IMC é ${imc.toFixed(2)} - ${classificacao}`;
        }
    </script>
</body>
</html>
