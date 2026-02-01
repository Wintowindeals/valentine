# valentine
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine Surprise 💖</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        font-family: 'Arial', sans-serif;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
    }

    .screen {
        display: none;
        text-align: center;
        width: 100%;
        height: 100%;
    }

    .active {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    h1 {
        color: #fff;
        margin-bottom: 30px;
        text-shadow: 1px 1px 4px rgba(0,0,0,0.3);
    }

    button {
        padding: 14px 28px;
        font-size: 18px;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        transition: 0.3s;
    }

    .start-btn {
        background: #ff4d6d;
        color: white;
    }

    .start-btn:hover {
        transform: scale(1.1);
    }

    .yes-btn {
        background: hotpink;
        color: white;
        margin-right: 20px;
    }

    .no-btn {
        background: #eee;
        color: #333;
        position: absolute;
    }

    .buttons {
        position: relative;
        width: 300px;
        height: 200px;
    }

    .final-msg {
        font-size: 24px;
        color: white;
        margin-top: 20px;
    }
</style>
</head>

<body>

<!-- Screen 1 -->
<div class="screen active" id="startScreen">
    <h1>Hey 👀💖</h1>
    <button class="start-btn" onclick="goToValentine()">Click Here 💌</button>
</div>

<!-- Screen 2 -->
<div class="screen" id="valentineScreen">
    <h1>Gouthami 💕<br>Will you be my Valentine? 💘</h1>

    <div class="buttons">
        <button class="yes-btn" onclick="yesClicked()">YES 💖</button>
        <button class="no-btn" id="noBtn">NO 🙈</button>
    </div>

    <div class="final-msg" id="finalMsg"></div>
</div>

<script>
    function goToValentine() {
        document.getElementById("startScreen").classList.remove("active");
        document.getElementById("valentineScreen").classList.add("active");
    }

    const noBtn = document.getElementById("noBtn");

    noBtn.addEventListener("mouseover", moveNoButton);
    noBtn.addEventListener("click", moveNoButton);

    function moveNoButton() {
        const x = Math.random() * 200;
        const y = Math.random() * 120;
        noBtn.style.left = x + "px";
        noBtn.style.top = y + "px";
    }

    function yesClicked() {
        document.getElementById("finalMsg").innerHTML =
            "Yayyy 😍💖<br>You just made my day! 🌹";
    }
</script>

</body>
</html>
