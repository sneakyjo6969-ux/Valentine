<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Neha, Be My Valentine ❤️</title>

<style>
body{
  margin:0;
  height:100vh;
  background:linear-gradient(rgba(0,0,0,.6),rgba(0,0,0,.85)),
  url('https://images.unsplash.com/photo-1518895312237-a6f9b7a1c0d3') center/cover no-repeat;
  font-family:'Segoe UI',cursive;
  display:flex;
  justify-content:center;
  align-items:center;
  overflow:hidden;
  color:white;
}

.box{
  text-align:center;
  background:rgba(255,0,100,.25);
  padding:50px;
  border-radius:30px;
  box-shadow:0 0 70px hotpink;
  animation:pulse 2s infinite alternate;
  z-index:2;
}

@keyframes pulse{
  from{box-shadow:0 0 30px pink;}
  to{box-shadow:0 0 80px hotpink;}
}

h1{
  font-size:3.8em;
  margin-bottom:10px;
}

.mal{
  font-style:italic;
  color:#ffd6e7;
  font-size:1.3em;
}

button{
  font-size:1.4em;
  padding:15px 45px;
  margin:15px;
  border:none;
  border-radius:40px;
  cursor:pointer;
  transition:.3s;
}

button:hover{transform:scale(1.1);}

.yes{
  background:#ff2f6d;
  color:white;
  box-shadow:0 0 20px pink;
}

.no{
  background:white;
  color:#ff2f6d;
  position:absolute;
}

.heart{
  position:absolute;
  font-size:26px;
  animation:float 6s linear infinite;
  color:pink;
}

@keyframes float{
  0%{transform:translateY(100vh);opacity:0;}
  10%{opacity:1;}
  100%{transform:translateY(-10vh);opacity:0;}
}

.typing{
  font-size:2em;
  border-right:3px solid white;
  white-space:nowrap;
  overflow:hidden;
}
</style>
</head>

<body>

<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<div class="box" id="box">
  <h1>Neha 💕</h1>
  <p>You are my favorite person, my comfort, my love.</p>
  <p class="mal">"Neha, ente hridayam ninakku vendi maathram aanu ❤️"</p>
  <h2>Will you be my Valentine? 🌹</h2>

  <button class="yes" onclick="yesClicked()">YES 💖</button>
  <button class="no" id="noBtn">NO 😜</button>
</div>

<script>
const noBtn=document.getElementById("noBtn");

noBtn.addEventListener("mouseover",()=>{
  noBtn.style.left=Math.random()*(window.innerWidth-150)+"px";
  noBtn.style.top=Math.random()*(window.innerHeight-80)+"px";
});

function createHeart(){
  const h=document.createElement("div");
  h.className="heart";
  h.innerHTML="💖";
  h.style.left=Math.random()*100+"vw";
  h.style.animationDuration=(3+Math.random()*4)+"s";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),7000);
}
setInterval(createHeart,250);

function yesClicked(){
  document.body.innerHTML=`
    <div style="text-align:center;">
      <div class="typing" id="type"></div>
    </div>
  `;
  typeText("She said YES!!! 💖💖💖",()=>{
    setTimeout(showFinal,800);
  });
}

function typeText(text,callback){
  let i=0;
  const el=document.getElementById("type");
  const timer=setInterval(()=>{
    el.textContent+=text[i];
    i++;
    if(i===text.length){
      clearInterval(timer);
      callback();
    }
  },120);
}

function showFinal(){
  document.body.innerHTML=`
    <h1 style="font-size:4em;color:white;">Best Valentine Ever 😘</h1>
    <p style="font-size:2em;">I love you, Neha ❤️</p>
  `;
  for(let i=0;i<120;i++){
    setTimeout(createHeart,i*25);
  }
}
</script>

</body>
</html>
