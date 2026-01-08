<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>IG Access Console</title>

<style>
:root{
  --bg:#070a12;
  --panel:#0e1424;
  --panel-2:#0b1020;
  --line:rgba(255,255,255,.06);
  --text:#e7ebff;
  --muted:#9aa3c7;
  --accent:#5c7cff;
  --ok:#2ee59d;
  --warn:#ffcc66;
  --mono: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
}

*{box-sizing:border-box}
html,body{height:100%}
body{
  margin:0;
  background:
    radial-gradient(900px 500px at 10% -10%, #0f1a44 0%, transparent 60%),
    radial-gradient(800px 500px at 110% 10%, #0b1b3a 0%, transparent 55%),
    var(--bg);
  color:var(--text);
  font-family: Inter, system-ui, -apple-system, Segoe UI, sans-serif;
  display:flex; align-items:center; justify-content:center;
}

.wrap{width:100%; max-width:980px; padding:18px}

.shell{
  background:linear-gradient(180deg, #0f1633, var(--panel));
  border:1px solid var(--line);
  border-radius:14px;
  box-shadow:0 40px 120px rgba(0,0,0,.65);
  overflow:hidden;
}

/* header */
.top{
  display:flex; align-items:center; justify-content:space-between;
  padding:14px 18px;
  background:linear-gradient(180deg, #101842, var(--panel-2));
  border-bottom:1px solid var(--line);
}
.brand{
  display:flex; align-items:center; gap:10px; font-weight:600;
}
.dot{width:8px; height:8px; border-radius:50%; background:var(--ok); box-shadow:0 0 10px var(--ok)}
.env{
  font-family:var(--mono); font-size:12px; color:#cfe0ff;
  background:rgba(92,124,255,.12);
  border:1px solid rgba(92,124,255,.25);
  padding:6px 10px; border-radius:10px;
}

/* grid */
.grid{
  display:grid;
  grid-template-columns: 300px 1fr;
  gap:0;
}
.side{
  border-right:1px solid var(--line);
  background:linear-gradient(180deg, #0c1227, #0b1020);
}
.main{padding:18px}

/* sidebar */
.block{padding:16px 18px; border-bottom:1px solid var(--line)}
.kv{display:flex; justify-content:space-between; font-size:13px; color:var(--muted)}
.kv b{color:var(--text); font-weight:500}
.tag{
  display:inline-flex; align-items:center; gap:6px;
  font-family:var(--mono); font-size:12px;
  padding:6px 10px; border-radius:10px;
  background:rgba(46,229,157,.12);
  border:1px solid rgba(46,229,157,.28);
  color:#caffea;
}

/* terminal */
.term{
  background:#060913;
  border:1px solid var(--line);
  border-radius:12px;
  padding:14px;
  font-family:var(--mono);
  font-size:13px;
  line-height:1.6;
}
.line{color:#cfe0ff}
.dim{color:#7f88b8}
.ok{color:#7dffd0}
.warn{color:#ffd27d}

/* cards */
.cards{
  display:grid; grid-template-columns: repeat(3, 1fr);
  gap:14px; margin-top:14px;
}
.card{
  background:linear-gradient(180deg, #0e1530, #0c132b);
  border:1px solid var(--line);
  border-radius:12px; padding:14px;
}
.card h4{margin:0 0 8px; font-size:13px; color:#cfe0ff; font-weight:500}
.card p{margin:0; font-size:12px; color:var(--muted)}

/* footer */
.foot{
  display:flex; justify-content:space-between; align-items:center;
  padding:12px 18px; border-top:1px solid var(--line);
  font-size:12px; color:var(--muted)
}
.lock{display:flex; align-items:center; gap:6px; color:#b7ffea}

@media(max-width:900px){
  .grid{grid-template-columns:1fr}
  .side{border-right:none; border-bottom:1px solid var(--line)}
}
</style>
</head>

<body>
<div class="wrap">
  <div class="shell">

    <div class="top">
      <div class="brand">
        <span class="dot"></span>
        <span>IG Access Console</span>
      </div>
      <div class="env">NODE · EU-WEST · SECURE</div>
    </div>

    <div class="grid">
      <!-- sidebar -->
      <div class="side">
        <div class="block">
          <div class="kv"><span>Status</span><b>Connected</b></div>
          <div class="kv"><span>Scope</span><b>Read-Only</b></div>
          <div class="kv"><span>Channel</span><b>Encrypted</b></div>
        </div>
        <div class="block">
          <span class="tag">SESSION ACTIVE</span>
        </div>
        <div class="block">
          <div class="kv"><span>Latency</span><b>18 ms</b></div>
          <div class="kv"><span>Integrity</span><b>OK</b></div>
          <div class="kv"><span>Risk</span><b>Low</b></div>
        </div>
      </div>

      <!-- main -->
      <div class="main">
        <div class="term">
