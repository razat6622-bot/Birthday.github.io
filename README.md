<!DOCTYPE html>
<html>
<head>
<title>Happy Birthday SAIQA 💖</title>

<style>
body {
  margin:0;
  background:black;
  color:white;
  text-align:center;
  font-family: Arial;
  overflow:hidden;
}

h1 {
  margin-top: 50px;
  font-size: 45px;
  color: pink;
  text-shadow: 0 0 20px red;
}

#msg {
  font-size: 22px;
  margin-top: 20px;
  min-height: 40px;
}

button {
  padding: 15px 25px;
  margin: 10px;
  border: none;
  border-radius: 10px;
  font-size: 18px;
  cursor: pointer;
}

.balloon, .heart {
  position: absolute;
}

.balloon {
  width: 50px;
  height: 70px;
  border-radius: 50%;
  animation: float 6s infinite;
}

@keyframes float {
  from { bottom: -100px; }
  to { bottom: 100%; }
}

.heart {
  font-size: 20px;
  animation: fall 5s linear infinite;
}

@keyframes fall {
  from { top: -50px; }
  to { top: 100%; }
}

#cake {
  display:none;
  font-size:80px;
}

canvas {
  position: fixed;
  top:0;
  left:0;
}
</style>
</head>

<body>

<h1>🎂 Happy Birthday SAIQA 💖</h1>
<div id="msg"></div>

<button onclick="start()">Start Surprise 🎉</button>
<button onclick="cutCake()">Cut Cake 🎂</button>

<div id="cake">🎂</div>

<audio id="music" src="https://www2.cs.uic.edu/~i101/SoundFiles/HappyBirthday.wav"></audio>
<canvas id="fire"></canvas>

<script>
// typing romantic message
let text = "SAIQA... 💖\nYou are not just special...\nYou are the reason I smile everyday 😊\nI am lucky to have you ❤️";
let i = 0;

function type(){
  if(i < text.length){
    document.getElementById("msg").innerHTML += text.charAt(i);
    i++;
    setTimeout(type, 50);
  }
}

// start animation
function start(){
  document.getElementById("music").play();
  type();

  for(let i=0;i<25;i++){
    let b=document.createElement("div");
    b.className="balloon";
    b.style.left=Math.random()*100+"vw";
    b.style.background="hsl("+Math.random()*360+",100%,50%)";
    document.body.appendChild(b);
  }

  for(let i=0;i<25;i++){
    let h=document.createElement("div");
    h.className="heart";
    h.innerHTML="❤️";
    h.style.left=Math.random()*100+"vw";
    document.body.appendChild(h);
  }
}

// cake + fireworks
function cutCake(){
  document.getElementById("cake").style.display="block";
  fireworks();
  alert("🎉 Happy Birthday SAIQA 💖\nYou mean a lot to me ❤️🎁");
}

// fireworks
function fireworks(){
  let c=document.getElementById("fire");
  let ctx=c.getContext("2d");
  c.width=window.innerWidth;
  c.height=window.innerHeight;

  for(let i=0;i<100;i++){
    ctx.fillStyle="hsl("+Math.random()*360+",100%,50%)";
    ctx.beginPath();
    ctx.arc(Math.random()*c.width,Math.random()*c.height,3,0,Math.PI*2);
    ctx.fill();
  }
}
</script>

</body>
</html>
