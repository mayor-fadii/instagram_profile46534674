<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Instagram Access Tool</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    body{
        margin:0;
        background:#060e0b;
        color:#c9ffe9;
        font-family:"Segoe UI", Arial, sans-serif;
    }

    .container{
        min-height:100vh;
        display:flex;
        align-items:center;
        justify-content:center;
        padding:30px;
    }

    .card{
        width:100%;
        max-width:560px;
        background:#0b1a15;
        border-radius:16px;
        padding:30px;
        box-shadow:0 0 45px rgba(0,0,0,.65);
    }

    h1{
        color:#6bffd0;
        font-weight:600;
        margin-bottom:10px;
        letter-spacing:.3px;
    }

    .sub{
        font-size:13px;
        opacity:.9;
        margin-bottom:22px;
        line-height:1.6;
    }

    .conditions{
        background:#071310;
        border-radius:12px;
        padding:16px;
        font-size:13px;
        line-height:1.7;
        margin-bottom:24px;
        border:1px solid rgba(107,255,208,.15);
    }

    label{
        font-size:13px;
        opacity:.9;
    }

    input{
        width:100%;
        margin-top:8px;
        padding:12px 14px;
        border-radius:10px;
        border:none;
        outline:none;
        background:#060e0b;
        color:#c9ffe9;
        font-size:14px;
        border:1px solid rgba(107,255,208,.25);
    }

    input::placeholder{
        color:#7fdcc0;
        opacity:.7;
    }

    .access-title{
        margin-top:26px;
        font-size:18px;
        color:#6bffd0;
        font-weight:600;
    }

    .blur-emoji{
        filter:blur(5px);
        margin-left:6px;
    }

    .emoji-strip{
        display:flex;
        gap:14px;
        overflow-x:auto;
        margin-top:18px;
        padding-bottom:8px;
        scrollbar-width:none;
    }

    .emoji-strip::-webkit-scrollbar{
        display:none;
    }

    .emoji-box{
        min-width:78px;
        height:78px;
        border-radius:14px;
        background:#071310;
        display:flex;
        align-items:center;
        justify-content:center;
        font-size:32px;
        border:1px solid rgba(107,255,208,.18);
        box-shadow:0 0 18px rgba(0,0,0,.4);
        user-select:none;
    }

    .note{
        margin-top:22px;
        font-size:14px;
        line-height:1.7;
        opacity:.95;
    }

    .footer{
        margin-top:30px;
        font-size:12px;
        color:#8fffd9;
        opacity:.9;
        text-align:center;
    }
</style>
</head>

<body>

<div class="container">
<div class="card">

    <h1>Instagram Access Tool</h1>
    <div class="sub">
        Secure diagnostic interface for controlled Instagram account inspection.
    </div>

    <div class="conditions">
        • Access depends on session integrity and network stability<br>
        • Delays may occur due to endpoint restrictions<br>
        • Ensure correct username format before proceeding
    </div>

    <label>Enter Instagram Username</label>
    <input type="text" placeholder="@username" autocomplete="off">

    <div class="access-title">
        Your Accessed Data is here
        <span class="blur-emoji">🔓</span>
    </div>

    <div class="emoji-strip" id="emojiStrip">
        <div class="emoji-box">📡</div>
        <div class="emoji-box">🧩</div>
        <div class="emoji-box">🔍</div>
        <div class="emoji-box">🗂️</div>
        <div class="emoji-box">⚙️</div>
        <div class="emoji-box">🛰️</div>
        <div class="emoji-box">🔐</div>
        <div class="emoji-box">🧠</div>
    </div>

    <div class="note">
        Requested data could not be rendered at this time due to
        client-side network limitations or permission conflicts.<br>
        Please verify your connection and retry.
    </div>

    <div class="footer">
        Operated by <strong style="color:#6bffd0;">fadii_the_mayor</strong>
    </div>

</div>
</div>

<script>
/* ---- Telegram Session Restriction (UNCHANGED LOGIC) ---- */
(function () {
    const ua = navigator.userAgent.toLowerCase();
    const params = new URLSearchParams(window.location.search);

    const session = params.get("session");
    const token   = params.get("token");
    const ts      = parseInt(params.get("ts"), 10);

    const now = Math.floor(Date.now() / 1000);
    const ONE_MINUTE = 60;

    const isTelegram =
        ua.includes("telegram") ||
        ua.includes("telegrambot") ||
        ua.includes("tg");

    const isValidTime = ts && (now - ts) <= ONE_MINUTE;
    const usedKey = "used_token_" + token;
    const isReused = token && localStorage.getItem(usedKey);

    if (!isTelegram || session !== "TG" || !token || !isValidTime || isReused) {
        document.body.innerHTML = `
            <div style="
                background:#060e0b;
                color:#c9ffe9;
                height:100vh;
                display:flex;
                align-items:center;
                justify-content:center;
                font-family:'Segoe UI', Arial, sans-serif;
                text-align:center;
                padding:30px;">
                <div>
                    <h2 style="color:#6bffd0;font-weight:600;">Restricted Access</h2>
                    <p style="max-width:520px;line-height:1.7;">
                        This interface is available only through an
                        authorized Telegram session.<br><br>
                        Your access token is expired, invalid,
                        or already consumed.
                    </p>
                    <p style="font-size:12px;color:#8fffd9;opacity:.9;">
                        Operated by <strong style="color:#6bffd0;">fadii_the_mayor</strong>
                    </p>
                </div>
            </div>`;
        return;
    }
    localStorage.setItem(usedKey,"1");
})();

/* ---- Random emoji rotation ---- */
const emojis = ["📡","🔍","🧠","🧩","🛰️","⚙️","🔐","🗂️"];
setInterval(()=>{
    document.querySelectorAll(".emoji-box").forEach(box=>{
        box.textContent = emojis[Math.floor(Math.random()*emojis.length)];
    });
},1800);
</script>

</body>
</html>
