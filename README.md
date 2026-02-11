<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For You ❤️</title>
  <style>
    :root {
      --primary-red: #cc0000;
      --highlight-red: #ff8080;
    }

    body {
      margin: 0;
      background: radial-gradient(circle, #ffccd5, #ff4d6d);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      overflow: hidden;
    }

    /* Floating background hearts */
    .bg-heart {
      position: absolute;
      color: rgba(255, 255, 255, 0.4);
      font-size: 20px;
      animation: float 6s linear infinite;
      z-index: 0;
    }

    @keyframes float {
      0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
      100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
    }

    .container {
      position: relative;
      text-align: center;
      z-index: 1;
      animation: breathe 3s ease-in-out infinite;
    }

    .teddy {
      position: relative;
      width: 220px;
      height: 280px;
      margin: 0 auto;
    }

    .part {
      background: radial-gradient(circle at 35% 35%, var(--highlight-red), var(--primary-red));
      border-radius: 50%;
      position: absolute;
      box-shadow: inset -6px -10px 18px rgba(0,0,0,0.3),
                  inset 6px 8px 14px rgba(255,255,255,0.3),
                  0 10px 20px rgba(0,0,0,0.1);
    }

    /* Positioning */
    .head { width: 120px; height: 110px; top: 0; left: 50px; z-index: 3; }
    .ear-left { width: 45px; height: 45px; top: -10px; left: 35px; z-index: 2; }
    .ear-right { width: 45px; height: 45px; top: -10px; right: 35px; z-index: 2; }
    .body { width: 150px; height: 140px; bottom: 30px; left: 35px; border-radius: 50% 50% 45% 45%; z-index: 1; }
    .arm-left { width: 55px; height: 90px; top: 100px; left: 10px; border-radius: 50px; transform: rotate(20deg); z-index: 4; }
    .arm-right { width: 55px; height: 90px; top: 100px; right: 10px; border-radius: 50px; transform: rotate(-20deg); z-index: 4; }
    .leg-left { width: 75px; height: 75px; bottom: 0px; left: 25px; z-index: 2; }
    .leg-right { width: 75px; height: 75px; bottom: 0px; right: 25px; z-index: 2; }

    /* Face Details */
    .eye { position: absolute; top: 45px; width: 12px; height: 12px; background: #1a0000; border-radius: 50%; z-index: 5; }
    .eye-left { left: 30px; }
    .eye-right { right: 30px; }
    .eye::after { content: ''; position: absolute; width: 4px; height: 4px; background: white; border-radius: 50%; top: 2px; left: 2px; }

    .snout {
        position: absolute; width: 40px; height: 30px; background: #ffb3b3; 
        border-radius: 50%; top: 60px; left: 40px; z-index: 4;
    }
    .nose { position: absolute; top: 5px; left: 12px; width: 16px; height: 10px; background: #330000; border-radius: 50%; }

    .text {
      margin-top: 20px;
      font-size: 26px;
      color: white;
      font-weight: bold;
      text-shadow: 0 0 10px rgba(255,255,255,0.8);
      letter-spacing: 2px;
    }

    /* Animations */
    @keyframes breathe {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }

    @keyframes glow {
      from { text-shadow: 0 0 5px #fff, 0 0 10px #ff4d6d; }
      to { text-shadow: 0 0 15px #fff, 0 0 30px #ff4d6d; }
    }

    .text { animation: glow 1.5s infinite alternate; }
  </style>
</head>
<body>

  <script>
    for (let i = 0; i < 15; i++) {
      let heart = document.createElement('div');
      heart.className = 'bg-heart';
      heart.innerHTML = '❤️';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDelay = Math.random() * 5 + 's';
      heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
      document.body.appendChild(heart);
    }
  </script>

  <div class="container">
    <div class="teddy">
      <div class="part ear-left"></div>
      <div class="part ear-right"></div>
      <div class="part head">
        <div class="eye eye-left"></div>
        <div class="eye eye-right"></div>
        <div class="snout">
            <div class="nose"></div>
        </div>
      </div>
      <div class="part arm-left"></div>
      <div class="part arm-right"></div>
      <div class="part body"></div>
      <div class="part leg-left"></div>
      <div class="part leg-right"></div>
    </div>
    <div class="text">I LOVE YOU ❤️</div>
  </div>

</body>
</html>




