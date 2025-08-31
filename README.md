[prankv2.html](https://github.com/user-attachments/files/22061884/prankv2.html)[U<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Hacker Prank</title>
    <style>
        body {
            background-color: black;
            color: lime;
            font-family: monospace;
            text-align: center;
        }
        .binary {
            font-size: 14px;
            margin-top: 10px;
        }
        .mask {
            width: 100px;
            vertical-align: middle;
        }
        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
    </style>
</head>
<body>
    <div class="container">
        <img src="" class="mask">
        <div>
            <div id="hackText">Initializing secret hack...</div>
            <div id="binary" class="binary"></div>
        </div>
        <img src="" class="mask">
    </div>

    <script>
        const hackText = document.getElementById("hackText");
        const binary = document.getElementById("binary");
        const targets = ["NASA Server", "Secret Bank", "Google Account"];
        let index = 0;

        function glitchText(text) {
            return text.split("").map(c => Math.random() < 0.2 ? "01"[Math.floor(Math.random()*2)] : c).join("");
        }

        function updateBinary() {
            binary.innerText = Array.from({length: 50}, () => Math.random() < 0.5 ? "0" : "1").join(" ");
        }

        function hackStep() {
            if(index >= targets.length) index = 0;
            let target = `Breaching ${targets[index]}...`;
            let glitchCount = 0;

            const glitchInterval = setInterval(() => {
                hackText.innerText = glitchText(target);
                updateBinary();
                glitchCount++;
                if(glitchCount > 10) {
                    clearInterval(glitchInterval);
                    hackText.innerText = target;
                    setTimeout(() => { index++; hackStep(); }, 3000);
                }
            }, 100);
        }

        hackStep();
        setInterval(updateBinary, 200);
    </script>
</body>
</html>
ploading prankv2.html…]()
