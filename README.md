<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Be My Valentine 💖</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 30px 40px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 15px 30px rgba(0,0,0,0.2);
    }

    h1 {
      color: #ff4d6d;
      margin-bottom: 10px;
    }

    p {
      font-size: 18px;
      color: #555;
    }

    .buttons {
      margin-top: 25px;
      position: relative;
      height: 60px;
    }

    button {
      padding: 12px 25px;
      font-size: 16px;
      border-radius: 30px;
      border: none;
      cursor: pointer;
      transition: 0.3s;
    }

    #yesBtn {
      background-color: #ff4d6d;
      color: white;
    }

    #yesBtn:hover {
      background-color: #ff1e4d;
      transform: scale(1.1);
    }

    #noBtn {
      background-color: #ccc;
      position: absolute;
    }

    .hearts {
      position: fixed;
      font-size: 24px;
      animation: float 4s linear infinite;
    }

    @keyframes float {
      0% {
        transform: translateY(0);
        opacity: 1;
      }
      100% {
        transform: translateY(-600px);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Hey Beautiful 💕</h1>
    <p>
      I was going to write you a long love letter…<br>
      but I decided to code instead 😌💻<br><br>
      Will you be my Valentine?
    </p>

    <div class="buttons">
      <button id="yesBtn" onclick="sayYes()">YES 💖</button>
      <button id="noBtn" onmouseover="moveNo()">No 🙃</button>
    </div>
  </div>

  <script>
    function moveNo() {
      const noBtn = document.getElementById("noBtn");
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 80 - 40;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    }

    function sayYes() {
      document.body.innerHTML = `
        <div style="
          text-align:center;
          color:white;
          font-family:'Comic Sans MS', cursive;
        ">
          <h1>You just made me the happiest person ever 💘</h1>
          <p style="font-size:20px;">
            Valentine secured 🥰<br>
            I love you more than bugs hate my code 🐛❤️
          </p>
        </div>
      `;

      for (let i = 0; i < 30; i++) {
        createHeart();
      }
    }

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "hearts";
      heart.innerHTML = "💖";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.bottom = "0px";
      heart.style.animationDuration = Math.random() * 2 + 3 + "s";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }
  </script>

</body>
</html>
