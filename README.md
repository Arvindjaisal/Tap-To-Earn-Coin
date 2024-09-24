
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tap to Earn Coin</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            font-family: Arial, sans-serif;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
        #coin-count {
            margin-top: 20px;
            font-size: 24px;
        }
    </style>
</head>
<body>
    <button id="earn-coin-btn">Tap to Earn Coin</button>
    <div id="coin-count">Coins: 0</div>

    <script>
        document.addEventListener("DOMContentLoaded", () => {
            const coinCountElement = document.getElementById("coin-count");
            const earnCoinBtn = document.getElementById("earn-coin-btn");
            let coinCount = parseInt(localStorage.getItem("coinCount")) || 0;

            function updateCoinCount() {
                coinCountElement.textContent = `Coins: ${coinCount}`;
            }

            earnCoinBtn.addEventListener("click", () => {
                coinCount++;
                localStorage.setItem("coinCount", coinCount);
                updateCoinCount();
            });

            updateCoinCount();
        });
    </script>
</body>
</html>
