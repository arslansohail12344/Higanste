<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Move the Car!</title>
    <style>
        body {
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }
        #gameArea {
            position: relative;
            width: 800px;
            height: 600px;
            border: 2px solid #000;
            background-color: #fff;
        }
        #car {
            position: absolute;
            width: 50px;
            height: 100px;
            background-image: url('car.png'); /* Replace with your car image URL */
            background-size: cover;
        }
    </style>
</head>
<body>
    <div id="gameArea">
        <div id="car"></div>
    </div>
    <script>
        const car = document.getElementById('car');
        const gameArea = document.getElementById('gameArea');
        let carX = 375; // Starting X position
        let carY = 250; // Starting Y position
        const step = 10; // Step size

        // Set initial position
        car.style.left = carX + 'px';
        car.style.top = carY + 'px';

        // Handle key press events
        window.addEventListener('keydown', (e) => {
            switch(e.key) {
                case 'w': // Move up
                    if (carY > 0) carY -= step;
                    break;
                case 's': // Move down
                    if (carY < gameArea.clientHeight - car.clientHeight) carY += step;
                    break;
                case 'a': // Move left
                    if (carX > 0) carX -= step;
                    break;
                case 'd': // Move right
                    if (carX < gameArea.clientWidth - car.clientWidth) carX += step;
                    break;
            }
            car.style.left = carX + 'px';
            car.style.top = carY + 'px';
        });
    </script>
</body>
</html>
