<--! python learning basics-->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Learn Python</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #121212;
            color: #e0e0e0;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }

        header {
            background: linear-gradient(45deg, #1976d2, #0d47a1);
            color: white;
            text-align: center;
            padding: 2rem;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        nav {
            background-color: #0d47a1;
            padding: 1rem;
        }

        nav ul {
            list-style-type: none;
            display: flex;
            justify-content: center;
            margin: 0;
            padding: 0;
        }

        nav ul li {
            margin: 0 15px;
        }

        nav ul li a {
            color: #90caf9;
            text-decoration: none;
            font-weight: bold;
        }

        nav ul li a:hover {
            color: #42a5f5;
            transition: color 0.3s;
        }

        section {
            margin: 20px;
            padding: 20px;
            background-color: #1e1e1e;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        h1, h2 {
            color: #42a5f5;
        }

        footer {
            text-align: center;
            padding: 1rem;
            background-color: #0d47a1;
            color: white;
            margin-top: auto;
            box-shadow: 0 -4px 8px rgba(0, 0, 0, 0.2);
        }

        textarea {
            width: 100%;
            margin-top: 10px;
            border: 2px solid #42a5f5;
            padding: 10px;
            border-radius: 5px;
            font-family: monospace;
            background-color: #212121;
            color: white;
        }

        button {
            background-color: #42a5f5;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
        }

        button:hover {
            background-color: #358ad3;
            transition: background-color 0.3s;
        }

        pre {
            background-color: #212121;
            padding: 15px;
            border-radius: 8px;
            border-left: 5px solid #42a5f5;
            overflow-x: auto;
            color: #90caf9;
        }

        #output {
            margin-top: 15px;
            padding: 10px;
            background-color: #1e1e1e;
            border-radius: 5px;
            border-left: 4px solid #42a5f5;
            color: #90caf9;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to Python Learning Hub</h1>
        <p>Your step-by-step guide to mastering Python programming.</p>
    </header>

    <nav>
        <ul>
            <li><a href="#intro">Introduction</a></li>
            <li><a href="#syntax">Basic Syntax</a></li>
            <li><a href="#functions">Functions & Return</a></li>
            <li><a href="#libraries">Using Libraries</a></li>
            <li><a href="#example">Example Program</a></li>
            <li><a href="#practice">Try it Yourself</a></li>
        </ul>
    </nav>

    <section id="intro">
        <h2>Introduction to Python</h2>
        <p>Python is a powerful programming language used for web development, data analysis, artificial intelligence, and more. It's known for its simplicity and readability.
        </p>
            <p>  It is a very simple language to learn so lets get started!! We are going to start with giving output. When you blend fruits in the grinder, we expect output: juice. In the same vain, if we want to get an output in python we use the print("text you want to output")  statement. Look at the code below and observe.
        </p>
    </section>

    <section id="syntax">
        <h2>Basic Syntax</h2>
        <ul>
            <li>Variables: <code>x = 5</code></li>
            <bold> <li>Print statement: <code>print("Hello, World!")

            </code></li><bold/>
            <li>Conditional statements: <code>if x > 0:</code></li>
        </ul>
    </section>

    <section id="functions">
        <h2>Functions & Return</h2>
        <p>Functions in Python are defined using the <code>def</code> keyword. The <code>return</code> statement sends back the result of the function.</p>
        <pre><code>
def square(number):
    return number * number

result = square(4)
print(result)  # Output will be 16
        </code></pre>
    </section>

    <section id="libraries">
        <h2>Using Libraries in Python</h2>
        <p>Python has a vast collection of libraries that you can import and use. Example:</p>
        <pre><code>
import math

result = math.sqrt(16)
print(result)  # Output will be 4.0
        </code></pre>
    </section>

    <section id="example">
        <h2>Example Program</h2>
        <p>Here’s a simple Python program that adds two numbers:</p>
        <pre><code>
def add_numbers(a, b):
    return a + b

result = add_numbers(3, 5)
print("The result is", result)
        </code></pre>
    </section>

    <section id="practice">
        <h2>Try it Yourself</h2>
        <p>Type your own Python code here and click 'Run Code' to see the output:</p>
        <textarea id="pythonCode" rows="10" cols="50"></textarea><br>
        <button onclick="runPython()">Run Code</button>
        <div id="output"></div>
    </section>

    <footer>
        <p>&copy; 2024 Python Learning Hub</p>
    </footer>

    <!-- Skulpt Python Interpreter -->
    <script src="https://cdn.jsdelivr.net/npm/skulpt@1.2.0/dist/skulpt.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/skulpt@1.2.0/dist/skulpt-stdlib.js"></script>

    <script>
        function outf(text) {
            var outputElement = document.getElementById("output");
            outputElement.innerHTML += text + "<br>";
        }

        function runPython() {
            var code = document.getElementById("pythonCode").value;
            var outputElement = document.getElementById("output");
            outputElement.innerHTML = "";  // Clear previous output

            Sk.configure({ output: outf, read: function(x) {
                if (Sk.builtinFiles === undefined || Sk.builtinFiles["files"][x] === undefined) {
                    throw "File not found: '" + x + "'";
                }
                return Sk.builtinFiles["files"][x];
            }});

            (Sk.TurtleGraphics || (Sk.TurtleGraphics = {})).target = 'output';
            var myPromise = Sk.misceval.asyncToPromise(function() {
                return Sk.importMainWithBody("<stdin>", false, code, true);
            });

            myPromise.then(function(mod) {
                console.log('success');
            }, function(err) {
                outputElement.innerHTML = err.toString();
            });
        }
    </script>
</body>
</html>
