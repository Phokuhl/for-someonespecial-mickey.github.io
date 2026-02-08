<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Be My Valentine ❤️</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
  margin: 0;
  height: 100vh;
  background: 
    linear-gradient(rgba(0,0,0,0.45), rgba(0,0,0,0.45)),
    url('Mickey.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  color: #fff;
}

    .card {
  position: relative;
  border-radius: 20px;
  padding: 40px;
  max-width: 420px;
  text-align: center;
  color: #fff;
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(0,0,0,0.3);
}

   .card::before {
  content: "";
  position: absolute;
  inset: 0;
  background: 
    linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
    url('Mickey1.jpg');
  background-size: cover;
  background-position: center;
  filter: blur(0px);
  transform: scale(1.1); /* prevents edge blur cuts */
  z-index: -1;
}

    .card * {
  position: relative;
  z-index: 1;
}
    h1 {
      font-size: 2.4rem;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.1rem;
      margin-bottom: 30px;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
    }

    button {
      padding: 12px 24px;
      border-radius: 30px;
      border: none;
      font-size: 1rem;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .yes {
      background: #fff;
      color: #ff4f7b;
      font-weight: bold;
    }

    .yes:hover {
      transform: scale(1.1);
    }

    .no {
      background: transparent;
      border: 2px solid #fff;
      color: #fff;
      position: relative;
    }

    .hearts {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }

    .heart {
      position: absolute;
      color: rgba(255,255,255,0.8);
      animation: float 6s infinite;
    }

    @keyframes float {
      0% { transform: translateY(100vh) scale(0.5); opacity: 0; }
      20% { opacity: 1; }
      100% { transform: translateY(-10vh) scale(1.2); opacity: 0; }
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .message {
      margin-top: 25px;
      font-size: 1.3rem;
      display: none;
      animation: fadeIn 1s ease;
    }
  </style>
</head>
<body>
  <div class="hearts" id="hearts"></div>

  <div class="card">
    <h1>Heyy Mickey 💕</h1>
    <p>Every moment I spend with you feels special, and I can’t imagine a day without you, especially Valentine’s Day.</p>
    <p>With that being said</p>
    <h2>Will you be my Valentine? 🥹💖</h2>

    <div class="buttons">
      <button class="yes" onclick="sayYes()">Yes 💘</button>
      <button class="no" onmouseover="moveNo(this)">No 🙈</button>
    </div>

    <div class="message" id="message">
      You just made my heart so happy ❤️ now I can die happy😭
      <br />I can’t wait to spend Valentine’s with you 💐 I love you🖤
    </div>
  </div>

  <script>
    function sayYes() {
      document.getElementById('message').style.display = 'block';
      createHearts();
    }

    function moveNo(btn) {
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 200 - 100;
      btn.style.transform = `translate(${x}px, ${y}px)`;
    }

    function createHearts() {
      const heartsContainer = document.getElementById('hearts');
      for (let i = 0; i < 30; i++) {
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.innerHTML = '❤️';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDelay = Math.random() * 5 + 's';
        heart.style.fontSize = Math.random() * 20 + 15 + 'px';
        heartsContainer.appendChild(heart);
      }
    }
  </script>
</body>
</html>
