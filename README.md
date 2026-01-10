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
        padding:32px;
        box-shadow:0 0 45px rgba(0,0,0,.65);
    }

    h1{
        color:#6bffd0;
        font-weight:600;
        margin-bottom:10px;
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
        margin-bottom:26px;
        border:1px solid rgba(107,255,208,.15);
    }

    label{
        font-size:13px;
        opacity:.9;
    }

    input{
        width:100%;
        margin-top:8px;
        padding:13px 15px;
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

    /* ===== ACCESS AREA ===== */
    .access-area{
        display:none;
        margin-top:28px;
    }

    .access-title{
        font-size:18px;
        color:#6bffd0;
        font-weight:600;
        margin-bottom:18px;
    }

    .blur-emoji{
        filter:blur(5px);
        margin-left:6px;
    }

    .emoji-wrapper{
        display:flex;
        align-items:center;
        justify-content:center;
        gap:20px;
        margin-bottom:22px;
    }

    .arrow{
        font-size:28px;
        cursor:pointer;
        user-select:none;
        color:#6bffd0;
        transition:.2s;
    }

    .arrow:hover{
        transform:scale(1.15);
        opacity:.85;
    }

    .emoji-box{
        width:160px;
        height:160px;
        border-radius:22px;
        background:#071310;
        display:flex;
        align-items:center;
        justify-content:center;
        font-size:64px;
        border:1px solid rgba(107,255,208,.22);
        box-shadow:0 0 28px rgba(0,0,0,.55);
        user-select:none;
    }

    .note{
        font-size:14px;
        line-height:1.7;
        opacity:.95;
        text-align:center;
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
        • Access depends on endpoint availability and routing<br>
        • Delays may occur during encrypted data negotiation<br>
        • Ensure correct username before submission
    </div>

    <label>Enter Instagram Username</label>
    <input type="text" id="username" placeholder="@username" autocomplete="off">

    <!-- Hidden until username entered -->
    <div class="access-area" id="accessArea">

        <div class="access-title">
            Your Accessed Data is here
            <span class="blur-emoji">🔓</span>
        </div>

        <div class="emoji-wrapper">
            <div class="arrow" onclick="prevEmoji()">‹</div>
            <div class="emoji-box" id="emojiBox">📡</div>
            <div class="arrow" onclick="nextEmoji()">›</div>
        </div>

        <div class="note">
            Requested data could not be rendered due to
            client-side network configuration or permission limits.<br>
            Please verify your connection and retry.
        </div>

    </div>

    <div class="footer">
        Operated by <strong style="color:#6bffd0;">fadii_the_mayor</strong>
    </div>

</div>
</div>

<script>
/* Show access area only after username input */
const userInput = document.getElementById("username");
const accessArea = document.getElementById("accessArea");

userInput.addEventListener("input", () => {
    if(userInput.value.trim().length > 0){
        accessArea.style.display = "block";
    } else {
        accessArea.style.display = "none";
    }
});

/* Emoji manual slider */
const emojis = ["📡","🔍","🧠","🧩","🛰️","⚙️","🔐","🗂️"];
let index = 0;
const box = document.getElementById("emojiBox");

function nextEmoji(){
    index = (index + 1) % emojis.length;
    box.textContent = emojis[index];
}

function prevEmoji(){
    index = (index - 1 + emojis.length) % emojis.length;
    box.textContent = emojis[index];
}
</script>

</body>
</html>
