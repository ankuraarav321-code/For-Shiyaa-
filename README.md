<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Dear Shiyaa ❤️</title>

<link rel="stylesheet" href="style.css">

<script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>

</head>

<body>

<div class="stars"></div>

<div class="container">

<section class="page active">

<h1>Hiii 🌸</h1>

<lottie-player
src="https://assets5.lottiefiles.com/packages/lf20_x62chJ.json"
background="transparent"
speed="1"
style="width:250px;height:250px"
loop
autoplay>
</lottie-player>

<p>
Bas ek choti si request...
Iss page ko end tak dekh lena. 😊
</p>

<button onclick="nextPage()">Next ➜</button>

</section>

<section class="page">

<h1>💛</h1>

<p>Kya kar rhi ho?</p>

<div class="options">

<button onclick="saveAnswer('Theek hu')">Theek hu</button>

<button onclick="saveAnswer('Mast hu')">Mast hu</button>

<button onclick="saveAnswer('Bore ho rhi')">Bore ho rhi</button>

<button onclick="saveAnswer('Pareshan hu')">Pareshan hu</button>

</div>

<button onclick="nextPage()">Next ➜</button>

</section>

<section class="page">

<h2>Mujhse koi galti hui hai kya?<br>Ya sirf mann nahi tha baat karne ka?</h2>

<div class="options">

<button onclick="saveAnswer('Bas mann nahi tha')">

Bas mann nahi tha

</button>

</div>

<textarea

id="problem"

placeholder="Agar koi aur baat hai to yaha likh do..."

></textarea>

<button onclick="saveProblem()">Next ➜</button>

</section>

<section class="page">

<h2>

Tum pagal ho...

Ye mujhe pata hai 😂

Par agar tumhe lagta hai

main bhi hu?

</h2>

<div class="options">

<button onclick="saveAnswer('Haan 😂')">

Haan

</button>

<button onclick="saveAnswer('Nahi 😂')">

Nahi

</button>

</div>

<button onclick="nextPage()">Next ➜</button>

</section>

<section class="page">

<h1>📝</h1>

<h2>Note For Me (Ankur)</h2>

<textarea

id="note"

placeholder="Jo bhi dil kare likh dena 😊"

></textarea>

<button onclick="saveNote()">

Next ➜

</button>

</section>

<section class="page">

<h1>🌙</h1>

<p>

Theek hai...

Jab tumhari marzi ho tab baat kar lena.

Bas itna yaad rakhna...

Agar kabhi kisi bhi tarah ki help chahiye ho,

main apni taraf se jitni ho sake utni

karne ki koshish karunga.

❤️

</p>

<h2>

Good Night

Dear Shiyaa 🌸

</h2>

<p>

Take Care ✨

</p>

</section>

</div>

<script src="script.js"></script>

<script type="module" src="firebase-config.js"></script>

</body>

</html>*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Poppins',sans-serif;
}

body{

background:linear-gradient(135deg,#ffd6e8,#d8f3ff);

height:100vh;

overflow:hidden;

display:flex;

justify-content:center;

align-items:center;

}

.container{

width:100%;

height:100vh;

position:relative;

overflow:hidden;

}

.page{

position:absolute;

width:100%;

height:100%;

left:100%;

top:0;

display:flex;

flex-direction:column;

justify-content:center;

align-items:center;

padding:30px;

transition:.7s;

text-align:center;

}

.active{

left:0;

}

.prev{

left:-100%;

}

h1{

font-size:40px;

margin-bottom:20px;

color:#ff3d81;

}

h2{

font-size:28px;

margin-bottom:25px;

color:#444;

line-height:1.5;

}

p{

font-size:20px;

line-height:1.8;

color:#555;

margin:20px;

max-width:500px;

}

button{

margin:10px;

padding:15px 35px;

border:none;

border-radius:40px;

font-size:18px;

cursor:pointer;

background:#ff4f8b;

color:white;

transition:.3s;

box-shadow:0 10px 25px rgba(0,0,0,.15);

}

button:hover{

transform:scale(1.08);

background:#ff2e74;

}

.options{

display:flex;

flex-wrap:wrap;

justify-content:center;

gap:15px;

margin-top:20px;

}

textarea{

width:90%;

max-width:420px;

height:140px;

padding:18px;

border:none;

outline:none;

resize:none;

border-radius:18px;

font-size:18px;

margin:20px;

box-shadow:0 10px 25px rgba(0,0,0,.15);

}

.stars{

position:absolute;

width:100%;

height:100%;

overflow:hidden;

pointer-events:none;

}

.stars span{

position:absolute;

display:block;

width:4px;

height:4px;

background:white;

border-radius:50%;

animation:twinkle 4s infinite;

}

@keyframes twinkle{

0%{

opacity:.2;

transform:scale(.5);

}

50%{

opacity:1;

transform:scale(1.5);

}

100%{

opacity:.2;

transform:scale(.5);

}

}

.heart{

position:absolute;

color:#ff5d95;

font-size:20px;

animation:float 7s linear infinite;

}

@keyframes float{

0%{

transform:translateY(100vh) rotate(0deg);

opacity:0;

}

20%{

opacity:1;

}

100%{

transform:translateY(-120vh) rotate(360deg);

opacity:0;

}

}

.fade{

animation:fade .7s;

}

@keyframes fade{

from{

opacity:0;

transform:translateY(40px);

}

to{

opacity:1;

transform:translateY(0);

}

}

@media(max-width:600px){

h1{

font-size:32px;

}

h2{

font-size:23px;

}

p{

font-size:18px;

}

button{

width:90%;

font-size:17px;

}

textarea{

font-size:16px;

}

}const pages = document.querySelectorAll(".page");
let current = 0;

function nextPage() {
    if (current < pages.length - 1) {
        pages[current].classList.remove("active");
        pages[current].classList.add("prev");

        current++;

        pages[current].classList.add("active");
        pages[current].classList.add("fade");
    }
}

// ---------- Save Answers ----------
let answers = {
    mood: "",
    reason: "",
    note: ""
};

function saveAnswer(ans) {
    if (current === 1) {
        answers.mood = ans;
    } else if (current === 3) {
        answers.reason = ans;
    }
}

function saveProblem() {
    answers.reason =
        document.getElementById("problem").value || answers.reason;

    nextPage();
}

function saveNote() {
    answers.note = document.getElementById("note").value;

    if (typeof saveToFirebase === "function") {
        saveToFirebase(answers);
    }

    nextPage();
}

// ---------- Floating Hearts ----------
function createHeart() {

    const heart = document.createElement("div");

    heart.className = "heart";

    heart.innerHTML = "❤";

    heart.style.left = Math.random() * 100 + "%";

    heart.style.fontSize = 15 + Math.random() * 25 + "px";

    heart.style.animationDuration = 4 + Math.random() * 5 + "s";

    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 9000);
}

setInterval(createHeart, 500);

// ---------- Stars ----------
const stars = document.querySelector(".stars");

for (let i = 0; i < 80; i++) {

    const star = document.createElement("span");

    star.style.left = Math.random() * 100 + "%";

    star.style.top = Math.random() * 100 + "%";

    star.style.animationDelay = Math.random() * 5 + "s";

    stars.appendChild(star);
}

// ---------- Prevent Back ----------
history.pushState(null, null, location.href);

window.onpopstate = function () {
    history.go(1);
};// firebase-config.js

import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";
import {
  getFirestore,
  collection,
  addDoc,
  serverTimestamp
} from "https://www.gstatic.com/firebasejs/10.12.2/firebase-firestore.js";

// ---------------- Firebase Config ----------------
// Apne Firebase project ki details yaha paste karo
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};

// ---------------- Initialize ----------------
const app = initializeApp(firebaseConfig);
const db = getFirestore(app);

// ---------------- Save Data ----------------
window.saveToFirebase = async function (data) {
  try {
    await addDoc(collection(db, "responses"), {
      mood: data.mood || "",
      reason: data.reason || "",
      note: data.note || "",
      createdAt: serverTimestamp()
    });

    console.log("Data Saved Successfully ❤️");
  } catch (err) {
    console.error("Firebase Error:", err);
  }
};<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Admin Panel</title>

<link rel="stylesheet" href="style.css">

</head>

<body>

<div class="container">

<div class="page active">

<h1>🔒 Admin Panel</h1>

<p>

Enter Password

</p>

<input

type="password"

id="password"

placeholder="Password"

style="padding:15px;border:none;border-radius:30px;width:280px;text-align:center;font-size:18px;">

<br><br>

<button onclick="login()">

Login

</button>

</div>

<div

id="dashboard"

style="display:none;padding:30px;overflow:auto;height:100vh;">

<h1>

Responses ❤️

</h1>

<div id="responses">

Loading...

</div>

</div>

</div>

<script src="admin.js" type="module"></script>

</body>

</html>import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";
import {
getFirestore,
collection,
getDocs,
query,
orderBy
} from "https://www.gstatic.com/firebasejs/10.12.2/firebase-firestore.js";

// ---------------------
// FIREBASE CONFIG
// ---------------------

const firebaseConfig = {

apiKey:"YOUR_API_KEY",

authDomain:"YOUR_PROJECT.firebaseapp.com",

projectId:"YOUR_PROJECT_ID",

storageBucket:"YOUR_PROJECT.appspot.com",

messagingSenderId:"YOUR_SENDER_ID",

appId:"YOUR_APP_ID"

};

const app = initializeApp(firebaseConfig);

const db = getFirestore(app);

// ---------------------
// CHANGE PASSWORD HERE
// ---------------------

const PASSWORD="CHANGE_ME";

// ---------------------

window.login=function(){

const pass=document.getElementById("password").value;

if(pass!==PASSWORD){

alert("Wrong Password");

return;

}

document.querySelector(".page").style.display="none";

document.getElementById("dashboard").style.display="block";

loadResponses();

}

// ---------------------

async function loadResponses(){

const box=document.getElementById("responses");

box.innerHTML="Loading...";

const q=query(

collection(db,"responses"),

orderBy("createdAt","desc")

);

const snap=await getDocs(q);

box.innerHTML="";

if(snap.empty){

box.innerHTML="<h2>No Responses Yet ❤️</h2>";

return;

}

snap.forEach((doc)=>{

const d=doc.data();

const card=document.createElement("div");

card.style.background="white";

card.style.padding="20px";

card.style.marginBottom="20px";

card.style.borderRadius="20px";

card.style.boxShadow="0 8px 20px rgba(0,0,0,.12)";

card.innerHTML=`

<h2>🌸 New Response</h2>

<p><b>Mood :</b> ${d.mood||"-"}</p>

<p><b>Reason :</b> ${d.reason||"-"}</p>

<p><b>Note :</b><br>${d.note||"-"}</p>

`;

box.appendChild(card);

});

}
