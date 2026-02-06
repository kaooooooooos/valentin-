<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Veux-tu être mon·/ma Valentin·e ? ❤️</title>

<style>
    body {
        font-family: "Arial", sans-serif;
        text-align: center;
        background: #ffe6ee;
        color: #b30047;
        padding: 40px;
    }

    h1 {
        font-size: 2.8rem;
        margin-bottom: 30px;
    }

    button {
        font-size: 1.3rem;
        padding: 15px 30px;
        margin: 15px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        transition: transform 0.2s ease;
    }

    #yesBtn {
        background: #ff4f79;
        color: white;
    }

    #noBtn {
        background: white;
        border: 3px solid #ff4f79;
        color: #ff4f79;
    }
</style>
</head>
<body>

<h1>Veux-tu être ma Valentine ? ❤️</h1>

<button id="yesBtn">Oui 😍</button>
<button id="noBtn">Non 😢</button>

<script>
    const yesBtn = document.getElementById('yesBtn');
    const noBtn = document.getElementById('noBtn');

    yesBtn.addEventListener('click', () => {
        document.body.innerHTML = `
            <h1>bonne reponse bebou bien  ❤️</h1>
            <p>ta enfin une bonne reponse je t'aime mon chaaaat 💖</p>
        `;
        launchConfetti();
    });

    let noClicks = 0;
    const noMessages = [
        "Essaye encore ptet tu va trouver la bonne reponse  😉",
        "Ta pas assez reflechis continue oe ",
        "Vje vais commencer a le prendre mal fait gaffe  😅",
        "tu veux que je pleure c'est ça ? tu veux me faire du mal c'est ça ?❤️"
    ];

    noBtn.addEventListener('click', () => {
        if (noClicks < noMessages.length) {
            noBtn.textContent = noMessages[noClicks];
            yesBtn.style.transform = `scale(${1 + noClicks*0.15})`;
        } else {
            noBtn.style.display = 'none';
        }
        noClicks++;
    });

    function launchConfetti() {
        const script = document.createElement('script');
        script.src = "https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js";
        document.body.appendChild(script);
        script.onload = () => confetti({ particleCount: 100, spread: 70 });
    }
</script>

</body>
</html>

