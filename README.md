html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora Simples</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="calculadora">
        <input type="text" id="visor" readonly>
        
        <div class="botoes">
            <button onclick="limpar()">C</button>
            <button onclick="apagar()">←</button>
            <button onclick="adicionar('%')">%</button>
            <button class="operador" onclick="adicionar('/')">/</button>
            
            <button onclick="adicionar('7')">7</button>
            <button onclick="adicionar('8')">8</button>
            <button onclick="adicionar('9')">9</button>
            <button class="operador" onclick="adicionar('*')">*</button>
            
            <button onclick="adicionar('4')">4</button>
            <button onclick="adicionar('5')">5</button>
            <button onclick="adicionar('6')">6</button>
            <button class="operador" onclick="adicionar('-')">-</button>
            
            <button onclick="adicionar('1')">1</button>
            <button onclick="adicionar('2')">2</button>
            <button onclick="adicionar('3')">3</button>
            <button class="operador" onclick="adicionar('+')">+</button>
            
            <button onclick="adicionar('0')">0</button>
            <button onclick="adicionar('.')">.</button>
            <button onclick="calcular()" class="operador" style="grid-column: span 2;">=</button>
        </div>
    </div>
    <script src="script.js" defer></script>
</body>
</html>

CSS

}
.botoes {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 5px;
}
button {
  padding: 10px;
  font-size: 18px;
  border: none;
  background-color: #000000;
  color: rgb(255, 255, 255);
  cursor: pointer;
  transition: background-color 0.3s;
}
button:hover {
  background-color: #000000;
}
.operador {
  background-color: #ff1100;
}
.operador:hover {
  background-color: #da190b;
}


JAVASCRIPT

function adicionar(valor) {
  document.getElementById('visor').value += valor;
}

function limpar() {
  document.getElementById('visor').value = '';
}

function apagar() {
  var visor = document.getElementById('visor');
  visor.value = visor.value.slice(0, -1);
}

function calcular() {
  var visor = document.getElementById('visor');
  try {
      visor.value = eval(visor.value);
  } catch (error) {
      visor.value = 'Erro';
  }
}
