<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Choose Your Path, Nandita 💖</title>
  <style>
    body {
      background: linear-gradient(to right, #ffdde1, #ee9ca7);
      font-family: 'Comic Sans MS', cursive, sans-serif;
      text-align: center;
      color: #fff;
      padding: 40px;
    }

    h1 {
      font-size: 36px;
      color: #fff;
      margin-bottom: 20px;
    }

    .question-box, .message {
      background-color: rgba(255, 192, 203, 0.9);
      border-radius: 20px;
      padding: 30px;
      margin: 20px auto;
      max-width: 600px;
      box-shadow: 0 0 15px rgba(255, 105, 180, 0.7);
    }

    .button {
      display: inline-block;
      margin: 10px;
      padding: 15px 30px;
      background-color: #ff69b4;
      color: white;
      border: none;
      border-radius: 30px;
      font-size: 18px;
      cursor: pointer;
      transition: 0.3s;
    }

    .button:hover {
      background-color: #ff1493;
    }

    .hearts {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }

    .heart {
      position: absolute;
      width: 30px;
      height: 30px;
      background: url('https://i.imgur.com/2cJbL48.png') no-repeat center/contain;
      animation: float 6s infinite;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) scale(0.5);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.2);
        opacity: 0;
      }
    }

    .love-meter {
      margin-top: 30px;
    }

    .meter-bar {
      width: 100%;
      background-color: #eee;
      border-radius: 20px;
      overflow: hidden;
      border: 2px solid #ff69b4;
      margin-top: 10px;
    }

    .meter-fill {
      height: 30px;
      width: 100%;
      background-color: #ff1493;
      animation: fillMeter 2s ease-out forwards;
    }

    @keyframes fillMeter {
      from { width: 0; }
      to { width: 100%; }
    }

    .final-message {
      font-size: 20px;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <h1>Choose Your Path, My Love 💘</h1>

  <div class="question-box" id="step1">
    <p>How do you feel when we hold hands?</p>
    <button class="button" onclick="showStep('step2')">Safe & Happy</button>
    <button class="button" onclick="showStep('step2')">Like the world stops</button>
  </div>

  <div class="question-box" id="step2" style="display:none;">
    <p>What kind of dates do you love the most?</p>
    <button class="button" onclick="showStep('step3')">Long walks & talks</button>
    <button class="button" onclick="showStep('step3')">Netflix & cuddles</button>
  </div>

  <div class="question-box" id="step3" style="display:none;">
    <p>If I wrote you a poem, what would you do?</p>
    <button class="button" onclick="showFinal()">Frame it forever</button>
    <button class="button" onclick="showFinal()">Kiss me instantly</button>
  </div>

  <div class="question-box message" id="final" style="display:none;">
    <h2>💌 Dear Nandita 💌</h2>
    <p>
      This is a cute little thing just for you.  
      I love you so much and I want you to continue being happy with me always.<br><br>
      Thanks for trusting me all these years.  
      You make my world brighter, softer, and more real every day.<br><br>
      Here's to many more beautiful chapters with you.<br><br>
      <strong>11:11</strong> ✨
    </p>

    <div class="love-meter">
      <p>Love Meter ❤️</p>
      <div class="meter-bar">
        <div class="meter-fill"></div>
      </div>
      <p>100%</p>
    </div>
  </div>

  <div class="hearts" id="hearts-container"></div>

  <script>
    function showStep(stepId) {
      document.querySelectorAll('.question-box').forEach(box => box.style.display = 'none');
      document.getElementById(stepId).style.display = 'block';
    }

    function showFinal() {
      document.querySelectorAll('.question-box').forEach(box => box.style.display = 'none');
      document.getElementById('final').style.display = 'block';
    }

    // Generate floating hearts
    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (4 + Math.random() * 3) + "s";
      document.getElementById("hearts-container").appendChild(heart);
      setTimeout(() => heart.remove(), 7000);
    }

    setInterval(createHeart, 300);
  </script>
</body>
</html>
