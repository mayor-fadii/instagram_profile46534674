<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Instagram Access Tool</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{margin:0;background:#060e0b;color:#e6fff6;font-family:"Segoe UI",Arial,sans-serif}

/* OVERLAY */
#overlay{position:fixed;inset:0;background:rgba(3,10,8,.97);display:flex;align-items:center;justify-content:center;z-index:9999}
.overlay-box{max-width:540px;background:#0b1a15;border-radius:16px;padding:32px;box-shadow:0 0 60px rgba(0,0,0,.8)}
.overlay-box h2{color:#4cffc0;font-weight:600;text-align:center;margin-bottom:12px}
.typing{font-size:13px;opacity:.9;line-height:1.6;min-height:70px}
.legal{margin-top:14px;height:90px;overflow:hidden;background:#050e0b;border-radius:10px;padding:10px;font-size:11px;opacity:.75}
.overlay-box button{margin:22px auto 0;display:block;padding:12px 42px;border:none;border-radius:12px;background:#4cffc0;color:#052019;font-weight:600;cursor:pointer}

/* MAIN UI */
.container{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:30px}
.card{width:100%;max-width:560px;background:#0b1a15;border-radius:16px;padding:30px;box-shadow:0 0 40px rgba(0,0,0,.65)}
h1{color:#4cffc0;font-weight:600}
.sub{font-size:13px;opacity:.9;margin-bottom:22px}
label{font-size:13px;opacity:.9}
input{width:100%;margin-top:8px;padding:13px 14px;border-radius:10px;border:1px solid rgba(76,255,192,.25);background:#050e0b;color:#e6fff6}
button{width:100%;margin-top:16px;padding:13px;border:none;border-radius:12px;background:#4cffc0;color:#052019;font-weight:600;cursor:pointer}
.spinner{width:18px;height:18px;border:3px solid rgba(0,0,0,.25);border-top:3px solid #052019;border-radius:50%;animation:spin 1s linear infinite;display:none}
@keyframes spin{to{transform:rotate(360deg)}}
.wait,.status,.indicator,.logs,.result{display:none}
.wait{text-align:center;margin-top:14px;font-size:13px}
.status{text-align:center;margin-top:10px;font-size:12px;color:#7dffd3}
.indicator{text-align:center;font-size:11px;opacity:.7}
.logs{margin-top:18px;background:#050e0b;border-radius:10px;padding:12px;font-size:12px;font-family:monospace}
.row{display:flex;justify-content:space-between;padding:12px 0;border-bottom:1px solid rgba(255,255,255,.08)}
.value{letter-spacing:2px;color:#4cffc0}
.kernel{text-align:center;margin-top:22px;font-size:11px;opacity:.75;color:#8fffd9}

/* FEEDBACK ROTATOR */
.feedback-box{position:fixed;right:24px;bottom:120px;width:270px;background:#0b1a15;border-radius:14px;padding:14px;box-shadow:0 0 35px rgba(0,0,0,.6)}
.feedback-box h4{margin:0 0 10px;font-size:13px;color:#4cffc0}
.fb-user{color:#8fffd9;font-weight:600;font-size:12px}
.fb-text{font-size:12px;opacity:.85;margin-top:4px}
</style>
</head>

<body>

<!-- OVERLAY -->
<div id="overlay">
<div class="overlay-box">
<h2>Kernel Authority<br>Instagram Access Page</h2>
<div class="typing" id="typing"></div>
<div class="legal" id="legal">
Kernel Authority operates under restricted internal jurisdiction.<br><br>
Any misuse, replication, redistribution, or exploitation of this interface
outside approved inspection scope is strictly prohibited.<br><br>
Violations may result in permanent access suspension, audit logging,
and authority escalation under internal compliance framework.
</div>
<button onclick="enter()">Proceed</button>
</div>
</div>

<!-- MAIN -->
<div class="container">
<div class="card">
<h1>Instagram Access Tool</h1>
<div class="sub">Authorized account inspection interface</div>

<label>Enter Instagram Username</label>
<input id="iguser" placeholder="username">

<button id="btn">
<div class="spinner" id="sp"></div>
<span id="btntxt">Search</span>
</button>

<div class="wait" id="wait"><span id="loadtxt"></span> • <span id="sec">10</span>s</div>
<div class="status" id="status">Connection established • Secure channel active</div>
<div class="indicator" id="indicator">● live inspection in progress</div>

<div class="logs" id="logs">
[ kernel ] resolving user node<br>
[ kernel ] handshake accepted<br>
[ kernel ] access scope verified
</div>

<div class="result" id="res">
<div class="row"><span>Username</span><span class="value">••••••••</span></div>
<div class="row"><span>Email</span><span class="value">••••••••</span></div>
<div class="row"><span>Password</span><span class="value">••••••••</span></div>
</div>

<div class="kernel">Powered by internal kernel authority</div>
</div>
</div>

<!-- FEEDBACK -->
<div class="feedback-box">
<h4>System Feedback</h4>
<div class="fb-user" id="fbUser"></div>
<div class="fb-text" id="fbText"></div>
</div>

<script>
/* Typing */
const text="This interface operates under strict internal authority protocols. Kernel Authority is not responsible for misuse or violation beyond inspection scope. Directive issued by Kernel Fadi.";
let i=0;
const typing=document.getElementById("typing");
(function type(){ if(i<text.length){ typing.textContent+=text.charAt(i++); setTimeout(type,30);} })();

/* Legal scroll */
const legal=document.getElementById("legal");
setInterval(()=>{ legal.scrollTop+=1; if(legal.scrollTop>=legal.scrollHeight) legal.scrollTop=0 },60);

function enter(){document.getElementById("overlay").style.display="none"}

/* Feedback rotate */
const feedbacks=[
["ahmed_munawar","nice webpage hy brother"],
["legend.65","working hy bhai access mil gya 😯 thanks yr bhot zada"],
["Arshad45","how it is possible sir 😬"],
["mr_jutt804","great sir g"],
["cyber_nova","looks like internal system"],
["root_master","clean ui authority level"],
["hashline","next level presentation"],
["null_axis","professional & controlled"]
];
let f=0;
const fu=document.getElementById("fbUser");
const ft=document.getElementById("fbText");
function rotate(){
fu.textContent="@"+feedbacks[f][0];
ft.textContent=feedbacks[f][1];
f=(f+1)%feedbacks.length;
}
rotate(); setInterval(rotate,4000);

/* Existing logic */
const btn=document.getElementById("btn"),sp=document.getElementById("sp"),btntxt=document.getElementById("btntxt"),
wait=document.getElementById("wait"),sec=document.getElementById("sec"),
loadtxt=document.getElementById("loadtxt"),status=document.getElementById("status"),
indicator=document.getElementById("indicator"),logs=document.getElementById("logs"),
res=document.getElementById("res"),iguser=document.getElementById("iguser");
const texts=["Initializing request","Verifying access","Syncing nodes"];
btn.onclick=()=>{
if(!iguser.value.trim())return;
let t=10;btn.disabled=true;sp.style.display="block";btntxt.textContent="Processing";
wait.style.display=status.style.display=indicator.style.display=logs.style.display="block";
res.style.display="none";loadtxt.textContent=texts[0];sec.textContent=t;
const timer=setInterval(()=>{
t--;sec.textContent=t;
if(t===7)loadtxt.textContent=texts[1];
if(t===4)loadtxt.textContent=texts[2];
if(t<=0){clearInterval(timer);sp.style.display="none";wait.style.display=indicator.style.display="none";
res.style.display="block";btntxt.textContent="Completed";btn.disabled=false;}
},1000);
};
</script>

</body>
</html>
