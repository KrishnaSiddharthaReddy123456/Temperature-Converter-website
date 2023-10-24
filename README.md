<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Converter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        #container {
            margin: 50px auto;
            width: 300px;
        }

        input[type="number"] {
            width: 100px;
            padding: 5px;
        }

        select {
            width: 100px;
            padding: 5px;
        }

        button {
            padding: 5px 10px;
            background-color: #007BFF;
            color: #fff;
            border: none;
            cursor: pointer;
        }

        #result {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div id="container">
        <h2>Temperature Converter</h2>
        <input type="number" id="temperature" placeholder="Enter temperature">
        <select id="unit">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
        </select>
        <button onclick="convertTemperature()">Convert</button>
        <div id="result"></div>
    </div>

    <script>
        function convertTemperature() {
            const temperatureInput = document.getElementById("temperature").value;
            const unit = document.getElementById("unit").value;
            const resultElement = document.getElementById("result");

            if (unit === "celsius") {
                const fahrenheit = (temperatureInput * 9/5) + 32;
                resultElement.innerHTML = `${temperatureInput} &deg;C = ${fahrenheit.toFixed(2)} &deg;F`;
            } else if (unit === "fahrenheit") {
                const celsius = (temperatureInput - 32) * 5/9;
                resultElement.innerHTML = `${temperatureInput} &deg;F = ${celsius.toFixed(2)} &deg;C`;
            }
        }
    </script>
</body>
</html>
