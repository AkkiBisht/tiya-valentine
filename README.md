<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>tiya ❤️</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',sans-serif}
body{height:100vh;overflow:hidden}

/* COMMON */
.page{display:none;height:100vh;width:100%;justify-content:center;align-items:center;text-align:center}
.active{display:flex}
button{padding:12px 35px;border:none;border-radius:40px;font-size:16px;cursor:pointer}

/* PAGE 1 */
#page1{background:url('bg.jpg') center/cover no-repeat;position:relative;color:white}
.overlay{position:absolute;inset:0;background:rgba(0,0,0,.45)}
.card{
  position:relative;z-index:2;
  backdrop-filter:blur(14px);
  background:rgba(255,255,255,.2);
  padding:45px;border-radius:30px
}
.name{font-size:60px;text-transform:lowercase}
#yes{background:#ff4d88;color:white}
#no{background:#ddd;position:absolute}

/* PAGE 2 */
#page2{background:linear-gradient(135deg,#ff9a9e,#fad0c4)}
.riddleBox{
  background:white;padding:40px;border-radius:30px;
  width:90%;max-width:460px;
}
input{
  width:100%;padding:12px;border-radius:30px;
  border:2px solid #ff4d88;font-size:16px;margin-top:15px;
}
.shake{animation:shake .4s}
@keyframes shake{
  0%{transform:translateX(0)}
  25%{transform:translateX(-6px)}
  50%{transform:translateX(6px)}
  75%{transform:translateX(-6px)}
  100%{transform:translateX(0)}
}

/* PAGE 3 */
#page3{
  background:linear-gradient(135deg,#fad0c4,#ffd1dc);
  flex-direction:column;overflow:auto
}
.photos img{
  width:260px;height:180px;object-fit:cover;
  border-radius:25px;margin:15px;
  cursor:pointer;
  transition:.4s;
}
.photos img:hover{transform:scale(1.05)}

/* PAGE 4 */
#page4{
  background:rgba(0,0,0,.9);
  flex-direction:column;color:white;
  padding:20px;
}
#fullImg{
  max-width:90%;
  max-height:70vh;
  border-radius:25px;
}
.memory{
  max-width:600px;
  margin-top:20px;
  font-size:18px;
  line-height:1.5;
}

/* Animated memory text */
.memory span{
  opacity:0;
  animation:textPop .4s forwards;
}
@keyframes textPop{
  to{opacity:1}
}

/* Letter */
.letter{
  background:white;padding:30px;border-radius:25px;
  max-width:650px;margin:25px;font-size:18px;color:black
}

/* Hearts */
.heart{
  position:fixed;bottom:-20px;color:#ff4d88;
  animation:float 5s linear infinite;
}
@keyframes float{
  to{transform:translateY(-120vh);opacity:0}
}

/* Glow + Fade Blur */
.glow{animation:glowPulse .8s ease-in-out}
@keyframes glowPulse{
  0%{box-shadow:0 0 0 rgba(255,77,136,0)}
  50%{box-shadow:0 0 40px rgba(255,77,136,.9)}
  100%{box-shadow:0 0 0 rgba(255,77,136,0)}
}
.fadeBlur{
  animation:fadeBlur .8s ease;
}
@keyframes fadeBlur{
  from{opacity:0;filter:blur(10px)}
  to{opacity:1;filter:blur(0)}
}

/* Slideshow Button */
#slideBtn{
  background:#ff4d88;
  color:white;
  margin:15px;
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<div class="page active" id="page1">
  <div class="overlay"></div>
  <div class="card">
    <div class="name">kuttiii</div>
    <p>Since 01 March 2023 ❤️
    yo are my valentine to tu na ni bol skti </p><br>
    <button id="yes" onclick="goPage(2)">YES 💍</button>
    <button id="no">NO 😭</button>
  </div>
</div>

<!-- PAGE 2 -->
<div class="page" id="page2">
  <div class="riddleBox" id="riddleBox">
    <h2 id="rTitle"></h2><br>
    <p id="rText"></p>
    <input id="answer" placeholder="Type your answer…">
    <br><br>
    <button style="background:#ff4d88;color:white" onclick="nextRiddle()">Next ❤️</button>
  </div>
</div>

<!-- PAGE 3 -->
<div class="page" id="page3">
  <h2>Our Love in Frames ❤️</h2>
  <div class="photos">
    <img src="p1.jpg" onclick="openMemory(0)">
    <img src="p2.jpg" onclick="openMemory(1)">
    <img src="p3.jpg" onclick="openMemory(2)">
    <img src="p4.jpg" onclick="openMemory(3)">
  </div>

  <div class="letter">
    chotu don jii<br><br>
    Tum meri life ka sabse soft aur strong hissa ho.  
    Tumhare saath har memory ek blessing lagti hai.  
    I don’t need perfect days —  
    I just need you in all my days ❤️
    the best part of my life ki tera mere sath hona
    Tere nakhre uthane me bhi maja ata 😂😋
Or jab tu gusse me Hoti tbh to aye hayee 🥹😚 maja ata teko dekhne me 
Kbhi bhi to tu bht hala krti pr maja ata 😁😁
Tere sath bitaye har movement kushi ladhi ruthna manana sab best hai 😚😚
Teri chudel wali harkate sali pagal si 
Kbhi kbhi sochta hu ki
Agr hum sath ni hote to kay hota hum dono pagalo ka 😂
Tu to sudhri rhti 😂
Kair xod na hu n me tere sath to ni sochna esa 
Dono  pagal ek jese hai 😚
36 ke 36 gudh mile hai syed hamare bhi 🤭🤭
But thank you soo much for everything 🤭🩷👥
Cudel si dayan 
Teri bachi wali harkate sab se best pagl si 🤭😚kutti kamini 
Notanki baj khi ki 🤭🤭
  </div>
</div>

<!-- PAGE 4 -->
<div class="page" id="page4">
  <img id="fullImg">
  <div class="memory" id="memoryText"></div>
  <button id="slideBtn" onclick="toggleSlideshow()">Pause ⏸️</button>
  <button onclick="goPage(3)" style="background:#ff4d88;color:white">Back ❤️</button>
</div>

<script>
function goPage(n){
  stopSlideshow();
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.getElementById('page'+n).classList.add('active');
}

/* NO button run */
no.addEventListener("mouseenter",()=>{
  no.style.transform=`translate(${Math.random()*200-100}px,${Math.random()*120-60}px)`
});

/* RIDDLES */
const riddles=[
  "Main bolta nahi par sab kuch keh deta hoon, main kaun hoon?",
  "Wo kaunsa naam hai jo sunte hi smile aa jaati hai?",
  "Wo kaun hai jiske saath future imagine hota hai?"
];
let r=0;
rTitle.innerText="Riddle 1 💌";
rText.innerText=riddles[0];

function nextRiddle(){
  if(answer.value.trim()===""){
    riddleBox.classList.add("shake");
    setTimeout(()=>riddleBox.classList.remove("shake"),400);
    return;
  }
  r++;
  answer.value="";
  if(r<riddles.length){
    rTitle.innerText="Riddle "+(r+1)+" 💌";
    rText.innerText=riddles[r];
  }else{
    goPage(3);
  }
}

/* PHOTO + SLIDESHOW */
const memories=[
  "Is photo ke saath ek simple si feeling judi hai — sukoon yad hai tu kese sarma ri thi us din jab mepe yeh phto ayii heheh.",
  "Is moment mein mujhe realise hua, tum meri safe place ho kese hum coching me sath me padhte bethte smjhte the qutions ko ek dusre ko smjhate .",
  "Har smile ke peeche tumhara haath tha yad hai us din tera bithday tha tu aayi kese mene teko hug kiya fir ......",
  "Ye memory meri favorite hai… kyunki isme tum ho is time pe hmari bht ladai hui mele ke time pe mene bola tu mese ml ni ri pr fir bhi maja aaya is din ."
];

let currentIndex=0;
let slide=null;
let playing=true;

function animateText(text){
  memoryText.innerHTML="";
  [...text].forEach((c,i)=>{
    const span=document.createElement("span");
    span.innerText=c;
    span.style.animationDelay=i*0.03+"s";
    memoryText.appendChild(span);
  });
}

function showPhoto(){
  fullImg.className="";
  void fullImg.offsetWidth;
  fullImg.src=`p${currentIndex+1}.jpg`;
  fullImg.classList.add("fadeBlur","glow");
  animateText(memories[currentIndex]);
}

function openMemory(i){
  currentIndex=i;
  goPage(4);
  showPhoto();
  startSlideshow();
}

function startSlideshow(){
  stopSlideshow();
  slide=setInterval(()=>{
    currentIndex=(currentIndex+1)%memories.length;
    showPhoto();
  },3000);
}

function stopSlideshow(){
  clearInterval(slide);
}

function toggleSlideshow(){
  if(playing){
    stopSlideshow();
    slideBtn.innerText="Play ▶️";
  }else{
    startSlideshow();
    slideBtn.innerText="Pause ⏸️";
  }
  playing=!playing;
}

/* SWIPE */
let startX=0;
page4.addEventListener("touchstart",e=>startX=e.touches[0].clientX);
page4.addEventListener("touchend",e=>{
  let endX=e.changedTouches[0].clientX;
  if(Math.abs(startX-endX)>50){
    currentIndex = startX>endX
      ? (currentIndex+1)%memories.length
      : (currentIndex-1+memories.length)%memories.length;
    showPhoto();
  }
});

/* HEARTS */
setInterval(()=>{
  const h=document.createElement("div");
  h.className="heart";
  h.innerHTML="❤️";
  h.style.left=Math.random()*100+"vw";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),5000);
},700);
</script>

</body>
</html>
