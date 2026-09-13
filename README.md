# love-page
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Do You Love Me? ❤️</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    height: 100vh;
    overflow: hidden;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #ff758c, #ff7eb3);
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Floating hearts */
.heart {
    position: absolute;
    color: white;
    font-size: 25px;
    animation: float 6s linear infinite;
    opacity: 0.7;
}

@keyframes float {
    0% {
        transform: translateY(100vh) rotate(0deg);
        opacity: 0;
    }
    30% {
        opacity: 0.8;
    }
    100% {
        transform: translateY(-10vh) rotate(360deg);
        opacity: 0;
    }
}

.card {
    width: 90%;
    max-width: 400px;
    padding: 45px 25px;
    text-align: center;
    background: rgba(255,255,255,0.2);
    backdrop-filter: blur(15px);
    border-radius: 25px;
    box-shadow: 0 10px 40px rgba(0,0,0,0.2);
    color: white;
}

.emoji {
    font-size: 65px;
}

h1 {
    font-size: 30px;
    margin: 15px 0;
}

p {
    font-size: 17px;
}

button {
    border: none;
    padding: 14px 28px;
    border-radius: 30px;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
}

#yes {
    background: white;
    color: #ff4f81;
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

#no {
    background: #ff416c;
    color: white;
    position: fixed;
    transition: 0.15s;
}

#message {
    margin-top: 25px;
    font-size: 22px;
}
</style>
</head>

<body>

<!-- Hearts -->
<div class="heart" style="left:10%; animation-delay:0s;">❤️</div>
<div class="heart" style="left:30%; animation-delay:2s;">💕</div>
<div class="heart" style="left:50%; animation-delay:1s;">❤️</div>
<div class="heart" style="left:70%; animation-delay:3s;">💗</div>
<div class="heart" style="left:90%; animation-delay:1.5s;">💖</div>

<div class="card">

    <div class="emoji">🥰</div>

    <h1>Do You Love Me? ❤️</h1>

    <p>Be honest... 😏</p>

    <button id="yes" onclick="yesClicked()">
        Yes ❤️
    </button>

    <button id="no">
        No 😜
    </button>

    <div id="message"></div>

</div>

<script>

const noButton = document.getElementById("no");

function moveButton() {

    const maxX = window.innerWidth - noButton.offsetWidth - 10;
    const maxY = window.innerHeight - noButton.offsetHeight - 10;

    const x = Math.random() * maxX;
    const y = Math.random() * maxY;

    noButton.style.left = x + "px";
    noButton.style.top = y + "px";
}

/* Computer */
noButton.addEventListener("mouseover", moveButton);

/* Mobile */
noButton.addEventListener("touchstart", function(event) {
    event.preventDefault();
    moveButton();
});

function yesClicked() {

    document.getElementById("message").innerHTML =
        "Yayyy! ❤️🥰 I knew it! 💕";

    noButton.style.display = "none";
}

</script>

</body>
</html>
