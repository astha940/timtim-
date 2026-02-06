
index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Forever Valentine 💖</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ffd1dc, #ff4d6d);
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
  width: 340px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.3);
  z-index: 2;
}

h1 {
  color: #ff3366;
  font-size: 22px;
}

p {
  color: #ff4d6d;
  font-size: 17px;
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

#result {
  margin-top: 15px;
  font-size: 20px;
  color: #ff3366;
}

/* Floating hearts */
.heart {
  position: absolute;
  font-size: 22px;
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
    Baby, will you be my Valentine forever? 💖<br><br>
    I love you so much ❤️<br>
    I can’t imagine my life without you 🥹💞<br><br>
    Thank you for being there for me 🌹✨
  </p>

  <button class="yes" onclick="yesClicked()">Yes, forever 💍💖</button>

  <div id="result"></div>
</div>

<script>
function yesClicked() {
  document.getElementById("result").innerHTML =
    "You are my forever and always 🥰❤️";
}

// Floating hearts
setInterval(() => {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = ["💖","💘","❤️","💝"][Math.floor(Math.random()*4)];
  heart.style.left = Math.random() * 100 + "vw";
  document.body.appendChild(heart);

  setTimeout(() => heart.remove(), 6000);
}, 400);
</script>

</body>
</html>
