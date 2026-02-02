<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Giselle, My Valentine 💘</title>
<style>
  body {
    margin:0;
    padding:40px 0;
    font-family: Arial, sans-serif;
    text-align: center;
    background: linear-gradient(135deg, #ffdde1, #ee9ca7);
    overflow: hidden;
  }

  #musicHint {
    font-size:14px;
    color:#888;
    margin-bottom:10px;
  }

  #imageContainer img {
    width: 320px;
    border-radius:15px;
    animation: dance 1.5s infinite ease-in-out;
  }

  @keyframes dance {
    0%,100% { transform: translateY(0) rotate(-5deg);}
    50% { transform: translateY(-15px) rotate(5deg);}
  }

  h1 {
    font-size: 32px;
    margin-top:20px;
    animation: glow 2s infinite;
    position: relative;
    display:inline-block;
  }

  @keyframes glow {
    0%,100% { color:#ff4d6d; }
    50% { color:#ffb6c1; }
  }

  .buttons { margin-top:25px; }
  button {
    font-size:18px;
    padding:12px 20px;
    margin:8px;
    border:none;
    border-radius:8px;
    cursor:pointer;
    transition:all 0.3s ease;
  }

  #yesBtn { background-color:#4caf50;color:white; }
  #noBtn { background-color:#f44336;color:white; position:relative; }

  .heart {
    position: fixed;
    bottom: -20px;
    font-size: 24px;
    animation: floatHeart 6s linear forwards;
    pointer-events: none;
  }

  @keyframes floatHeart {
    0% { transform: translateY(0) rotate(0deg); opacity:1; }
    100% { transform: translateY(-100vh) rotate(360deg); opacity:0; }
  }

  .nameHeart {
    position:absolute;
    font-size:20px;
    pointer-events:none;
    animation: floatHeart 4s linear forwards;
  }
</style>
</head>
<body>

<div id="musicHint">🔊 Tap anywhere to start romantic music</div>

<div id="imageContainer">
  <img src="https://i.imgur.com/fRFGGZw.gif" alt="Minion holding flowers">
</div>

<h1 id="question">Will you be my Valentine, Giselle? 💘</h1>

<div class="buttons">
  <button id="yesBtn" onclick="celebrate()">Yes 💖</button>
  <button id="noBtn" onclick="shrinkNo()">No 💔</button>
</div>

<!-- Hidden YouTube player for Tangerine (feat. d4vd) -->
<iframe
  width="0"
  height="0"
  src="https://www.youtube.com/embed/ReRm0OjnHFQ?autoplay=1&loop=1&playlist=ReRm0OjnHFQ"
  frameborder="0"
  allow="autoplay; encrypted-media"
  allowfullscreen
  style="display:none;">
</iframe>

<script>
let yesSize = 18;
const messages = [
  "Are you sure, Giselle? 🥺",
  "Really really sure?? 💕",
  "C’mon Giselle 😍",
  "Don’t break my heart 💔",
  "You know you want to say yes 💖"
];
let index = 0;

// Start music on tap (mobile friendly)
document.body.addEventListener("click", () => {
  document.getElementById("musicHint").style.display = "none";
});

// Move No button randomly and grow Yes button
function shrinkNo() {
  const yesBtn = document.getElementById("yesBtn");
  const noBtn = document.getElementById("noBtn");
  const question = document.getElementById("question");

  yesSize += 12;
  yesBtn.style.fontSize = yesSize + "px";
  yesBtn.style.padding = "20px 40px";

  noBtn.style.position = "absolute";
  noBtn.style.left = Math.random() * (window.innerWidth - 120) + "px";
  noBtn.style.top = Math.random() * (window.innerHeight - 60) + "px";

  if (index < messages.length) {
    question.innerText = messages[index];
    index++;
  }
}

// Celebrate Yes
function celebrate() {
  document.body.innerHTML = `
    <div style="text-align:center;">
      <h1 style="font-size:50px;color:#ff4d6d;">YAYYYY Giselle! 💘</h1>
      <p style="font-size:24px;">You just made me the happiest person alive 💕</p>
      <div style="font-size:60px;">💐💖💐</div>
    </div>
  `;
  setInterval(createHeart, 300);
  setInterval(createNameHeart, 500);
}

// Create floating heart confetti
function createHeart() {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerText = "❤️";
  heart.style.left = Math.random() * window.innerWidth + "px";
  document.body.appendChild(heart);
  setTimeout(() => heart.remove(), 6000);
}

// Hearts floating in her name
function createNameHeart() {
  const heart = document.createElement("div");
  heart.className = "nameHeart";
  heart.innerText = "❤️";
  const question = document.getElementById("question");
  const rect = question.getBoundingClientRect();
  heart.style.left = rect.left + Math.random() * rect.width + "px";
  heart.style.top = rect.top + "px";
  document.body.appendChild(heart);
  setTimeout(() => heart.remove(), 4000);
}

// Start initial hearts
for(let i=0;i<20;i++) setTimeout(createHeart, i*200);
</script>

</body>
</html>
