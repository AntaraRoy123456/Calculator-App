# Calculator-App
<!DOCTYPE html>
<html>
<head>
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }

    .calculator {
      width: 200px;
      background-color: #f4f4f4;
      padding: 10px;
      border-radius: 5px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    }

    .calculator input {
      width: 100%;
      padding: 5px;
      margin-bottom: 10px;
    }

    .calculator button {
      width: 48%;
      padding: 10px;
      font-size: 16px;
    }

    .calculator button.clear {
      background-color: #ff4136;
      color: #fff;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="result" disabled>

    <button onclick="clearInput()" class="clear">C</button>
    <button onclick="appendNumber(1)">1</button>
    <button onclick="appendNumber(2)">2</button>
    <button onclick="appendNumber(3)">3</button>
    <button onclick="appendNumber(4)">4</button>
    <button onclick="appendNumber(5)">5</button>
    <button onclick="appendNumber(6)">6</button>
    <button onclick="appendNumber(7)">7</button>
    <button onclick="appendNumber(8)">8</button>
    <button onclick="appendNumber(9)">9</button>
    <button onclick="appendOperator('*')">*</button>
    <button onclick="appendOperator('+')">+</button>
    <button onclick="appendOperator('-')">-</button>
    <button onclick="appendOperator('/')">/</button>
    <button onclick="appendNumber(0)">0</button>
    <button onclick="calculate()">=</button>
  </div>
  <script>
    function appendNumber(number) {
      var result = document.getElementById('result');
      result.value += number;
    }

    function appendOperator(operator) {
      var result = document.getElementById('result');
      var lastChar = result.value.slice(-1);
      if (lastChar !== '+' && lastChar !== '-' && lastChar !== '*' && lastChar !== '/') {
        result.value += operator;
      }
    }

    function calculate() {
      var result = document.getElementById('result');
      var expression = result.value;
      var answer = eval(expression);
      result.value = answer;
    }

    function clearInput() {
      var result = document.getElementById('result');
      result.value = '';
    }
  </script>
</body>
</html>
