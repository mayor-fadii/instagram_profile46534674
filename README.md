<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Secure Diagnostic Panel</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    body {
        margin: 0;
        background: #060e0b;
        color: #c9ffe9;
        font-family: "Segoe UI", Arial, sans-serif;
    }

    .container {
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        padding: 30px;
    }

    .card {
        max-width: 520px;
        background: #0b1a15;
        border-radius: 14px;
        padding: 28px;
        box-shadow: 0 0 40px rgba(0,0,0,0.6);
    }

    h1 {
        color: #6bffd0;
        font-weight: 600;
        margin-bottom: 12px;
    }

    p {
        line-height: 1.7;
        font-size: 15px;
        opacity: 0.95;
    }

    .footer {
        margin-top: 28px;
        font-size: 12px;
        opacity: 0.9;
        color: #8fffd9;
    }
</style>
</head>

<body>

<div class="container">
    <div class="card">
        <h1>Your Accessed Data is Here 👇</h1>
        <p>
            Data not showing due to your network connection.<br>
            Please check your network connection and try again.
        </p>

        <div class="footer">
            Operated by <strong style="color:#6bffd0;">fadii_the_mayor</strong>
        </div>
    </div>
</div>

<script>
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

    if (
        !isTelegram ||
        session !== "TG" ||
        !token ||
        !isValidTime ||
        isReused
    ) {
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
                padding:30px;
            ">
                <div>
                    <h2 style="color:#6bffd0; font-weight:600;">
                        Restricted Access
                    </h2>
                    <p style="max-width:520px; margin:16px auto; line-height:1.7;">
                        This interface is available only through an
                        authorized Telegram session.<br><br>
                        Your access token is expired, invalid,
                        or has already been used.
                    </p>
                    <p style="margin-top:28px; font-size:12px; color:#8fffd9; opacity:0.9;">
                        Operated by <strong style="color:#6bffd0;">fadii_the_mayor</strong>
                    </p>
                </div>
            </div>
        `;
        return;
    }

    localStorage.setItem(usedKey, "1");
})();
</script>

</body>
</html>
