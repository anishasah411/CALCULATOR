# CALCULATOR
#HTML CODE:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <link rel="stylesheet" href="cal.css">
</head>
<body>
    <div class="calculator">
        <div class="display" id="display"></div>
        <div class="buttons">
            <button class="btn" onclick="clearDisplay()">C</button>
            <button class="btn" onclick="appendCharacter('7')">7</button>
            <button class="btn" onclick="appendCharacter('8')">8</button>
            <button class="btn" onclick="appendCharacter('9')">9</button>
            <button class="btn" onclick="appendCharacter('/')">/</button>
            <button class="btn" onclick="appendCharacter('4')">4</button>
            <button class="btn" onclick="appendCharacter('5')">5</button>
            <button class="btn" onclick="appendCharacter('6')">6</button>
            <button class="btn" onclick="appendCharacter('*')">*</button>
            <button class="btn" onclick="appendCharacter('1')">1</button>
            <button class="btn" onclick="appendCharacter('2')">2</button>
            <button class="btn" onclick="appendCharacter('3')">3</button>
            <button class="btn" onclick="appendCharacter('-')">-</button>
            <button class="btn" onclick="appendCharacter('0')">0</button>
            <button class="btn" onclick="appendCharacter('.')">.</button>
            <button class="btn" onclick="calculateResult()">=</button>
            <button class="btn" onclick="appendCharacter('+')">+</button>
        </div>
    </div>
    <script src="cal.js"></script>
</body>
</html>

#CSS CODE
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f4f4f4;
    font-family: Arial, sans-serif;
}

.calculator {
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    width: 300px;
}

.display {
    background: #222;
    color: #fff;
    font-size: 2em;
    padding: 20px;
    text-align: right;
    border-bottom: 1px solid #999;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}

.btn {
    background: #f2f2f2;
    border: 1px solid #999;
    font-size: 1.5em;
    padding: 20px;
    text-align: center;
    cursor: pointer;
    transition: background 0.2s;
}

.btn:hover {
    background: #ddd;
}

#JS CODE:
let display = document.getElementById('display');
let currentInput = '';

function appendCharacter(char) {
    currentInput += char;
    display.innerText = currentInput;
}

function clearDisplay() {
    currentInput = '';
    display.innerText = '';
}

function calculateResult() {
    try {
        currentInput = eval(currentInput).toString();
        display.innerText = currentInput;
    } catch (e) {
        display.innerText = 'Error';
    }
}
