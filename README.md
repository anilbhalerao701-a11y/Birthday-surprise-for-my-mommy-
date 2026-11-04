
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday ❤️</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  min-height: 100vh;
  background: linear-gradient(135deg, #200b32, #691b68, #d94d91);
  color: white;
  font-family: Georgia, serif;
  overflow-x: hidden;
  text-align: center;
}

.container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 25px 16px;
}

h1 {
  color: #ffd6ed;
  font-size: 2.5rem;
  text-shadow: 0 0 20px #ff70bd;
  animation: glow 2s infinite alternate;
}

.subtitle {
  margin: 15px;
  color: #ffe2f2;
}

@keyframes glow {
  from { text-shadow: 0 0 8px #ff83c5; }
  to { text-shadow: 0 0 30px #ffb2de; }
}

.envelope {
  font-size: 95px;
  margin: 25px;
  cursor: pointer;
  animation: bounce 2s infinite;
  filter: drop-shadow(0 0 15px #ff8bc8);
}

@keyframes bounce {
  50% { transform: translateY(-12px); }
}

button {
  border: none;
  padding: 14px 25px;
  border-radius: 30px;
  background: #ff9acb;
  color: #4a1240;
  font-size: 17px;
  cursor: pointer;
  box-shadow: 0 0 18px #ff8bc8;
}

.letter {
  display: none;
  width: 100%;
  max-width: 520px;
  margin-top: 25px;
  padding: 25px;
  border-radius: 20px;
  background: rgba(255,255,255,0.94);
  color: #78275b;
  text-align: left;
  line-height: 1.9;
  box-shadow: 0 0 35px #ffb5df;
  animation: appear 1s ease;
}

.letter.show {
  display: block;
}

@keyframes appear {
  from { opacity: 0; transform: translateY(30px) scale(.9); }
  to { opacity: 1; transform: translateY(0) scale(1); }
}

.signature {
  text-align: center;
  margin-top: 20px;
  font-weight: bold;
}

.heart {
  position: fixed;
  bottom: -30px;
  pointer-events: none;
  animation: floatUp 7s linear forwards;
  z-index: 5;
}

@keyframes floatUp {
  to {
    transform: translateY(-110vh) rotate(360deg);
    opacity: 0;
  }
}

.sparkle {
  position: fixed;
  pointer-events: none;
  color: #fff0a8;
  animation: twinkle 2s infinite alternate;
}

@keyframes twinkle {
  from { opacity: .2; transform: scale(.6); }
  to { opacity: 1; transform: scale(1.3); }
}

.music {
  margin-top: 20px;
  background: #ffe0ef;
}
</style>
</head>

<body>

<div class="container">

  <h1>Happy Birthday! 🎂</h1>

  <p class="subtitle">
    A little surprise made just for you 💗
  </p>

  <div class="envelope" onclick="openLetter()">💌</div>

  <button onclick="openLetter()">
    Open Your Birthday Letter 💝
  </button>

  <div class="letter" id="letter">

    <p>heyy i know you're soo happy for today and I was soo excited for your birthday and it's hear wishing you a very very happy birthday. Be happy, beautiful and hot baddie 😁 I want to be there but it's ok. I know it's not perfect but and I am sorry for making you sad angry and uncomfortable but I was like I dont want to make something like that sooo i really sorry about that and just be my friend💝 and um injoy your birthday injoy your life</p>

    <div class="signature">
      <p>Love from me ❣️</p>
      <br>
      <p>I LOVE YOU 💞🎀♥️💌</p>
    </div>

  </div>

  <button class="music" onclick="toggleMusic()" id="musicButton">
    🎵 Play Music
  </button>

  <audio id="bgMusic" loop>
    <source src="song.mp3" type="audio/mpeg">
  </audio>

</div>

<script>
function openLetter() {
  document.getElementById("letter").classList.add("show");
  createHearts();
}

function toggleMusic() {
  const music = document.getElementById("bgMusic");
  const button = document.getElementById("musicButton");

  if (music.paused) {
    music.play().then(() => {
      button.innerHTML = "⏸ Pause Music";
    }).catch(() => {
      alert("Please upload song.mp3 to your GitHub repository.");
    });
  } else {
    music.pause();
    button.innerHTML = "🎵 Play Music";
  }
}

function createHearts() {
  for (let i = 0; i < 25; i++) {
    setTimeout(() => {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = ["💗","💕","💖","❤️","💝"][
        Math.floor(Math.random() * 5)
      ];
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = (15 + Math.random() * 25) + "px";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 7000);
    }, i * 120);
  }
}

setInterval(() => {
  const sparkle = document.createElement("div");
  sparkle.className = "sparkle";
  sparkle.innerHTML = "✦";
  sparkle.style.left = Math.random() * 100 + "vw";
  sparkle.style.top = Math.random() * 100 + "vh";
  sparkle.style.fontSize = (10 + Math.random() * 15) + "px";
  document.body.appendChild(sparkle);
  setTimeout(() => sparkle.remove(), 2500);
}, 350);
</script>

</body>
</html>
