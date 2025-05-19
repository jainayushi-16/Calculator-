<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f4f4f4;
      font-family: Arial, sans-serif;
    }

    .calculator {
      border: 1px solid #ccc;
      border-radius: 10px;
      padding: 20px;
      background: white;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    #display {
      width: 100%;
      height: 40px;
      margin-bottom: 10px;
      font-size: 1.5em;
      text-align: right;
      padding: 5px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }

    button {
      height: 60px;
      font-size: 1.2em;
      border: none;
      border-radius: 8px;
      background: #eee;
      cursor: pointer;
    }

    button:hover {
      background: #ddd;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <input type="text" id="display" disabled />

    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="appendValue('(')">(</button>
      <button onclick="appendValue(')')">)</button>
      <button onclick="deleteLast()">DEL</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('/')">÷</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('*')">×</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('-')">−</button>

      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button onclick="calculateResult()">=</button>
      <button onclick="appendValue('+')">+</button>
    </div>
  </div>

  <script>
    let display = document.getElementById('display');

    function appendValue(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = '';
    }

    function deleteLast() {
      display.value = display.value.slice(0, -1);
    }

    function calculateResult() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = 'Error';
      }
    }
  </script>

</body>
</html>
