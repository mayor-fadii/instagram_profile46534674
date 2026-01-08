<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Instagram Secure Access</title>

<style>
    :root {
        --bg: #0b0f1a;
        --card: #12172a;
        --accent: #4f7cff;
        --text: #e6e8f0;
        --muted: #9aa1b2;
        --success: #3ddc97;
    }

    * {
        box-sizing: border-box;
        font-family: "Inter", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
    }

    body {
        margin: 0;
        background: radial-gradient(1200px 600px at 20% 10%, #10163a, var(--bg));
        color: var(--text);
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 20px;
    }

    .container {
        width: 100%;
        max-width: 420px;
    }

    .card {
        background: linear-gradient(180deg, #141a35, var(--card));
        border-radius: 18px;
        padding: 28px;
        box-shadow: 0 30px 80px rgba(0,0,0,0.6);
        border: 1px solid rgba(255,255,255,0.04);
    }

    .brand {
        text-align: center;
        margin-bottom: 24px;
    }

    .brand h1 {
        font-size: 20px;
        font-weight: 600;
        margin: 0;
        letter-spacing: 0.3px;
    }

    .brand p {
        margin: 6px 0 0;
        font-size: 13px;
        color: var(--muted);
    }

    .status {
        display: flex;
        align-items: center;
        gap: 10px;
        background: rgba(79,124,255,0.08);
        border: 1px solid rgba(79,124,255,0.25);
        padding: 12px 14px;
        border-radius: 12px;
        margin-bottom: 18px;
    }

    .dot {
        width: 10px;
        height: 10px;
        background: var(--accent);
        border-radius: 50%;
        box-shadow: 0 0 10px var(--accent);
    }

    .status span {
        font-size: 13px;
        color: #cfd6ff;
    }

    .info {
        font-size: 14px;
        line-height: 1.6;
        color: var(--muted);
        margin-bottom: 22px;
    }

    .info strong {
        color: var(--text);
        font-weight: 500;
    }

    .progress {
        height: 6px;
        background: rgba(255,255,255,0.08);
        border-radius: 10px;
        overflow: hidden;
        margin-bottom: 14px;
    }

    .bar {
        height: 100%;
        width: 72%;
        background: linear-gradient(90deg, var(--accent), #7aa2ff);
        border-radius: 10px;
    }

    .footer {
        display: flex;
        justify-content: space-between;
        font-size: 12px;
        color: var(--muted);
        margin-top: 18px;
    }

    .secure {
        display: flex;
        align-items: center;
        gap: 6px;
        color: var(--success);
        font-weight: 500;
    }

    .divider {
        height: 1px;
        background: rgba(255,255,255,0.06);
        margin: 18px 0;
    }

    .note {
        font-size: 12px;
        color: var(--muted);
        text-align: center;
    }
</style>
</head>

<body>

<div class="container">
    <div class="card">

        <div class="brand">
            <h1>Instagram Secure Access</h1>
            <p>Protected session • Simulation environment</p>
        </div>

        <div class="status">
            <div class="dot"></div>
            <span>Connection established successfully</span>
        </div>

        <div class="info">
            A secure request has been initiated for this Instagram account.
            <br><br>
            <strong>Data visibility:</strong> Limited  
            <br>
            <strong>Session type:</strong> Read-only simulation  
            <br>
            <strong>Risk level:</strong> Minimal
        </div>

        <div class="progress">
            <div class="bar"></div>
        </div>

        <div class="footer">
            <div class="secure">🔒 Encrypted</div>
            <div>v1.0</div>
        </div>

        <div class="divider"></div>

        <div class="note">
            No credentials are collected or stored.  
            This interface is designed for demonstration purposes only.
        </div>

    </div>
</div>

</body>
</html>
