# Index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Always Us ♾️</title>

<style>
html, body {
  margin: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  font-family: 'Segoe UI', sans-serif;
}

/* BACKGROUND */
body {
  background: linear-gradient(135deg, #ff7aa2, #c77dff, #ff9ecd);
}

/* COMMON */
.section {
  position: absolute;
  width: 100%;
  height: 100%;
  display: none;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 30px;
}

.section.active {
  display: flex;
}

/* CARD */
.card {
  background: linear-gradient(180deg, #ff5c8a, #ff87ab);
  padding: 35px;
  border-radius: 30px;
  box-shadow: 0 30px 70px rgba(90, 0, 60, 0.4);
  max-width: 380px;
  color: #3a001e;
}

/* TEXT */
h1 {
  font-size: 28px;
  margin-bottom: 10px;
  color: #4a0026;
}

.name {
  font-size: 32px;
  font-weight: bold;
  color: #6a0038;
  text-shadow: 0 0 12px rgba(255, 150, 200, 0.9);
}

p {
  font-size: 17px;
  line-height: 1.6;
}

/* BUTTON */
button {
  margin-top: 22px;
  padding: 12px 28px;
  border: none;
  border-radius: 40px;
  background: linear-gradient(135deg, #ff4d6d, #d63384);
  color: #2b0015;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 12px 30px rgba(255, 77, 109, 0.5);
}

button:hover {
  transform: scale(1.08);
}

/* FLOATING HEARTS */
.heart {
  position: absolute;
  font-size: 20px;
  animation: floatUp linear infinite;
  opacity: 0.7;
}

@keyframes floatUp {
  from { transform: translateY(110vh); }
  to { transform: translateY(-10vh); }
}

/* COUNTER */
.counter {
  margin-top: 15px;
  font-size: 16px;
  font-weight: 600;
  color: #4a0026;
}
</style>
</head>

<body>

<!-- 🎵 MUSIC (replace link if you want) -->
<audio id="bgMusic" loop>
  <source src="https://files.freemusicarchive.org/storage-freemusicarchive-org/music/no_curator/Keys_of_Moon/Emotional/Keys_of_Moon_-_Eternity.mp3" type="audio/mpeg">
</audio>

<!-- 🌸 SECTION 1 -->
<div class="section active" id="page1">
  <div class="card">
    <h1>Hey</h1>
    <div class="name">kishuuu💗</div>
    <p>
      This isn’t a beginning.<br>
      We already have that.<br><br>
      This is me asking you something softer…<br>
      something that lasts.
    </p>
    <button onclick="nextPage(2)">Continue 💞</button>
  </div>
</div>

<!-- ♾️ SECTION 2 -->
<div class="section" id="page2">
  <div class="card">
    <h1>Us, Forever</h1>
    <p>
      Not just today.<br>
      Not just when it’s easy.<br><br>
      But in every version of life,<br>
      in every tomorrow.
    </p>
    <div class="counter" id="foreverCounter"></div>
    <button onclick="nextPage(3)">One More Thing ♾️</button>
  </div>
</div>

<!-- 💖 SECTION 3 -->
<div class="section" id="page3">
  <div class="card">
    <h1>I Choose You</h1>
    <p>
      Calm days.<br>
      Messy days.<br>
      Quiet love.<br><br>
      I choose you.<br>
      Again and again.
    </p>
    <button onclick="nextPage(4)">Always 💗</button>
  </div>
</div>

<!-- 🌸 SECTION 4 -->
<div class="section" id="page4">
  <div class="card">
    <h1>Always Us ♾️</h1>
    <p>
      No pressure.<br>
      No promises forced.<br><br>
      Just two people,<br>
      choosing each other… forever.
    </p>
  </div>
</div>

<script>
// 🎵 Start music on first tap
document.body.addEventListener("click", () => {
  document.getElementById("bgMusic").play();
}, { once: true });

// Page navigation
function nextPage(n) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.getElementById('page' + n).classList.add('active');
}

// ♾️ FOREVER COUNTER (CHANGE DATE HERE)
const startDate = new Date("2024-07-23"); // <- put YOUR date
setInterval(() => {
  const now = new Date();
  const diff = now - startDate;

  const days = Math.floor(diff / (1000 * 60 * 60 * 24));
  const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
  const minutes = Math.floor((diff / (1000 * 60)) % 60);

  document.getElementById("foreverCounter").innerText =
    `Together for ${days} days, ${hours} hours, ${minutes} minutes ♾️`;
}, 1000);

// Floating hearts
for (let i = 0; i < 40; i++) {
  const h = document.createElement("div");
  h.className = "heart";
  h.innerHTML = "💗";
  h.style.left = Math.random() * 100 + "vw";
  h.style.animationDuration = (6 + Math.random() * 6) + "s";
  document.body.appendChild(h);
}
</script>

</body>

</html>
