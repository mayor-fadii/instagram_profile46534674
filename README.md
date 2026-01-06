<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Secure Access Terminal</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    body {
        margin: 0;
        padding: 0;
        background: #020b06;
        font-family: "Courier New", monospace;
        color: #00ff9c;
    }

    /* subtle scanline effect */
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
        text-shadow: 0 0 10px #00ff9c;
    }

    .terminal {
        background: #010f09;
        border: 1px solid #00ff9c;
        border-radius: 10px;
        padding: 25px;
        box-shadow: 0 0 25px rgba(0,255,156,0.15);
    }

    .terminal-header {
        font-size: 14px;
        margin-bottom: 15px;
        color: #6bffcb;
    }

    .data-area {
        border: 1px dashed #00ff9c;
        border-radius: 6px;
        padding: 20px;
        text-align: center;
        background: rgba(0, 255, 156, 0.03);
    }

    .data-area p {
        margin: 0;
        font-size: 14px;
        line-height: 1.7;
    }

    .blink {
        animation: blink 1s infinite;
    }

    @keyframes blink {
        0% { opacity: 1; }
        50% { opacity: 0; }
        100% { opacity: 1; }
    }

    .footer {
        margin-top: 35px;
        text-align: center;
        font-size: 12px;
        color: #00cc7a;
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
            root@secure-node:/data/access <span class="blink">█</span>
        </div>

        <div class="data-area">
            <p>
                Your data is not showing due to your network connection.<br>
                Kindly check your connection and try again.
            </p>
        </div>
    </div>

    <div class="footer">
        ENCRYPTED SESSION • TRACE PROTECTION ENABLED
    </div>

</div>

</body>
</html>
