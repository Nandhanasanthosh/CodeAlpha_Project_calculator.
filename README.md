# CodeAlpha_Project_calculator.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: Arial, sans-serif;
      background-color: grey;
    }
    .calculator {
      width: 220px;
      padding: 20px;
      border-radius: 10px;
      background-color:white;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    }
    .display {
      width: 100%;
      height: 50px;
      text-align: right;
      padding-right: 10px;
      font-size: 24px;
      border: none;
      margin-bottom: 10px;
      border-bottom: 2px solid #ddd;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    .buttons button {
      width: 100%;
      height: 50px;
      font-size: 18px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      background-color:#3b82f6;
      color: #fff;
    }
    .buttons button.operator {
      background-color: #ef4444;
    }
    .buttons button.clear {
      background-color: #a855f7;
    }
  </style>
</head><body>
<h2> Calculator</h2>  <div class="calculator">
    <input type="text" id="display" class="display" disabled>
    <div class="buttons">
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="appendToDisplay('(')">(</button>
      <button onclick="appendToDisplay(')')">)</button>
      <button onclick="appendToDisplay('/')">÷</button>

      <button onclick="appendToDisplay('7')">7</button>
      <button onclick="appendToDisplay('8')">8</button>
      <button onclick="appendToDisplay('9')">9</button>
      <button onclick="appendToDisplay('*')">×</button>

      <button onclick="appendToDisplay('4')">4</button>
      <button onclick="appendToDisplay('5')">5</button>
      <button onclick="appendToDisplay('6')">6</button>
      <button onclick="appendToDisplay('-')">−</button>

      <button onclick="appendToDisplay('1')">1</button>
      <button onclick="appendToDisplay('2')">2</button>
      <button onclick="appendToDisplay('3')">3</button>
      <button onclick="appendToDisplay('+')">+</button>

      <button onclick="appendToDisplay('0')">0</button>
      <button onclick="appendToDisplay('.')">.</button>
      <button onclick="calculateResult()" class="operator">=</button>
    </div>
  </div>

  <script>
    function clearDisplay() {
      document.getElementById('display').value = '';
    }

    function appendToDisplay(value) {
      document.getElementById('display').value += value;
    }

    function calculateResult() {
      try {
        const display = document.getElementById('display');
        display.value = eval(display.value);
      } catch (error) {
        display.value = 'Error';
      }
    }
  </script>
</body>
</html>
