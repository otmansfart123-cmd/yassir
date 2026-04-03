<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Hajar Football Game ⚽</title>
  <meta name="description" content="Interactive football website with Messi vs Buffon mini game ⚽🔥">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      background: linear-gradient(to right, #0f172a, #020617);
      color: white;
      font-family: Arial;
      text-align: center;
    }

    h1 {
      color: #22c55e;
      font-size: 45px;
    }

    p {
      width: 80%;
      margin: auto;
      font-size: 18px;
      line-height: 1.6;
    }

    iframe {
      margin-top: 20px;
      border-radius: 15px;
    }

    /* 🎮 Game */
    #game {
      position: relative;
      width: 400px;
      height: 200px;
      margin: 40px auto;
      background: green;
      border: 3px solid white;
      overflow: hidden;
    }

    #ball {
      position: absolute;
      bottom: 10px;
      left: 20px;
      font-size: 30px;
    }

    #goalkeeper {
      position: absolute;
      top: 20px;
      left: 150px;
      font-size: 30px;
      transition: left 0.3s;
    }

    button {
      padding: 12px 25px;
      background: #22c55e;
      border: none;
      color: black;
      font-size: 18px;
      cursor: pointer;
      border-radius: 10px;
    }
  </style>
</head>

<body>

<h1>Hajar Football Game ⚽🔥</h1>

<p>
Football is the most popular sport in the world. It connects millions of fans across different countries. 
Legendary players like Messi have amazed the world with their talent, while goalkeepers like Buffon have protected the goal with incredible saves.
This project is an interactive football website where you can watch, learn and play a mini game!
</p>

<!-- 🎥 فيديو -->
<iframe width="560" height="315"
src="https://www.youtube.com/embed/aqz-KE-bpKQ"
allowfullscreen>
</iframe>

<!-- 🎮 GAME -->
<div id="game">
  <div id="ball">⚽</div>
  <div id="goalkeeper">🧤</div>
</div>

<button onclick="shoot()">Shoot ⚽</button>

<p id="result"></p>

<script>
function shoot() {
  let ball = document.getElementById("ball");
  let keeper = document.getElementById("goalkeeper");
  let result = document.getElementById("result");

  // حركة الحارس
  let randomPos = Math.random() * 300;
  keeper.style.left = randomPos + "px";

  // حركة الكرة
  ball.style.left = "180px";

  setTimeout(() => {
    if (Math.abs(randomPos - 180) < 50) {
      result.innerHTML = "Buffon SAVES 🧤❌";
    } else {
      result.innerHTML = "GOAL by Messi ⚽🔥";
    }

    // رجوع الكرة
    ball.style.left = "20px";
  }, 500);
}
</script>

</body>
</html>
