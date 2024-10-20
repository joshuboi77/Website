<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A2</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet">
    <style>

        a {
            text-decoration: none; /* Removes the underline */
            color: inherit; /* Inherits the current text color from the parent */
        }

        a:hover {
            color: inherit; /* Keeps the hover color the same */
        }

        * {
            box-sizing: border-box;
        }

        html, body {
            height: 100%;
            margin: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            background: url('Images/Background.webp') no-repeat center center fixed;
            background-size: cover;
            color: #e0e0e0;
            display: flex;
            flex-direction: column;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0px 0;
            text-align: center;
        }

        .head-trade {
            display: flex;
            justify-content: left;
            margin-left: 2px;
            flex-grow: 1;
            padding-left: 10px;
        }

        .trade-button {
            background-color: rgba(255, 255, 255, 0);
            color: rgb(0, 0, 0);
            font-family: 'Dancing Script', cursive;
            font-size: 2em;
            padding: 10px 20px;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            text-align: center;
        }

        .trade-button:hover {
            background-color: rgba(255, 255, 255, 0.6);
        }

        .sidebar {
            position: fixed;
            top: .5px;
            left: -300px;
            width: 300px;
            height: 99.9%;
            background: rgba(192, 192, 192, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 0 10px 10px 0;
            padding: 0px;  /* Remove padding to align the elements better */
            transition: 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.3);
            z-index: 1000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        .sidebar.active {
            left: 0;
        }

        .nav-buttons {
            margin-top: auto; /* Ensures buttons stay at the bottom */
            flex-direction: column;
            align-items: center;
        }

        .nav-button {
            background-color: rgba(249, 5, 5, 0.977);
            color: white;
            font-family: 'Helvetica', sans-serif;
            font-size: 16px;
            padding: 12px 30px;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            margin: 10px 0;
            display: block;
            text-align: center; /* Center the text */
            width: 80%;
            max-width: 250px;
            min-width: 200px;
            white-space: nowrap;
        }

        .nav-button:hover {
            background-color: rgba(255, 255, 255, 0.6);
        }

        .close-btn {
            background-color: transparent;
            border: none;
            font-size: 24px;
            color: #e0e0e0;
            position: absolute;
            top: 5px; /* Snugged into the corner */
            right: 5px; /* Snugged into the corner */
            cursor: pointer;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 500;
            opacity: 0;
            transition: opacity 0.3s ease;
            visibility: hidden;
        }

        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        main {
            display: flex;
            flex-grow: 1;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }

        .main-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            padding: 40px;
            width: 100%;
        }

        .grid-box {
            background: rgba(50, 50, 50, 0.3); /* Darker foggy background */
            backdrop-filter: blur(10px);
            border-radius: 10px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 20px;
            text-align: center;
            color: white;
            transition: transform 0.3s ease;
        }

        .grid-box:hover {
            transform: translateY(-10px); /* Slight hover effect */
        }

        .grid-box h2 {
            margin: 0;
            font-size: 1.5em;
            font-family: 'Dancing Script', cursive;
        }

        .grid-box p {
            font-size: 1em;
        }

        footer {
            padding: 10px 0;
            background: rgba(51, 51, 51, 0.8);
            color: #e0e0e0;
            text-align: center;
            font-size: 0.8em;
            margin-top: auto;
        }
    </style>
</head>
<body>
    <header>
        <nav class="head-trade">
            <button class="trade-button" onclick="toggleSidebar()">Tr@d3</button>
        </nav>
    </header>

    <!-- Sidebar -->
    <div class="sidebar" id="sidebar">
        <!-- Close Button -->
        <button class="close-btn" onclick="toggleSidebar()">×</button>

        <!-- Navigation Buttons at the bottom -->
        <div class="nav-buttons">
            <button class="nav-button">About</button>
            <button class="nav-button">Services</button>
            <button class="nav-button">Contact</button>
        </div>
    </div>

    <!-- Overlay for clicking outside to close -->
    <div class="overlay" id="overlay" onclick="toggleSidebar()"></div>

    <main>
        <!-- Main Content Area with Grid -->
        <div class="main-content">
            <a href="page1.html">
                <div class="grid-box">
                    <h2>Box 1</h2>
                    <p>Tech and Digital</p>
                </div>
            </a>
            <a href="page2.html">
                <div class="grid-box">
                    <h2>Box 2</h2>
                    <p>Home and Repairs</p>
                </div>
            </a>
            <a href="page3.html">
                <div class="grid-box">
                    <h2>Box 3</h2>
                    <p>Health and Wellness</p>
                </div>
            </a>
            <a href="page4.html">
                <div class="grid-box">
                    <h2>Box 4</h2>
                    <p>Arts and Design</p>
                </div>
            </a>
            <a href="page5.html">
                <div class="grid-box">
                    <h2>Box 5</h2>
                    <p>Education and Tutoring</p>
                </div>
            </a>
            <a href="page6.html">
                <div class="grid-box">
                    <h2>Box 6</h2>
                    <p>Odds and Ends</p>
                </div>
            </a>
        </div>
    </main>
    
    <footer>
        <p>© 2024 jg05. All rights reserved.</p>
    </footer>

    <script>
        function toggleSidebar() {
            const sidebar = document.getElementById('sidebar');
            const overlay = document.getElementById('overlay');
            sidebar.classList.toggle('active');
            overlay.classList.toggle('active');
        }
    </script>
</body>
</html>
