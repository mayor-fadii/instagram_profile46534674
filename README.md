<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Instagram Secure Access</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    body{
        margin:0;
        padding:0;
        background:#0b0614;
        font-family:"Courier New", monospace;
        color:#e1306c;
    }

    /* scanlines */
    body::before{
        content:"";
        position:fixed;
        inset:0;
        background:repeating-linear-gradient(
            to bottom,
            rgba(255,255,255,0.02),
            rgba(255,255,255,0.02) 1px,
            transparent 1px,
            transparent 3px
        );
        pointer-events:none;
    }

    .container{
        max-width:900px;
        margin:60px auto;
        padding:25px;
    }

    .heading{
        text-align:center;
        font-size:26px;
        font-weight:bold;
        margin-bottom:30px;
        text-shadow:0 0 14px #e1306c;
    }

    /* OWNER BADGE — noticeable */
    .owner-badge{
        text-align:center;
        margin-bottom:25px;
    }
    .owner-badge span{
        display:inline-block;
        padding:10px 22px;
        border:1px solid #ff3f86;
        border-radius:30px;
        color:#ff7aa8;
        font-size:14px;
        letter-spacing:1px;
        text-shadow:0 0 12px #ff3f86;
        box-shadow:0 0 25px rgba(255,63,134,0.35);
        background:rgba(225,48,108,0.08);
    }

    .terminal{
        background:#12081f;
        border:1px solid #e1306c;
        border-radius:10px;
        padding:25px;
        box-shadow:0 0 30px rgba(225,48,108,0.25);
    }

    .terminal-header{
        font-size:14px;
        margin-bottom:12px;
        color:#ff7aa8;
    }

    .status{
        font-size:14px;
        margin-bottom:18px;
        color:#ff9cbc;
    }

    .timer{
        font-weight:bold;
        color:#ffd1e1;
        text-shadow:0 0 10px #ff7aa8;
    }

    .data-area{
        border:1px dashed #e1306c;
        border-radius:6px;
        padding:24px;
        text-align:center;
        background:rgba(225,48,108,0.05);
        min-height:80px;
    }

    .blink{ animation:blink 1s infinite; }
    @keyframes blink{
        0%{opacity:1}
        50%{opacity:0}
        100%{opacity:1}
    }

    .footer{
        margin-top:35px;
        text-align:center;
        font-size:12px;
        color:#c77b9b;
        opacity:0.75;
    }
</style>
</head>

<body>

<div class="container">

    <div class="heading">
        Your Accessed Data is here... 👇🏻
    </div>

    <div class="owner-badge">
        <span>AUTHORIZED OPERATOR • fadii_the_mayor</span>
    </div>

    <div class="terminal">
        <div class="terminal-header">
            root@instagram-node:/secure/session <span class="blink">█</span>
        </div>

        <div class="status" id="statusText">
            Fetching Instagram data… Please wait
            (<span class="timer" id="timer">10:00</span>)
        </div>

        <div class="data-area" id="dataBox">
            Initializing encrypted media synchronization…
        </div>
    </div>

    <div class="footer">
        INSTAGRAM SECURE INTERFACE • TRACE PROTECTION ENABLED
    </div>

</div>

<script>
    // 10 minutes = 600 seconds
    let timeLeft = 600;

    const timerEl = document.getElementById("timer");
    const dataBox = document.getElementById("dataBox");
    const statusText = document.getElementById("statusText");

    function formatTime(sec){
        const m = Math.floor(sec / 60);
        const s = sec % 60;
        return `${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}`;
    }

    timerEl.textContent = formatTime(timeLeft);

    const countdown = setInterval(()=>{
        timeLeft--;
        timerEl.textContent = formatTime(timeLeft);

        if(timeLeft <= 0){
            clearInterval(countdown);
            statusText.textContent = "Data retrieval failed";
            dataBox.innerHTML = `
                Your data is not showing due to your network connection.<br>
                Kindly check your connection and try again.
            `;
        }
    },1000);
</script>

</body>
</html>
