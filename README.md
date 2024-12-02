<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Conversor para Nome Fonético</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f4f4f9;
      color: #333;
      padding: 20px;
    }
    h1 {
      color: #007BFF;
    }
    input {
      padding: 10px;
      margin: 10px 0;
      width: 80%;
      max-width: 300px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 10px 20px;
      background-color: #007BFF;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #0056b3;
    }
    #output {
      margin-top: 20px;
      font-size: 18px;
    }
  </style>
</head>
<body>
  <h1>Conversor para Nome Fonético</h1>
  <p>Insira um nome para converter para a forma fonética:</p>
  <input type="text" id="nameInput" placeholder="Digite o nome...">
  <button onclick="convertToPhonetic()">Converter</button>
  <div id="output"></div>

  <script>
    // Função que converte o nome em alfabeto fonético
    function convertToPhonetic() {
      const phoneticAlphabet = {
        A: "Alfa", B: "Bravo", C: "Charlie", D: "Delta", E: "Echo",
        F: "Foxtrot", G: "Golf", H: "Hotel", I: "Índia", J: "Juliet",
        K: "Kilo", L: "Lima", M: "Mike", N: "November", O: "Oscar",
        P: "Papa", Q: "Quebec", R: "Romeo", S: "Sierra", T: "Tango",
        U: "Uniform", V: "Victor", W: "Whiskey", X: "X-ray", Y: "Yankee", Z: "Zulu"
      };

      // Obtém o valor do campo de entrada
      const name = document.getElementById("nameInput").value.toUpperCase();

      if (!name) {
        document.getElementById("output").innerHTML = "Por favor, insira um nome.";
        return;
      }

      // Converte o nome em fonético
      let phoneticName = "";
      for (let char of name) {
        if (phoneticAlphabet[char]) {
          phoneticName += phoneticAlphabet[char] + " ";
        } else if (char === " ") {
          phoneticName += "/ "; // Representa espaço como "/"
        } else {
          phoneticName += char + " "; // Mantém caracteres não alfabéticos
        }
      }

      // Exibe o resultado
      document.getElementById("output").innerHTML = `
        <strong>Nome Original:</strong> ${name} <br>
        <strong>Nome Fonético:</strong> ${phoneticName.trim()}
      `;
    }
  </script>
</body>
</html>
