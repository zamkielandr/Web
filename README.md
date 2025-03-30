<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>4 Aşamalı Web Sitesi</title>
    <style>
        body {
            background-color: #121212;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            display: none;
            width: 90%;
            max-width: 400px;
            padding: 20px;
            border: 2px solid white;
            border-radius: 10px;
        }
        .active {
            display: block;
        }
        button {
            background-color: #ff9800;
            color: black;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 18px;
        }
        button:hover {
            background-color: #e68900;
        }
        .video-container {
            width: 100%;
            aspect-ratio: 16 / 9;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div id="step1" class="container active">
        <p id="text1"></p>
        <button onclick="nextStep(2)">Haydi bakalım, bas şuna!</button>
    </div>
    <div id="step2" class="container">
        <p id="text2"></p>
        <button onclick="nextStep(3)">Tıklamaktan zarar gelmez!</button>
    </div>
    <div id="step3" class="container">
        <p id="text3"></p>
        <button onclick="nextStep(4, true)">Devam et!</button>
    </div>
    <div id="step4" class="container">
        <p id="text4">İyi Bayramlar !!</p>
        <div class="video-container">
            <iframe id="videoFrame" width="100%" height="100%" 
                src="about:blank" frameborder="0" 
                allow="autoplay; encrypted-media" allowfullscreen>
            </iframe>
        </div>
    </div>
    
    <script>
        function nextStep(step, playVideo = false) {
            document.querySelector('.active').classList.remove('active');
            document.getElementById(`step${step}`).classList.add('active');

            if (playVideo) {
                document.getElementById("videoFrame").src = "https://www.youtube.com/embed/-aFFXlrgGTY?autoplay=1&mute=0";
            }
        }
    </script>
</body>
</html>
