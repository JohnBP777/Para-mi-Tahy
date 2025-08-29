<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Para mi Tahy 💖</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Dancing Script', cursive;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      overflow: hidden;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .screen {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      text-align: center;
      padding: 20px;
      transition: all 1s ease;
      color: #fff;
    }

    .screen.active {
      left: 0;
    }

    h1 {
      font-size: 2.5rem;
      margin-bottom: 20px;
      text-shadow: 2px 2px 6px rgba(0,0,0,0.3);
    }

    p {
      font-size: 1.5rem;
      margin-bottom: 20px;
      text-shadow: 1px 1px 4px rgba(0,0,0,0.2);
    }

    .btn {
      background: linear-gradient(135deg, #ff6a88, #ff99ac);
      border: none;
      padding: 12px 24px;
      border-radius: 30px;
      font-size: 1rem;
      color: white;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: transform 0.3s;
    }

    .btn:hover {
      transform: scale(1.05);
    }

    /* corazones */
    .hearts {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
      z-index: -1;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: pink;
      transform: rotate(45deg);
      animation: float 6s linear infinite;
    }

    .heart:before,
    .heart:after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: pink;
      border-radius: 50%;
    }

    .heart:before {
      top: -10px;
      left: 0;
    }
    .heart:after {
      left: -10px;
      top: 0;
    }

    @keyframes float {
      from {
        transform: translateY(100vh) rotate(45deg);
        opacity: 1;
      }
      to {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <div class="hearts"></div>

  <!-- Pantallas -->
  <div class="screen active">
    <h1>Para mi Tahy 💖</h1>
    <p>Aunque la distancia nos separe, mi corazón siempre está contigo.</p>
    <button class="btn" onclick="nextScreen()">Siguiente</button>
  </div>

  <div class="screen">
    <h1>Mi Amor 💌</h1>
    <p>Ni la distancia, ni el tiempo pueden apagar lo que siento por ti.</p>
    <button class="btn" onclick="nextScreen()">Siguiente</button>
  </div>

  <div class="screen">
    <h1>Recuerda 🌙</h1>
    <p>Cada noche pienso en ti, y eso me da fuerzas para seguir.</p>
    <button class="btn" onclick="nextScreen()">Siguiente</button>
  </div>

  <div class="screen">
    <h1>Siempre tú 💍</h1>
    <p>Un día la distancia será solo un recuerdo... y estaremos juntos para siempre.</p>
    <button class="btn" onclick="nextScreen()">Siguiente</button>
  </div>

  <div class="screen">
    <h1 style="font-size:3rem;">Siempre serás mi Tahy ❤️</h1>
    <p>Te amo más de lo que las palabras pueden decir.</p>
  </div>

  <script>
    let current = 0;
    const screens = document.querySelectorAll('.screen');

    function nextScreen() {
      screens[current].classList.remove('active');
      current++;
      if (current < screens.length) {
        screens[current].classList.add('active');
      }
    }

    // generar corazones
    const heartsContainer = document.querySelector('.hearts');
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (3 + Math.random() * 3) + "s";
      heartsContainer.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }
    setInterval(createHeart, 500);
  </script>
</body>
</html>

