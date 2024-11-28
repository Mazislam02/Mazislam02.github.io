<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Photography Website</title>
    <style>
        /* General Styles */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: white;
            padding: 1em 0;
            text-align: center;
        }

        /* Navigation Menu Styles */
        .navbar {
            background-color: #444;
            overflow: hidden;
        }

        .navbar ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
        }

        .navbar li {
            position: relative;
        }

        .navbar a {
            display: block;
            color: white;
            text-decoration: none;
            padding: 14px 20px;
        }

        .navbar a:hover {
            background-color: #555;
        }

        .dropdown {
            display: none;
            position: absolute;
            background-color: #666;
            top: 100%;
            left: 0;
            min-width: 150px;
            z-index: 1000;
        }

        .dropdown a {
            padding: 10px 15px;
        }

        .navbar li:hover .dropdown {
            display: block;
        }

        /* Slider Styles */
        .slider {
            max-width: 100%;
            margin: 20px auto;
            position: relative;
            overflow: hidden;
        }

        .slides {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .slides img {
            width: 100%;
        }

        .slider-controls {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            transform: translateY(-50%);
        }

        .slider-controls button {
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
        }

        /* Calculator Styles */
        .calculator {
            max-width: 400px;
            margin: 20px auto;
            padding: 20px;
            background: white;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .calculator input, .calculator button {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            font-size: 16px;
        }

        .calculator button {
            background-color: #333;
            color: white;
            border: none;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <h1>Photography Website</h1>
    </header>

    <!-- Navigation Menu -->
    <nav class="navbar">
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Gallery</a>
                <ul class="dropdown">
                    <li><a href="#">Nature</a></li>
                    <li><a href="#">Portraits</a></li>
                </ul>
            </li>
            <li><a href="#">About Me</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>

    <!-- Slider -->
    <div class="slider">
        <div class="slides">
            <img src="https://via.placeholder.com/800x400?text=Photo+1" alt="Slide 1">
            <img src="https://via.placeholder.com/800x400?text=Photo+2" alt="Slide 2">
            <img src="https://via.placeholder.com/800x400?text=Photo+3" alt="Slide 3">
            <img src="https://via.placeholder.com/800x400?text=Photo+4" alt="Slide 4">
        </div>
        <div class="slider-controls">
            <button id="prev">❮</button>
            <button id="next">❯</button>
        </div>
    </div>

    <!-- Calculator -->
    <div class="calculator">
        <h2>Gas Mileage Calculator</h2>
        <input type="number" id="miles" placeholder="Miles Traveled">
        <input type="number" id="gallons" placeholder="Gallons of Gas Used">
        <button onclick="calculateMPG()">Calculate MPG</button>
        <p id="result"></p>
    </div>

    <script>
        // Slider Functionality
        let currentIndex = 0;
        const slides = document.querySelector('.slides');
        const slideImages = document.querySelectorAll('.slides img');

        document.getElementById('next').addEventListener('click', () => {
            currentIndex = (currentIndex + 1) % slideImages.length;
            updateSlider();
        });

        document.getElementById('prev').addEventListener('click', () => {
            currentIndex = (currentIndex - 1 + slideImages.length) % slideImages.length;
            updateSlider();
        });

        function updateSlider() {
            slides.style.transform = translateX(-${currentIndex * 100}%);
        }

        // Calculator Functionality
        function calculateMPG() {
            const miles = parseFloat(document.getElementById('miles').value);
            const gallons = parseFloat(document.getElementById('gallons').value);

            if (!isNaN(miles) && !isNaN(gallons) && gallons !== 0) {
                const mpg = miles / gallons;
                document.getElementById('result').innerText = Your car's mileage is ${mpg.toFixed(2)} MPG.;
            } else {
                document.getElementById('result').innerText = 'Please enter valid numbers.';
            }
        }
    </script>
</body>
</html>   
