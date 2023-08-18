# Calculator
<!DOCTYPE html>
<html>
<head>
<style>
.calculator {
    width: 300px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    background-color: #f5f5f5;
}

#display {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    font-size: 18px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 5px;
}

button {
    padding: 10px;
    font-size: 16px;
    background-color: #4285f4;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #357ae8;
}
</style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" readonly>
        <div class="buttons">
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('+')">+</button>
            <!-- Add more buttons here -->
            <button onclick="calculate()">=</button>
            <button onclick="clearDisplay()">C</button>
        </div>
    </div>
    <script>
        let currentInput = "";

        function appendToDisplay(value) {
            currentInput += value;
            updateDisplay();
        }

        function calculate() {
            try {
                const result = eval(currentInput);
                currentInput = result.toString();
                updateDisplay();
            } catch (error) {
                currentInput = "Error";
                updateDisplay();
            }
        }

        function clearDisplay() {
            currentInput = "";
            updateDisplay();
        }

        function updateDisplay() {
            const display = document.getElementById("display");
            display.value = currentInput;
        }
    </script>
</body>
</html>
