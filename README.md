# Website-of-temperature-converter.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Temperature Converter</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <h1>Temperature Converter</h1>
    <input type="number" id="temperature" placeholder="Enter temperature">
    <select id="unit">
      <option value="celsius">Celsius</option>
      <option value="fahrenheit">Fahrenheit</option>
      <option value="kelvin">Kelvin</option>
    </select>
    <button onclick="convertTemperature()">Convert</button>
    <div class="output" id="output"></div>
  </div>
  <script src="script.js"></script>
</body>
</html>

#Temperature converter.css


body {
    font-family: Arial, sans-serif;
    margin: 20px;
    text-align: center;
    background-color: #f0f8ff;
  }
  
  .container {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    background: #ffffff;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
  }
  
  h1 {
    color: #333;
  }
  
  input[type="number"] {
    width: calc(100% - 20px);
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  select, button {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border: none;
    border-radius: 5px;
    background-color: #007bff;
    color: #fff;
    font-size: 16px;
    cursor: pointer;
  }
  
  select {
    background-color: #f9f9f9c9;
    color: #333;
  }
  
  button:hover {
    background-color: #00b39b;
  }
  
  .output {
    margin-top: 20px;
    font-size: 18px;
    color: #0044ff;
  }


  #Temperature converter.js

  function convertTemperature() {
    const temperatureInput = document.getElementById('temperature').value;
    const unit = document.getElementById('unit').value;
    const output = document.getElementById('output');
    if (!temperatureInput || isNaN(temperatureInput)) {
      output.textContent = 'Please enter a valid number.';
      return;
    }
    const temperature = parseFloat(temperatureInput);
    let result = '';
    if (unit === 'celsius') {
      result += ${(temperature * 9/5 + 32).toFixed(2)} °F (Fahrenheit)\n;
      result += ${(temperature + 273.15).toFixed(2)} K (Kelvin);
    } else if (unit === 'fahrenheit') {
      result += ${((temperature - 32) * 5/9).toFixed(2)} °C (Celsius)\n;
      result += ${(((temperature - 32) * 5/9) + 273.15).toFixed(2)} K (Kelvin);
    } else if (unit === 'kelvin') {
      result += ${(temperature - 273.15).toFixed(2)} °C (Celsius)\n;
      result += ${((temperature - 273.15) * 9/5 + 32).toFixed(2)} °F (Fahrenheit);
    }
    output.textContent = result;
  }

  
