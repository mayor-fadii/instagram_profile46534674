<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>WhatsApp Secure Access</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    body {
        margin: 0;
        padding: 0;
        background: #020d0a;
        font-family: "Courier New", monospace;
        color: #25d366;
    }

    body::before {
        content: "";
        position: fixed;
        inset: 0;
        background: repeating-linear-gradient(
            to bottom,
            rgba(255,255,255,0.02),
            rgba(255,255,255,0.02) 1px,
            transparent 1px,
            transparent 3px
        );
        pointer-events: none;
    }

    .container {
        max-width: 850px;
        margin: 70px auto;
        padding: 25px;
    }

    .heading {
        text-align: center;
        font-size: 24px;
        font-weight: bold;
        margin-bottom: 35px;
        text-shadow: 0 0 10px #25d366;
    }

    .terminal {
        background: #010f0b;
        border: 1px solid #25d366;
        border-radius: 10px;
        padding: 25px;
        box-shadow: 0 0 25px rgba(37, 211, 102, 0.2);
    }

    .terminal-header {
        font-size: 14px;
        margin-bottom: 12px;
        color: #6bffb0;
    }

    .status {
        font-size: 13px;
        margin-bottom: 18px;
        color: #2aff9e;
        opacity: 0.9;
    }

    .data-area {
        border: 1px dashed #25d366;
        border-radius: 6px;
        padding: 22px;
        text-align: center;
        background: rgba(37, 211, 102, 0.04);
        min-height: 70px;
    }

    .blink {
        animation: blink 1s infinite;
    }

    @keyframes blink {
        0% { opacity: 1; }
        50% { opacity: 0; }
        100% { opacity: 1; }
    }

    .signature {
        margin-top: 25px;
        text-align: right;
        font-size: 12px;
        opacity: 0.85;
    }

    .footer {
        margin-top: 35px;
        text-align: center;
        font-size: 12px;
        opacity: 0.7;
    }
</style>
</head>

<body>

<div class="container">

    <div class="heading">
        Your Accessed Data is here... 👇🏻
    </div>

    <div class="terminal">
        <div class="terminal-header">
            root@whatsapp-node:/secure/session <span class="blink">█</span>
        </div>

        <div class="status" id="statusText">
            Fetching your data… Please wait (<span id="timer">30</span>s)
        </div>

        <div class="data-area" id="dataBox">
            Establishing encrypted tunnel…
        </div>

        <div class="signature">
            — Authorized Module • fadii_the_mayor
        </div>
    </div>

    <div class="footer">
        WHATSAPP SECURE INTERFACE • TRACE SHIELD ACTIVE
    </div>

</div>

<script>
    let timeLeft = 30;
    const timerEl = document.getElementById("timer");
    const dataBox = document.getElementById("dataBox");
    const statusText = document.getElementById("statusText");

    const countdown = setInterval(() => {
        timeLeft--;
        timerEl.textContent = timeLeft;

        if (timeLeft <= 0) {
            clearInterval(countdown);
            statusText.textContent = "Data retrieval failed";
            dataBox.innerHTML = `
                Your data is not showing due to your network connection.<br>
                Kindly check your connection and try again.
            `;
        }
    }, 1000);
</script>

</body>
</html>
