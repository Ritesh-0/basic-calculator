
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Basic Calculator</title>
  <style>
    .calculator {
      width: 250px;
      margin: 0 auto;
      text-align: center;
    }
    #display {
      width: 100%;
      height: 40px;
      margin-bottom: 10px;
      font-size: 20px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      grid-gap: 5px;
    }
    button {
      width: 50px;
      height: 50px;
      font-size: 20px;
    }
  </style>
</head>
<body>
<div class="calculator">
  <input type="text" id="display" disabled>
  <div class="buttons">
    <button class="number">7</button>
    <button class="number">8</button>
    <button class="number">9</button>
    <button class="operator">/</button>
    <button class="number">4</button>
    <button class="number">5</button>
    <button class="number">6</button>
    <button class="operator">*</button>
    <button class="number">1</button>
    <button class="number">2</button>
    <button class="number">3</button>
    <button class="operator">-</button>
    <button class="number">0</button>
    <button class="operator">C</button>
    <button class="operator">=</button>
    <button class="operator">+</button>
    <button id="decimal">.</button>
  </div>
</div>
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const display = document.getElementById("display");
    const buttons = document.querySelectorAll(".buttons button");
    let currentInput = "";
    let result = "";
    buttons.forEach(button => {
      button.addEventListener("click", function() {
        const buttonText = this.innerText;
        if (buttonText === "=") {
          result = eval(currentInput);
          display.value = result;
          currentInput = result;
        } else if (buttonText === "C") {
          currentInput = "";
          display.value = "";
        } else {
          currentInput += buttonText;
          display.value = currentInput;
        }
      });
    });
  });
</script>
</body>
</html># basic-calculator
