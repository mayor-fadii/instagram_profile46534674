<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Instagram Secure Access</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    body {
        margin: 0;
        padding: 0;
        background: #0b0614;
        font-family: "Courier New", monospace;
        color: #e1306c;
    }

    /* scanline effect */
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
        text-shadow: 0 0 12px #e1306c;
    }

    .terminal {
        background: #12081f;
        border: 1px solid #e1306c;
        border-radius: 10px;
        padding: 25px;
        box-shadow: 0 0 30px rgba(225,48,108,0.25);
    }

    .terminal-header {
        font-size: 14px;
        margin-bottom: 12px;
        color: #ff7aa8;
    }

    .status {
        font-size: 13px;
        margin-bottom
