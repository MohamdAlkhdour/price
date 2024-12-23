<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Real-Time Price Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background: #fff;
            padding: 20px 30px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            text-align: center;
            width: 300px;
        }
        h2 {
            color: #333;
            margin-bottom: 20px;
        }
        label {
            font-size: 16px;
            color: #555;
            margin-bottom: 10px;
            display: block;
        }
        input[type="number"] {
            width: calc(100% - 20px);
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        .results {
            margin-top: 20px;
        }
        .results p {
            font-size: 16px;
            color: #333;
        }
        span {
            font-weight: bold;
            color: #007bff;
        }
    </style>
    <script>
        function calculatePrice() {
            let price = parseFloat(document.getElementById("price").value);
            if (!isNaN(price)) {
                let plusResult = price + (price * 0.05); // price + (price * 0.025)
                let plusResult1 = price + (price * 0.025); // price + (price * 0.025)
                let plusResult2 = price + (price * 0.01); // price + (price * 0.01)
                let plusResult3 =price + (price * 0.005); // price + (price * 0.005)


                let minusResult = price - (price * 0.01); // price - (price * 0.01)
                let minusResult1 = price - (price * 0.025); // price - (price * 0.025)
                let minusResult2 = price - (price *0.05); //price - (price * 0.05)


                document.getElementById("plusResult").textContent = plusResult.toFixed(3);
                document.getElementById("plusResult1").textContent = plusResult1.toFixed(3);
                document.getElementById("plusResult2").textContent = plusResult2.toFixed(3);
                document.getElementById("plusResult3").textContent = plusResult3.toFixed(3);




                document.getElementById("minusResult").textContent = minusResult.toFixed(3);
                document.getElementById("minusResult1").textContent = minusResult1.toFixed(3);
                document.getElementById("minusResult2").textContent = minusResult2.toFixed(3);

            } else {
                document.getElementById("plusResult").textContent = "--";
                document.getElementById("plusResult1").textContent = "--";
                document.getElementById("plusResult2").textContent = "--";
                document.getElementById("plusResult3").textContent = "--";

                document.getElementById("minusResult").textContent = "--";
                document.getElementById("minusResult1").textContent = "--";
                document.getElementById("minusResult2").textContent = "--";

            }
        }
    </script>
</head>
<body>
    <div class="container">
        <h2>Price Calculator</h2>
        <label for="price">Enter Price:</label>
        <input type="number" id="price" step="0.001" placeholder="Enter a number" oninput="calculatePrice()">
        <div class="results">
            <p>Take Profit (5%) => <span id="plusResult"></span></p>
            <p>Take Profit (2.5%) => <span id="plusResult1"></span></p>
            <p>Take Profit (1%) => <span id="plusResult2"></span></p>
            <p>Take Profit (0.5%) => <span id="plusResult3"></span></p>

            <p>Stop Loss (1%) => <span id="minusResult"></span></p>
            <p>Stop Loss (2.5%) => <span id="minusResult1"></span></p>
            <p>Stop Loss ( 5%) => <span id="minusResult2"></span></p>

        </div>
    </div>
</body>
</html>
