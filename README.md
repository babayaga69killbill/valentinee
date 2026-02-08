# valentinee
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>My Love 💖</title>

<style>
body {
  margin:0;
  font-family: 'Segoe UI', sans-serif;
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
  overflow:hidden;
}

.card {
  background:white;
  width:90%;
  max-width:420px;
  padding:25px;
  border-radius:20px;
  text-align:center;
  box-shadow:0 20px 40px rgba(0,0,0,0.2);
  z-index:2;
}

h1 { color:#ff2f68; }

.names {
  font-size:22px;
  font-weight:bold;
  color:#ff2f68;
  margin-bottom:10px;
}

img {
  width:100%;
  border-radius:15px;
  margin:10px 0;
}

#message {
  min-height:100px;
  font-size:16px;
  color:#333;
}

button {
  padding:12px 22px;
  border:none;
  border-radius:25px;
  font-size:15px;
  cursor:pointer;
  margin:10px;
}

#yes {
  background:#ff2f68;
  color:white;
}

#no {
  background:#ccc;
}

.qr {
  margin-top:15px;
}

.qr img {
  width:140px;
}

.hearts span {
  position:fixed;
  bottom:-10px;
  font-size:20px;
  animation:float 6s linear infinite;
}

@keyframes float {
  from { transform:translateY(0); opacity:1; }
  to { transform:translateY(-100vh); opacity:0; }
}
</style>
</head>

<body>

<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<div class="card">
  <h1>Happy Valentine’s Day 💘</h1>
  <div class="names">Priyanshu ❤️ Chashmishhh</div>

  <img src="https://i.imgur.com/6Xg7K5F.jpg">

  <div id="message"></div>

  <button id="yes" onclick="yesClick()">Yes 😍</button>
  <button id="no" onmouseover="moveNo()">No 🙈</button>

  <div class="qr">
    <p>Scan this 💌</p>
    <img id="qrImg">
  </div>
</div>

<div class="hearts" id="hearts"></div>

<script>
const text = `Chashmishhh ❤️  
From the first time I saw you, my heart chose you without asking me.  
Every smile of yours makes my world brighter.  
I don't want a perfect life, I just want you in my life.  

Will you be mine forever? 💍💖`;

let i = 0;
function typeWriter() {
  if (i < text.length) {
    document.getElementById("message").innerHTML += text.charAt(i);
    i++;
    setTimeout(typeWriter, 50);
  }
}
typeWriter();

function yesClick() {
  alert("She said YES 😭💖 This is the best moment of my life!");
}

function moveNo() {
  const btn = document.getElementById("no");
  btn.style.position = "absolute";
  btn.style.left = Math.random()*80 + "vw";
  btn.style.top = Math.random()*80 + "vh";
}

// Floating hearts
setInterval(() => {
  const span = document.createElement("span");
  span.innerHTML = ["❤️","💖","💕","💘"][Math.floor(Math.random()*4)];
  span.style.left = Math.random()*100 + "vw";
  document.getElementById("hearts").appendChild(span);
  setTimeout(()=>span.remove(),6000);
},300);

// QR generator
const siteLink = "https://yourwebsite.netlify.app"; // PUT YOUR REAL LINK HERE
document.getElementById("qrImg").src =
  "https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=" + siteLink;
</script>

</body>
</html>
