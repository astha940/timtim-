
index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Be My Valentine 💕</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ffe4ec, #ff6b81);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Comic Sans MS', cursive;
  overflow: hidden;
}

.card {
  background: #fff0f5;
  padding: 30px;
  border-radius: 25px;
  text-align: center;
  width: 330px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.3);
  position: relative;
  z-index: 2;
}

h1 {
  color: #ff3366;
}

p {
  color: #ff4d6d;
  font-size: 18px;
  line-height: 1.5;
}

button {
  padding: 12px 25px;
  margin: 10px;
  border: none;
  border-radius: 20px;
  font-size: 16px;
  cursor: pointer;
}

.yes {
  background: #ff4d6d;
  color: white;
}

.no {
  background: #ffd1dc;
  color: #ff3366;
  position: absolute;
}

#message {
  margin-top: 15px;
  font-size: 20px;
  color: #ff3366;
}

/* Floating hearts animation */
.heart {
  position: absolute;
  font-size: 20px;
  animation: float 6s linear infinite;
}

@keyframes float {
  0% {
    transform: translateY(100vh) scale(0.6);
    opacity: 1;
  }
  100% {
    transform: translateY(-10vh) scale(1.3);
    opacity: 0;
  }
}
</style>
</head>

<body>

<div class="card">
  <h1>Hey Baby 💕</h1>

  <p>
    Baby, will you be my Valentine? 💖🌹
  </p>

  <button class="yes" onclick="yesClicked()">Yes 💘</button>
  <button class="no" id="noBtn">No 🙈</button>

  <div id="message"></div>
</div>

<script>
function yesClicked() {
  document.getElementById("message").innerHTML =
    "I love you so much baby 🥰❤️<br>Thank you for being there for me 💖";
}

// Runaway NO button
const noBtn = document.getElementById("noBtn");
noBtn.addEventListener("mouseover", () => {
  const x = Math.random() * 200 - 100;
  const y = Math.random() * 150 - 75;
  noBtn.style.transform = `translate(${x}px, ${y}px)`;
});

// Floating hearts
setInterval(() => {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = ["❤️","💖","💘","💝"][Math.floor(Math.random() * 4)];
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = Math.random() * 20 + 15 + "px";
  document.body.appendChild(heart);

  setTimeout(() => heart.remove(), 6000);
}, 400);
</script>

</body>
</html>
