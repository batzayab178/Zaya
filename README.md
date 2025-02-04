<!DOCTYPE html>
<html lang="mn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Батзаяатай үерхмээр байна уу?</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            background-color: #ffecf0;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        h1 {
            color: #ff4081;
            font-size: 24px;
        }
        button {
            font-size: 20px;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            transition: 0.3s;
        }
        .yes {
            background-color: #4CAF50;
            color: white;
        }
        .no {
            background-color: #FF5733;
            color: white;
        }
    </style>
</head>
<body>
    <h1>Чи Батзаяатай үерхмээр байна уу?</h1>
    <button class="yes" onclick="playAudio()">Тийм</button>
    <button class="no" onclick="resizeText()">Үгүй</button>

    <audio id="onniChan">
        <source src="onni_chan.mp3" type="audio/mpeg">
        Таны хөтөч энэ аудиог дэмжихгүй байна.
    </audio>

    <script>
        let yesButton = document.querySelector(".yes");
        let noButton = document.querySelector(".no");
        
        function resizeText() {
            let yesFontSize = window.getComputedStyle(yesButton).fontSize;
            let noFontSize = window.getComputedStyle(noButton).fontSize;

            yesButton.style.fontSize = (parseFloat(yesFontSize) + 5) + "px";
            noButton.style.fontSize = (parseFloat(noFontSize) - 2) + "px";
            
            if (parseFloat(noFontSize) <= 10) {
                noButton.style.display = "none";
            }
        }

        function playAudio() {
            alert("Батзаяаг сонгосонд баярлалаа! ❤️");
            document.getElementById("onniChan").play();
        }
    </script>
</body>
</html>
