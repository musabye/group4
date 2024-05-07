<!DOCTYPE html>
<html>
<head>
    <title>Calculator</title>
    <style>
        #calculator {
            width: 200px;
            background-color: rgb(16, 15, 15);
            padding: 10px;
        }
        button {
            width: 70px;
            height: 45px;
            margin: 5px;
            font-size: 20px;
        }
        #display {
            width: 100%;
            margin-bottom: 10px;
            font-size: 20px;
        }
    </style>
</head>
<body>

<div id="calculator">
    <input type="text" id="display" readonly>
    <br>
    <button onclick="addToDisplay('1')">1</button>
    <button onclick="addToDisplay('2')">2</button>
    <button onclick="addToDisplay('3')">3</button>
    <button onclick="addToDisplay('4')">4</button>
    <br>
    <button onclick="addToDisplay('5')">5</button>
    <button onclick="addToDisplay('6')">6</button>
    <button onclick="addToDisplay('7')">7</button>
    <button onclick="addToDisplay('8')">8</button>
    <br>
    <button onclick="addToDisplay('9')">9</button>
    <button onclick="addToDisplay('0')">0</button>
    <button onclick="addToDisplay('+')">+</button>
    <button onclick="addToDisplay('_')">_</button>
    <br>
    <button onclick="addToDisplay('*')">*</button>
    <button onclick="addToDisplay('.')">.</button>
    <button onclick="calculate()">=</button>
    <button onclick="addToDisplay('/')">/</button>
</div>

<script>
    var display = document.getElementById("display");

    function addToDisplay(value) {
        display.value += value;
    }

    function calculate() {
        try {
            display.value = eval(display.value);
        } catch (error) {
            display.value = "Error";
        }
    }

    window.addEventListener("keydown", function(event) {
        var key = event.key;
        if ((key >= '0' && key <= '9') || ['+', '-', '*', '/', '.'].includes(key)) {
            addToDisplay(key);
        } else if (key === 'Enter') {
            calculate();
        } else if (key === 'Backspace') {
            display.value = display.value.slice(0, -1);
        }
    });
</script>

</body>
</html>
