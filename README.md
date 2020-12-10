# Calc<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" type="text/css" href="cal.css">
    <title>Document</title>
</head>
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" type="text/css" href="cal.css">
    <title>Document</title>
</head>

<body>
    <h1>A simple calculator</h1>
    <div id="container">
        <div id="calculator">
            <div id="result">
                <div id="history">
                    <p id="history-value"></p>
                </div>
                <div id="output">
                    <p id="output-value"></p>
                </div>
                <div id="keyboard">
                    <button id="1" class="numbers">1</button><button id="2" class="numbers">2</button><button id="3" class="numbers">3</button>
                    <button id="4" class="numbers">4</button><button id="5" class="numbers">5</button>
                    <button id="6" class="numbers">6</button>
                    <button id="7" class="numbers">7</button><button id="+" class="operators">+</button>
                    <button id="8" class="numbers">8</button>
                    <button id="9" class="numbers">9</button><button id="0" class="numbers">0</button>
                    <button id="x" class="operators">x</button><button class="operators" id="clear">C</button>
                    <button class="operators" id="backspace">C/E</button> <button id="/" class="operators">/</button>
                    <button id="-" class="operators">-</button><button id="=" class="eqauls">=</button><button id="." class="numbers">.</button>
                </div>
            </div>
        </div>
        <script>function getHistory() {
            return document.getElementById("history-value").innerText;
        }
        
        function printHistory(num) {
            document.getElementById("history-value").innerText = num;
        }
        
        function getOutput() {
            return document.getElementById("output-value").innerText;
        }
        
        function printOutput(num) {
            document.getElementById("output-value").innerText = getFormatted(num);
        }
        
        function getFormatted(num) {
            if (num === "-") {
                return "";
            }
            var n = Number(num);
            var value = n.toLocaleString("en");
            return value;
        }
        
        function remFormatted(num) {
            return Number(num.replace(/,/g, ""));
        }
        var perator = document.getElementsByClassName("operators");
        for (i = 0; i < perator.length; i++) {
            perator[i].addEventListener("click", function() {
                if (this.id === "clear") {
                    printHistory("");
                    printOutput("");
                } else if (this.id === "backspace") {
                    var output = remFormatted(getOutput()).toString();
                    if (output !== NaN) {
                        output = output.substr(0, output.length - 1);
                        printOutput(output);
                    }
                } else {
                    var output = getOutput();
                    var history = getHistory();
                    if (isNaN(history[history.length - 1])) {
                        history = history.substr(0, history.length - 1);
                        printOutput(history);
        
                    }
                    if (output !== "" || history !== "") {
                        output = remFormatted(output);
                        history = history + this.id;
                        printHistory(history);
                        printOutput("");
                    }
                }
            })
        }
        var numbers = document.getElementsByClassName("numbers");
        for (i = 0; i < numbers.length; i++) {
            numbers[i].addEventListener("click", function() {
                var output = remFormatted(getHistory());
                var history = getHistory();
                if (output !== NaN) {
                    output = history + this.id;
                    printHistory(output);
                }
            })
        }
        const equate = document.getElementsByClassName("eqauls");
        equate.addEventListener("click", function() {
            var output = getOutput();
            var history = getHistory();
            history = output + history;
            var result = eval(output);
            printOutput(result);
            printHistory("");
        })
        </script>
</body>

</html>
<body>
    <h1>A simple calculator</h1>
    <div id="container">
        <div id="calculator">
            <div id="result">
                <div id="history">
                    <p id="history-value"></p>
                </div>
                <div id="output">
                    <p id="output-value"></p>
                </div>
                <div id="keyboard">
                    <button id="1" class="numbers">1</button><button id="2" class="numbers">2</button><button id="3" class="numbers">3</button>
                    <button id="4" class="numbers">4</button><button id="5" class="numbers">5</button>
                    <button id="6" class="numbers">6</button>
                    <button id="7" class="numbers">7</button><button id="+" class="operators">+</button>
                    <button id="8" class="numbers">8</button>
                    <button id="9" class="numbers">9</button><button id="0" class="numbers">0</button>
                    <button id="x" class="operators">x</button><button class="operators" id="clear">C</button>
                    <button class="operators" id="backspace">C/E</button> <button id="/" class="operators">/</button>
                    <button id="-" class="operators">-</button><button id="=" class="eqauls">=</button><button id="." class="numbers">.</button>
                </div>
            </div>
        </div>
        <script>function getHistory() {
            return document.getElementById("history-value").innerText;
        }
        
        function printHistory(num) {
            document.getElementById("history-value").innerText = num;
        }
        
        function getOutput() {
            return document.getElementById("output-value").innerText;
        }
        
        function printOutput(num) {
            document.getElementById("output-value").innerText = getFormatted(num);
        }
        
        function getFormatted(num) {
            if (num === "-") {
                return "";
            }
            var n = Number(num);
            var value = n.toLocaleString("en");
            return value;
        }
        
        function remFormatted(num) {
            return Number(num.replace(/,/g, ""));
        }
        var perator = document.getElementsByClassName("operators");
        for (i = 0; i < perator.length; i++) {
            perator[i].addEventListener("click", function() {
                if (this.id === "clear") {
                    printHistory("");
                    printOutput("");
                } else if (this.id === "backspace") {
                    var output = remFormatted(getOutput()).toString();
                    if (output !== NaN) {
                        output = output.substr(0, output.length - 1);
                        printOutput(output);
                    }
                } else {
                    var output = getOutput();
                    var history = getHistory();
                    if (isNaN(history[history.length - 1])) {
                        history = history.substr(0, history.length - 1);
                        printOutput(history);
        
                    }
                    if (output !== "" || history !== "") {
                        output = remFormatted(output);
                        history = history + this.id;
                        printHistory(history);
                        printOutput("");
                    }
                }
            })
        }
        var numbers = document.getElementsByClassName("numbers");
        for (i = 0; i < numbers.length; i++) {
            numbers[i].addEventListener("click", function() {
                var output = remFormatted(getHistory());
                var history = getHistory();
                if (output !== NaN) {
                    output = history + this.id;
                    printHistory(output);
                }
            })
        }
        const equate = document.getElementsByClassName("eqauls");
        equate.addEventListener("click", function() {
            var output = getOutput();
            var history = getHistory();
            history = output + history;
            var result = eval(output);
            printOutput(result);
            printHistory("");
        })
        </script>
</body>

</html>ulator
