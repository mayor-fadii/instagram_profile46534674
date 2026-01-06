<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Instagram Accessed Successfully</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    body{
        margin:0;
        background:#060e0b;
        font-family:"Segoe UI", Roboto, Arial, sans-serif;
        color:#c9ffe9;
    }

    body::before{
        content:"";
        position:fixed;
        inset:0;
        background:repeating-linear-gradient(
            to bottom,
            rgba(0,255,170,0.02),
            rgba(0,255,170,0.02) 1px,
            transparent 1px,
            transparent 5px
        );
        pointer-events:none;
    }

    .container{
        max-width:900px;
        margin:70px auto;
        padding:30px;
    }

    .title{
        text-align:center;
        font-size:26px;
        font-weight:600;
        margin-bottom:10px;
        color:#e6fff5;
    }

    .subtitle{
        text-align:center;
        font-size:14px;
        color:#9fffd8;
        margin-bottom:35px;
    }

    .panel{
        background:#0a1612;
        border:1px solid #1effb0;
        border-radius:14px;
        padding:30px;
        box-shadow:0 0 40px rgba(30,255,176,0.15);
    }

    .panel-header{
        font-size:14px;
        color:#7dffd1;
        margin-bottom:18px;
    }

    .status{
        font-size:14px;
        line-height:1.8;
        margin-bottom:22px;
    }

    .ok{ color:#4dffb4; }

    .analysis{
        border-top:1px solid rgba(30,255,176,0.3);
        padding-top:22px;
        margin-top:22px;
        font-size:14px;
        line-height:1.9;
        color:#eafff7;
    }

    .timer{
        font-weight:600;
        color:#6bffd0;
    }

    .footer{
        margin-top:38px;
        text-align:center;
        font-size:12px;
        color:#8fffd9;
        opacity:0.9;
        letter-spacing:0.4px;
    }

    .footer strong{
        color:#6bffd0;
        font-weight:600;
    }
</style>
</head>

<body>

<div class="container">

    <div class="title">
        Instagram Accessed Successfully
    </div>

    <div class="subtitle">
        Encrypted session established • Environment analysis in progress
    </div>

    <div class="panel">

        <div class="panel-header">
            Session Overview
        </div>

        <div class="status">
            <div class="ok">✔ Core servers responding within normal latency</div>
            <div class="ok">✔ Authentication scope verified</div>
            <div class="ok">✔ Secure transport layer established</div>
            <div class="ok">✔ Access permissions validated</div>
        </div>

        <div id="analysisBox" class="analysis">
            <span id="analysisText">Initializing diagnostics…</span><br><br>
            Estimated completion time:
            <span class="timer" id="countdown">01:00</span>
        </div>

    </div>

    <div class="footer">
        Maintained by <strong>fadii_the_mayor</strong> • Secure Systems Operator
    </div>

</div>

<script>
    let timeLeft = 60;

    const countdownEl = document.getElementById("countdown");
    const analysisBox = document.getElementById("analysisBox");
    const analysisText = document.getElementById("analysisText");

    const steps = [
        "Detecting server response channels…",
        "Validating authentication tokens…",
        "Analyzing encrypted data routes…",
        "Inspecting client-side network stability…",
        "Checking VPN / proxy interference…",
        "Synchronizing regional access nodes…",
        "Reviewing client environment restrictions…",
        "Finalizing diagnostic report…"
    ];

    let stepIndex = 0;

    const timer = setInterval(() => {
        timeLeft--;

        let minutes = Math.floor(timeLeft / 60);
        let seconds = timeLeft % 60;

        countdownEl.textContent =
            String(minutes).padStart(2, "0") + ":" +
            String(seconds).padStart(2, "0");

        // rotate professional analysis text
        analysisText.textContent = steps[stepIndex % steps.length];
        stepIndex++;

        if (timeLeft <= 0) {
            clearInterval(timer);
            analysisBox.innerHTML = `
                <strong>Diagnostic Result:</strong><br><br>
                The system is operating normally and no faults were detected on
                the service side during this session.<br><br>
                The requested Instagram data could not be rendered due to
                restrictions identified within the client environment.
                This commonly occurs when local network routing, VPN usage,
                DNS filtering, or regional traffic policies interfere with
                encrypted data synchronization.<br><br>
                Please review your local connection and environment
                configuration before attempting again.
            `;
        }
    }, 1000);
</script>

</body>
</html>
