# Play.html<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mustafaazahraa ❤️</title>

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    min-height:100vh;
    font-family:Tahoma,Arial,sans-serif;
    background:
    radial-gradient(circle at 20% 20%,#dceeff 0 10%,transparent 30%),
    radial-gradient(circle at 80% 20%,#ffdced 0 10%,transparent 30%),
    linear-gradient(135deg,#f8fbff,#fff0f7);
    color:#333;
    overflow-x:hidden;
}

button,input{
    font-family:inherit;
}

button{
    cursor:pointer;
}

#particles{
    position:fixed;
    inset:0;
    pointer-events:none;
    overflow:hidden;
    z-index:0;
}

.particle{
    position:absolute;
    bottom:-60px;
    animation:floatUp linear forwards;
    opacity:.7;
}

@keyframes floatUp{
    0%{
        transform:translateY(0) rotate(0);
        opacity:0;
    }
    15%{opacity:.8;}
    100%{
        transform:translateY(-110vh) rotate(360deg);
        opacity:0;
    }
}

.app{
    position:relative;
    z-index:2;
    width:100%;
    max-width:700px;
    margin:auto;
    padding:20px;
}

.screen{
    display:none;
    min-height:95vh;
    align-items:center;
    justify-content:center;
}

.screen.active{
    display:flex;
}

.card{
    width:100%;
    padding:30px;
    border-radius:35px;
    background:rgba(255,255,255,.82);
    backdrop-filter:blur(20px);
    box-shadow:0 25px 70px rgba(0,0,0,.12);
    text-align:center;
}

.logo{
    font-size:42px;
    font-weight:bold;
    margin-bottom:10px;
    background:linear-gradient(90deg,#1877d2,#ff4f9a);
    -webkit-background-clip:text;
    color:transparent;
}

.subtitle{
    color:#777;
    font-size:18px;
    margin-bottom:25px;
}

h1,h2,h3{
    margin-bottom:15px;
}

p{
    line-height:1.8;
}

input{
    width:100%;
    padding:16px;
    margin:8px 0;
    border:2px solid #eee;
    border-radius:18px;
    text-align:center;
    font-size:16px;
    outline:none;
}

input:focus{
    border-color:#ff5da2;
}

.btn{
    width:100%;
    padding:16px;
    margin-top:12px;
    border:0;
    border-radius:18px;
    font-size:17px;
    font-weight:bold;
    transition:.3s;
}

.btn:hover{
    transform:translateY(-3px);
}

.primary{
    color:white;
    background:linear-gradient(135deg,#ff4f9a,#ff83b9);
    box-shadow:0 10px 25px rgba(255,79,154,.25);
}

.secondary{
    color:#236cc2;
    background:#e4f0ff;
}

.blueBtn{
    color:#176bc5;
    background:#ddecff;
}

.pinkBtn{
    color:#e63783;
    background:#ffe1ef;
}

.gender{
    display:flex;
    gap:10px;
    margin:10px 0;
}

.gender button{
    flex:1;
    padding:14px;
    border:0;
    border-radius:18px;
    opacity:.55;
    font-weight:bold;
    transition:.3s;
}

.gender button.selected{
    opacity:1;
    transform:scale(1.04);
    box-shadow:0 8px 20px rgba(0,0,0,.1);
}

.room-code{
    margin:20px 0;
    padding:18px;
    border-radius:20px;
    background:#fff0f7;
    color:#ff408e;
    font-size:35px;
    font-weight:bold;
    letter-spacing:7px;
}

.share-box{
    display:flex;
    gap:7px;
}

.share-box input{
    margin:0;
}

.small-btn{
    border:0;
    border-radius:15px;
    padding:0 15px;
    background:#e4f0ff;
    color:#176bc5;
}

.waiting{
    margin-top:20px;
    color:#777;
    animation:pulse 1.5s infinite;
}

@keyframes pulse{
    50%{opacity:.4}
}

.hidden{
    display:none!important;
}

/* GAME */

.game{
    width:100%;
}

.game-header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:10px;
    margin-bottom:12px;
    font-weight:bold;
}

.progress{
    width:100%;
    height:10px;
    background:#eee;
    border-radius:20px;
    overflow:hidden;
    margin-bottom:15px;
}

.progress-bar{
    height:100%;
    width:1%;
    background:linear-gradient(90deg,#2180df,#ff4f9a);
    transition:.5s;
}

.players{
    display:flex;
    gap:10px;
    margin-bottom:15px;
}

.player{
    flex:1;
    padding:12px;
    border-radius:17px;
    font-weight:bold;
}

.player.blue{
    background:#ddecff;
    color:#176bc5;
}

.player.pink{
    background:#ffe1ef;
    color:#e63783;
}

.question-card{
    padding:30px 20px;
    background:rgba(255,255,255,.9);
    border-radius:35px;
    box-shadow:0 20px 60px rgba(0,0,0,.12);
    text-align:center;
}

.heart{
    font-size:70px;
    animation:heartbeat 1.5s infinite;
}

@keyframes heartbeat{
    0%,100%{transform:scale(1)}
    50%{transform:scale(1.18)}
}

.level-badge{
    display:inline-block;
    padding:8px 15px;
    background:#fff0f7;
    color:#ff438f;
    border-radius:20px;
    margin-bottom:15px;
    font-weight:bold;
}

#questionText{
    line-height:1.8;
    margin:15px 0 25px;
}

.answers{
    display:grid;
    gap:12px;
}

.answer{
    padding:16px;
    border:0;
    border-radius:18px;
    background:#f5f7fa;
    font-size:16px;
    transition:.3s;
}

.answer:hover{
    background:#ffe6f1;
    transform:translateY(-2px);
}

.answer.selected{
    background:#ff5da2;
    color:#fff;
}

.answer:disabled{
    cursor:not-allowed;
}

.status{
    min-height:30px;
    margin-top:18px;
    font-weight:bold;
    color:#777;
}

.reveal{
    display:none;
    margin-top:20px;
}

.reveal.active{
    display:block;
}

.reveal-box{
    padding:15px;
    border-radius:18px;
    margin:10px 0;
    line-height:1.7;
}

.reveal-blue{
    background:#ddecff;
    color:#176bc5;
}

.reveal-pink{
    background:#ffe1ef;
    color:#e63783;
}

.level-message{
    margin-top:15px;
    padding:15px;
    border-radius:20px;
    background:#fff7d9;
    color:#9a7200;
}

/* MINI GAME */

.mini-game{
    display:none;
    margin-top:20px;
    padding:20px;
    border-radius:25px;
    background:linear-gradient(135deg,#e8f4ff,#fff0f7);
}

.mini-game.active{
    display:block;
}

.race-track{
    position:relative;
    height:100px;
    background:#fff;
    border-radius:20px;
    margin:20px 0;
    overflow:hidden;
}

.racer{
    position:absolute;
    font-size:35px;
    transition:1s;
}

.racer.one{
    top:10px;
    right:10px;
}

.racer.two{
    bottom:10px;
    right:10px;
}

/* RESULT */

.result-heart{
    font-size:100px;
    animation:heartbeat 1.5s infinite;
}

.score{
    font-size:75px;
    font-weight:bold;
    color:#ff4f9a;
    margin:15px;
}

.final-box{
    padding:20px;
    border-radius:25px;
    background:linear-gradient(135deg,#fff0f7,#eaf5ff);
    line-height:2;
}

/* TOAST */

.toast{
    position:fixed;
    bottom:25px;
    left:50%;
    transform:translateX(-50%) translateY(100px);
    background:#222;
    color:#fff;
    padding:14px 22px;
    border-radius:30px;
    z-index:20;
    transition:.4s;
}

.toast.show{
    transform:translateX(-50%) translateY(0);
}

@media(max-width:500px){
    .card{
        padding:22px;
    }

    .logo{
        font-size:30px;
    }

    .room-code{
        font-size:28px;
    }
}
</style>
</head>

<body>

<div id="particles"></div>

<div class="app">

<!-- HOME -->
<section id="home" class="screen active">
<div class="card">

<div class="logo">
💙 Mustafaazahraa 🩷
</div>

<div class="subtitle">
لعبة لشخصين... 100 سؤال... وقصة حب واحدة ❤️
</div>

<h2>هل أنتم مستعدين للمغامرة؟ 😍</h2>

<p>
جاوبوا، اضحكوا، حلوا الألغاز، وتعرفوا على بعض أكثر ❤️
</p>

<button class="btn primary" id="createPage">
🎮 إنشاء لعبة جديدة
</button>

<button class="btn secondary" id="joinPage">
🔗 دخول إلى لعبة
</button>

</div>
</section>


<!-- CREATE -->
<section id="createScreen" class="screen">
<div class="card">

<h2>أنشئ لعبتكم ❤️</h2>

<input id="createName"
placeholder="اكتب اسمك">

<div class="gender">

<button class="blueBtn"
data-color="blue">
💙 مصطفى
</button>

<button class="pinkBtn"
data-color="pink">
🩷 زهراء
</button>

</div>

<button class="btn primary"
id="createRoom">
إنشاء الغرفة ❤️
</button>

<div id="createdArea" class="hidden">

<h3>تم إنشاء الغرفة 🎉</h3>

<div id="roomCode"
class="room-code">
------
</div>

<div class="share-box">

<input id="shareLink" readonly>

<button id="copyLink"
class="small-btn">
نسخ
</button>

</div>

<button class="btn primary"
id="whatsappShare">
📱 مشاركة الرابط
</button>

<div class="waiting">
⏳ ننتظر دخول اللاعب الثاني...
</div>

</div>

</div>
</section>


<!-- JOIN -->
<section id="joinScreen" class="screen">
<div class="card">

<h2>انضم إلى اللعبة 🩷</h2>

<input id="joinName"
placeholder="اكتب اسمك">

<input id="joinRoom"
placeholder="كود الغرفة">

<div class="gender">

<button class="blueBtn"
data-join-color="blue">
💙 مصطفى
</button>

<button class="pinkBtn"
data-join-color="pink">
🩷 زهراء
</button>

</div>

<button class="btn primary"
id="joinRoomBtn">
دخول اللعبة ❤️
</button>

</div>
</section>


<!-- GAME -->
<section id="gameScreen" class="screen">

<div class="game">

<div class="game-header">

<span id="levelText">
المستوى 1
</span>

<span id="questionCount">
1 / 10
</span>

</div>

<div class="progress">
<div id="progressBar"
class="progress-bar"></div>
</div>

<div class="players">

<div id="player1"
class="player blue">
💙 اللاعب الأول
</div>

<div id="player2"
class="player pink">
🩷 اللاعب الثاني
</div>

</div>

<div class="question-card">

<div class="heart">
❤️
</div>

<div id="levelBadge"
class="level-badge">
المستوى الأول
</div>

<h2 id="questionText">
السؤال
</h2>

<div id="answers"
class="answers">
</div>

<div id="status"
class="status">
اختار إجابتك ❤️
</div>

<div id="reveal"
class="reveal">

<h3>إجاباتكم 😍</h3>

<div id="answerOne"
class="reveal-box reveal-blue">
💙 ...
</div>

<div id="answerTwo"
class="reveal-box reveal-pink">
🩷 ...
</div>

<div id="levelMessage"
class="level-message">
</div>

<button id="nextQuestion"
class="btn primary">
السؤال التالي ➡️
</button>

</div>

</div>

<!-- MINI GAME -->
<div id="miniGame"
class="mini-game">

<h3>🏎️ سباق الحب!</h3>

<p>
اضغط الزر وخلي لاعبك يتقدم!
</p>

<div class="race-track">

<div id="racer1"
class="racer one">
💙🏎️
</div>

<div id="racer2"
class="racer two">
🩷🏎️
</div>

</div>

<button id="raceButton"
class="btn primary">
🏁 ابدأ السباق
</button>

</div>

</div>
</section>


<!-- RESULT -->
<section id="resultScreen" class="screen">
<div class="card">

<div class="result-heart">
💖
</div>

<h1>
انتهت مغامرتكم!
</h1>

<div class="score">
<span id="finalScore">100</span>%
</div>

<h2 id="finalTitle">
أنتم ثنائي رائع 😍
</h2>

<div class="final-box">

<p id="finalMessage">
بعد 100 سؤال، واضح أن قصتكم مميزة جدًا ❤️
</p>

</div>

<button class="btn primary"
onclick="location.href=location.pathname">
🔄 لعب من جديد
</button>

</div>
</section>

</div>

<div id="toast" class="toast"></div>


<script type="module">

/* =====================================================
   FIREBASE
===================================================== */

import {
initializeApp
} from
"https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";

import {
getDatabase,
ref,
set,
get,
update,
onValue,
runTransaction
} from
"https://www.gstatic.com/firebasejs/10.12.2/firebase-database.js";


/* =====================================================
   🔥 ضع بيانات Firebase هنا
===================================================== */

const firebaseConfig = {

apiKey:"YOUR_API_KEY",

authDomain:"YOUR_PROJECT_ID.firebaseapp.com",

databaseURL:
"https://YOUR_PROJECT_ID-default-rtdb.firebaseio.com",

projectId:"YOUR_PROJECT_ID",

storageBucket:
"YOUR_PROJECT_ID.appspot.com",

messagingSenderId:"YOUR_SENDER_ID",

appId:"YOUR_APP_ID"

};


const app =
initializeApp(firebaseConfig);

const db =
getDatabase(app);


/* =====================================================
   VARIABLES
===================================================== */

let roomId="";
let playerId="";
let playerName="";
let playerColor="";
let selectedColor="";

let currentRoom=null;

let answered=false;

let transitioning=false;


/* =====================================================
   QUESTIONS
   10 LEVELS × 10 QUESTIONS
===================================================== */

const questions=[

[
"منو يحب الثاني أكثر؟ 😏",
"منو وقع بالحب أول؟ ❤️",
"شنو أول شيء جذبك إلي؟",
"منو يغار أكثر؟ 😂",
"منو يعتذر أول؟",
"منو يدلل الثاني أكثر؟",
"شنو أجمل ذكرى بينكم؟",
"لو نطلع هسه وين توديني؟",
"شنو اللقب اللي تحب تسمعه مني؟",
"هل تتوقع نبقى سوا دائمًا؟ ❤️"
],

[
"شنو الأغنية اللي تذكرك بي؟ 🎵",
"منو يضحك الثاني أكثر؟ 😂",
"منو أكثر واحد عنيد؟",
"لو نسافر وين نروح؟",
"منو يحب المفاجآت أكثر؟",
"شنو أكثر شيء يخليك تبتسم؟",
"منو يشتاق أكثر؟",
"لو نفتح مشروع سوا شنو يكون؟",
"شنو حلم تتمنى نحققه؟",
"تحبني أكثر اليوم لو أول يوم؟ 😏"
],

[
"لو فزت بمليون شتسوي إلي؟",
"منو أكثر واحد يتوتر؟",
"شنو أكثر كلمة أقولها؟",
"لو نسافر سوا وين نروح؟",
"منو يحب المفاجآت؟",
"شنو الشيء اللي يخليك تبتسم؟",
"منو يغار أكثر؟",
"لو نفتح مطعم شنو نسميه؟",
"شنو حلمك ويانا؟",
"تحبني؟ ❤️"
],

[
"منو يزعل أسرع؟",
"شنو الشيء اللي مستحيل تنساه مني؟",
"لو أختفي يوم كامل شتسوي؟ 😂",
"منو يحب الكلام أكثر؟",
"شنو أجمل صفة بي؟",
"لو نكتب كتاب شنو نسميه؟",
"منو المدلل؟",
"شنو أكثر موقف محرج؟",
"شنو رسالتك السرية إلي؟",
"تتمنى قصتنا تستمر للأبد؟"
],

[
"منو يفكر بالثاني أول ما يصحى؟",
"شنو أكثر شيء يضحكك بي؟",
"منو يحب الأكل أكثر؟ 😂",
"لو نعيش بفيلم شنو يكون؟",
"منو يخاف أكثر؟",
"شنو يخليك تحس بالأمان وياي؟",
"منو يحب السهر؟",
"شنو أحلى هدية؟",
"شنو تريد نسوي سوا؟",
"تحب تسمع كلمة أحبك؟ ❤️"
],

[
"منو ينسى أكثر؟ 😂",
"شنو أول انطباع أخذته عني؟",
"منو رومانسي أكثر؟",
"وين نروح بدون تخطيط؟",
"شنو أكثر شيء تخاف تخسره؟",
"منو يحب الصور أكثر؟",
"شنو المكان اللي تتمنى نزوره؟",
"شنو الموقف اللي خلاك تحبني؟",
"شنو الشيء اللي تريدني أغيره؟",
"هل أنا شخص مميز بحياتك؟"
],

[
"لو كنت شخصية كرتونية شنو تكون؟",
"منو يضحك بدون سبب؟ 😂",
"شنو أغرب عادة عندي؟",
"منو يحب النوم أكثر؟",
"لو نعيش بجزيرة شنسوي؟",
"شنو أكثر شيء يجمعنا؟",
"منو يحب المغامرات؟",
"شنو تحب تسمع مني؟",
"لو عندنا يوم كامل شنسوي؟",
"مستعد تكمل المغامرة؟ ❤️"
],

[
"منو يحب المفاجآت؟ 🎁",
"شنو أجمل كلمة سمعتها مني؟",
"منو يشتاق أكثر؟",
"لو توقف الزمن شتسوي؟",
"شنو أكثر شيء نختلف عليه؟",
"شنو أكثر شيء يصالحنا؟",
"منو حساس أكثر؟",
"شنو اللحظة اللي تتمنى تتكرر؟",
"شنو أمنيتك إلنا؟",
"نكمل للمستوى الأخير؟ 😏"
],

[
"منو يعرف الثاني أكثر؟",
"شنو أكثر شيء تعلمته مني؟",
"لو نرجع لأول يوم شتغير؟",
"شنو أكثر شيء تحبه بعلاقتنا؟",
"منو يحافظ على العلاقة أكثر؟",
"شنو تتمنى يصير بالمستقبل؟",
"لو نكتب رسالة للمستقبل شنو نكتب؟",
"شنو الشيء اللي مستحيل تتخلى عنه؟",
"هل قصتنا مختلفة؟",
"هل أنت سعيد لأنك معي؟ ❤️"
],

[
"شنو أول شيء تسويه إذا شفنا بعض؟ 🥰",
"منو يحب الثاني أكثر؟",
"شنو أجمل لحظة عشتها وياي؟",
"شنو كلمة توصف علاقتنا؟",
"شنو الشيء اللي تتمنى يبقى بيننا؟",
"منو الشخص اللي ما تريد تخسره؟ ❤️",
"شنو وعدك إلي؟",
"لو نكبر سوا شنتمنى نتذكر؟",
"شنو رسالتك الأخيرة إلي؟",
"هل تحب مصطفى وزهراء؟ ❤️💙🩷"
]

];


/* =====================================================
   ANSWER OPTIONS
===================================================== */

const answerOptions=[
"أكيد ❤️",
"طبعًا 😍",
"يمكن 😏",
"هههه أكيد 😂"
];


/* =====================================================
   SCREEN
===================================================== */

function showScreen(id){

document
.querySelectorAll(".screen")
.forEach(s=>s.classList.remove("active"));

document
.getElementById(id)
.classList.add("active");

}


/* =====================================================
   TOAST
===================================================== */

function toast(message){

const t=
document.getElementById("toast");

t.innerText=message;

t.classList.add("show");

setTimeout(
()=>t.classList.remove("show"),
2500
);

}


/* =====================================================
   NAVIGATION
===================================================== */

document
.getElementById("createPage")
.onclick=()=>{
showScreen("createScreen");
};

document
.getElementById("joinPage")
.onclick=()=>{
showScreen("joinScreen");
};


/* =====================================================
   COLOR SELECT
===================================================== */

document
.querySelectorAll("[data-color]")
.forEach(btn=>{

btn.onclick=()=>{

document
.querySelectorAll("[data-color]")
.forEach(b=>
b.classList.remove("selected")
);

btn.classList.add("selected");

selectedColor=
btn.dataset.color;

};

});


document
.querySelectorAll("[data-join-color]")
.forEach(btn=>{

btn.onclick=()=>{

document
.querySelectorAll("[data-join-color]")
.forEach(b=>
b.classList.remove("selected")
);

btn.classList.add("selected");

selectedColor=
btn.dataset.joinColor;

};

});


/* =====================================================
   ROOM CODE
===================================================== */

function generateRoom(){

const chars=
"ABCDEFGHJKLMNPQRSTUVWXYZ23456789";

let code="";

for(let i=0;i<6;i++){

code+=chars[
Math.floor(
Math.random()*chars.length
)
];

}

return code;

}


/* =====================================================
   CREATE ROOM
===================================================== */

document
.getElementById("createRoom")
.onclick=async()=>{

playerName=
document
.getElementById("createName")
.value.trim();

if(!playerName){

toast("اكتب اسمك أولًا ❤️");

return;

}

if(!selectedColor){

toast("اختار شخصيتك 💙🩷");

return;

}

roomId=generateRoom();

playerId="player1";

playerColor=selectedColor;


const room={

status:"waiting",

level:0,

question:0,

phase:"waiting",

players:{

player1:{

name:playerName,

color:playerColor

},

player2:null

},

answers:{},

scores:{

player1:0,

player2:0

},

createdAt:Date.now(),

transitionLock:false

};


try{

await set(
ref(db,"rooms/"+roomId),
room
);


document
.getElementById("roomCode")
.innerText=roomId;


const link=
location.href.split("?")[0]
+"?room="+roomId;


document
.getElementById("shareLink")
.value=link;


document
.getElementById("createdArea")
.classList.remove("hidden");


listenRoom();


}catch(error){

console.error(error);

toast("حدث خطأ في إنشاء الغرفة");

}

};


/* =====================================================
   COPY
===================================================== */

document
.getElementById("copyLink")
.onclick=async()=>{

const link=
document
.getElementById("shareLink")
.value;

try{

await navigator.clipboard.writeText(link);

toast("تم نسخ الرابط ❤️");

}catch{

toast("انسخ الرابط يدويًا");

}

};


/* =====================================================
   WHATSAPP
===================================================== */

document
.getElementById("whatsappShare")
.onclick=()=>{

const link=
document
.getElementById("shareLink")
.value;

const text=
"تعالي نلعب لعبة Mustafaazahraa سوا ❤️🩷💙\n"
+link;

window.open(
"https://wa.me/?text="
+encodeURIComponent(text),
"_blank"
);

};


/* =====================================================
   JOIN
===================================================== */

document
.getElementById("joinRoomBtn")
.onclick=async()=>{

playerName=
document
.getElementById("joinName")
.value.trim();

roomId=
document
.getElementById("joinRoom")
.value.trim()
.toUpperCase();


if(!playerName){

toast("اكتب اسمك ❤️");

return;

}

if(!roomId){

toast("اكتب كود الغرفة");

return;

}

if(!selectedColor){

toast("اختار شخصيتك");

return;

}


const roomRef=
ref(db,"rooms/"+roomId);


const snapshot=
await get(roomRef);


if(!snapshot.exists()){

toast("الغرفة غير موجودة ❌");

return;

}


const room=
snapshot.val();


if(room.players.player2){

toast("الغرفة ممتلئة 😅");

return;

}


playerId="player2";

playerColor=selectedColor;


await update(

roomRef,

{

"players/player2":{

name:playerName,

color:playerColor

},

status:"ready",

phase:"question"

}

);


listenRoom();

};


/* =====================================================
   LISTEN
===================================================== */

function listenRoom(){

onValue(

ref(db,"rooms/"+roomId),

snapshot=>{

if(!snapshot.exists())
return;

currentRoom=
snapshot.val();


if(
currentRoom.players.player2
){

document
.getElementById("player1")
.innerText=
"💙 "+
currentRoom.players.player1.name;


document
.getElementById("player2")
.innerText=
"🩷 "+
currentRoom.players.player2.name;


if(
currentRoom.status==="ready"
){

showScreen("gameScreen");

}

}


if(
currentRoom.phase==="question"
){

renderQuestion();

}


if(
currentRoom.phase==="waiting_answers"
){

showWaiting();

}


if(
currentRoom.phase==="reveal"
){

showReveal();

}


if(
currentRoom.phase==="finished"
){

showResult();

}

}

);

}


/* =====================================================
   RENDER QUESTION
===================================================== */

function renderQuestion(){

showScreen("gameScreen");

answered=false;

transitioning=false;


const level=
currentRoom.level;

const q=
currentRoom.question;


document
.getElementById("levelText")
.innerText=
"المستوى "+
(level+1);


document
.getElementById("questionCount")
.innerText=
(q+1)+
" / 10";


document
.getElementById("levelBadge")
.innerText=
"المستوى "+
(level+1);


document
.getElementById("questionText")
.innerText=
questions[level][q];


const total=
level*10+q+1;


document
.getElementById("progressBar")
.style.width=
(total)+"%";


document
.getElementById("reveal")
.classList.remove("active");


document
.getElementById("status")
.innerText=
"اختار إجابتك ❤️";


const container=
document.getElementById("answers");


container.innerHTML="";


answerOptions.forEach(
option=>{

const button=
document.createElement("button");

button.className="answer";

button.innerText=option;


button.onclick=()=>{

if(answered)
return;

answered=true;

document
.querySelectorAll(".answer")
.forEach(
b=>b.disabled=true
);

button.classList.add("selected");

submitAnswer(option);

};


container.appendChild(button);

});

}


/* =====================================================
   SUBMIT ANSWER
===================================================== */

async function submitAnswer(answer){

const key=
currentRoom.level+
"_"+currentRoom.question;


await set(

ref(
db,
"rooms/"
+roomId+
"/answers/"
+key+
"/"+
playerId
),

{

text:answer,

time:Date.now()

}

);


document
.getElementById("status")
.innerText=
"تم حفظ إجابتك ❤️";


checkBothAnswers();

}


/* =====================================================
   CHECK BOTH
===================================================== */

async function checkBothAnswers(){

const key=
currentRoom.level+
"_"+currentRoom.question;


const snapshot=
await get(

ref(
db,
"rooms/"
+roomId+
"/answers/"
+key
)

);


if(!snapshot.exists())
return;


const data=
snapshot.val();


if(
data.player1 &&
data.player2
){

await update(

ref(
db,
"rooms/"+roomId
),

{

phase:"reveal"

}

);

}

}


/* =====================================================
   WAITING
===================================================== */

function showWaiting(){

document
.getElementById("status")
.innerText=
"⏳ ننتظر إجابة شريكك ❤️";

}


/* =====================================================
   REVEAL
===================================================== */

function showReveal(){

const key=
currentRoom.level+
"_"+currentRoom.question;


const data=
currentRoom.answers[key];


if(!data)
return;


document
.getElementById("answerOne")
.innerText=
"💙 "+
currentRoom.players.player1.name+
": "+
(data.player1?.text||"...");


document
.getElementById("answerTwo")
.innerText=
"🩷 "+
currentRoom.players.player2.name+
": "+
(data.player2?.text||"...");


document
.getElementById("reveal")
.classList.add("active");


document
.getElementById("status")
.innerText=
"😂 شوفوا إجابات بعض!";


if(
currentRoom.question===9
){

document
.getElementById("levelMessage")
.innerText=
"🎉 مبروك! خلصتوا هذا المستوى ❤️";

}else{

document
.getElementById("levelMessage")
.innerText=
"جاهزين للسؤال الجاي؟ 😍";

}

}


/* =====================================================
   NEXT QUESTION
===================================================== */

document
.getElementById("nextQuestion")
.onclick=async()=>{

if(playerId!=="player1"){

toast("اللاعب الأول ينتقل للسؤال التالي ❤️");

return;

}

if(transitioning)
return;

transitioning=true;


const roomRef=
ref(db,"rooms/"+roomId);


await runTransaction(

roomRef,

room=>{

if(!room)
return room;


if(
room.phase!=="reveal"
||
room.transitionLock
){

return;

}


room.transitionLock=true;


let nextQ=
room.question+1;

let nextLevel=
room.level;


if(nextQ>=10){

nextQ=0;

nextLevel++;

}


if(nextLevel>=10){

room.phase="finished";

return room;

}


room.level=nextLevel;

room.question=nextQ;

room.phase="question";

room.transitionLock=false;


return room;

}

);

};


/* =====================================================
   RESULT
===================================================== */

function showResult(){

showScreen("resultScreen");


const score=
Math.floor(
90+
Math.random()*11
);


document
.getElementById("finalScore")
.innerText=score;


if(score>=98){

document
.getElementById("finalTitle")
.innerText=
"أنتم روحين بقلب واحد 💖";


document
.getElementById("finalMessage")
.innerText=
"100 سؤال وما زلتوا سوا! واضح أن قصتكم مميزة جدًا، وإن شاء الله تبقى محبتكم للأبد ❤️";

}else{

document
.getElementById("finalTitle")
.innerText=
"ثنائي رائع جدًا 😍";


document
.getElementById("finalMessage")
.innerText=
"كانت رحلة جميلة بينكم، والأجمل أنكم عشتوها سوا ❤️";

}

}


/* =====================================================
   MINI RACE
===================================================== */

const raceButton=
document.getElementById("raceButton");


raceButton.onclick=()=>{

const r1=
document.getElementById("racer1");

const r2=
document.getElementById("racer2");


r1.style.right=
(20+
Math.random()*60)+"%";


r2.style.right=
(20+
Math.random()*60)+"%";


setTimeout(()=>{

toast(
Math.random()>.5
?
"💙 مصطفى فاز بالسباق 😂"
:
"🩷 زهراء فازت بالسباق 😂"
);

},1200);

};


/* =====================================================
   AUTO JOIN URL
===================================================== */

const params=
new URLSearchParams(
location.search
);

const roomFromUrl=
params.get("room");


if(roomFromUrl){

document
.getElementById("joinRoom")
.value=
roomFromUrl.toUpperCase();

showScreen("joinScreen");

}


/* =====================================================
   FLOATING HEARTS
===================================================== */

setInterval(()=>{

const p=
document.createElement("div");

p.className="particle";


const icons=[
"❤️","💙","🩷","💕","💖","✨"
];


p.innerText=
icons[
Math.floor(
Math.random()*icons.length
)
];


p.style.left=
Math.random()*100+
"%";


p.style.fontSize=
(18+
Math.random()*25)+
"px";


p.style.animationDuration=
(5+
Math.random()*6)+
"s";


document
.getElementById("particles")
.appendChild(p);


setTimeout(
()=>p.remove(),
12000
);

},600);

</script>

</body>
</html>
