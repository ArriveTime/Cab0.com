<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cab0.com — Every Ride. Every Delivery. One Search.</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
/* ALL YOUR GRAPHICS & STYLING */
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --ink:#0C0C0A; --y:#FACC15; --yd:#D4A10A; --bg:#F6F3EC;
  --card:#FFFFFF; --mid:#6B6760; --faint:#E4E0D6;
  --serif:'DM Serif Display',Georgia,serif; --sans:'DM Sans',sans-serif;
}
body{font-family:var(--sans);background:var(--bg);color:var(--ink);max-width:480px;margin:0 auto}

/* NAVIGATION */
.nav-bar{display:flex;justify-content:center;align-items:center;gap:8px;padding:14px 0;background:var(--bg);border-bottom:1px solid var(--faint);position:sticky;top:0;z-index:100}
.nd{width:8px;height:8px;border-radius:4px;background:var(--faint);border:none;cursor:pointer}
.nd.on{width:24px;background:var(--ink)}
.pg-label{font-size:11px;font-weight:700;color:var(--mid);margin-left:10px}

/* PAGE DISPLAY LOGIC */
.page{display:none}
.page.active{display:block}

/* STYLING FOR CARDS AND BUTTONS */
.logo{font-family:var(--serif);font-size:26px;display:flex;align-items:center;gap:2px}
.logo-zero{background:var(--y);border-radius:7px;padding:2px 8px;color:#0C0C0A}
.p1{background:#0C0C0A;min-height:100vh;padding:26px;color:white}
h1{font-family:var(--serif);font-size:46px;line-height:1.05;margin:20px 0}
h1 em{color:var(--y);font-style:normal}
.search-bar{background:#161616;border:1px solid #252525;border-radius:16px;padding:16px;display:flex;align-items:center;margin-top:30px;cursor:pointer}
.pcard{background:var(--card);border-radius:15px;border:1px solid var(--faint);padding:14px;margin-bottom:8px;display:flex;align-items:center;gap:12px;cursor:pointer}
.pcard.sel{border:2px solid var(--ink)}
.plogo{width:40px;height:40px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-weight:900;color:white}
.p3-footer{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:100%;max-width:480px;background:white;padding:15px;display:flex;align-items:center;justify-content:space-between;border-top:1px solid var(--faint)}
.open-btn{background:var(--ink);color:var(--y);padding:12px 20px;border-radius:12px;text-decoration:none;font-weight:700}
</style>
</head>
<body>

<div class="nav-bar">
  <button class="nd on" onclick="goTo(0)"></button>
  <button class="nd" onclick="goTo(1)"></button>
  <button class="nd" onclick="goTo(2)"></button>
  <span class="pg-label" id="pg-lbl">Page 1 of 3 — Welcome</span>
</div>

<div class="page active" id="pg0">
  <div class="p1">
    <div class="logo">Cab<div class="logo-zero">0</div>.com</div>
    <h1>Every ride.<br><em>Every delivery.</em><br>One search.</h1>
    <p style="color:#777">Compare 20+ platforms instantly. Free forever.</p>
    <div class="search-bar" onclick="goTo(1)">
      <div style="width:10px;height:10px;background:var(--y);border-radius:50%;margin-right:10px"></div>
      <span style="color:#444">Where are you going?</span>
    </div>
  </div>
</div>

<div class="page" id="pg1">
  <div style="padding:20px">
    <h2 style="font-family:var(--serif);font-size:30px">Set your home address</h2>
    <p style="color:var(--mid);margin-bottom:20px">Save it once — we pre-fill your pickup.</p>
    <input type="text" placeholder="Street Address" style="width:100%;padding:15px;border-radius:10px;border:1px solid var(--faint);margin-bottom:10px">
    <button onclick="goTo(2)" style="width:100%;padding:15px;background:var(--ink);color:var(--y);border-radius:10px;font-weight:700;border:none">Save & Continue</button>
  </div>
</div>

<div class="page" id="pg2">
  <div style="padding:15px" id="grid"></div>
  <div class="p3-footer">
    <div>
      <div id="sel-name" style="font-weight:700">Select an option</div>
      <div style="font-size:12px;color:var(--mid)">$0 Cab0 Fee</div>
    </div>
    <a href="#" id="final-link" target="_blank" class="open-btn">Open App →</a>
  </div>
</div>

<script>
var PROVIDERS = [
  { id:'uber', name:'Uber X', s:'Ub', c:'#000', link:'https://m.uber.com/ul/' },
  { id:'lyft', name:'Lyft', s:'Ly', c:'#E91E8C', link:'https://lyft.com/ride?id=lyft' },
  { id:'dash', name:'DoorDash', s:'DD', c:'#FF3008', link:'https://www.doordash.com/' }
];

function goTo(n) {
  document.querySelectorAll('.page').forEach((p, i) => p.classList.toggle('active', i === n));
  document.querySelectorAll('.nd').forEach((d, i) => d.classList.toggle('on', i === n));
  document.getElementById('pg-lbl').textContent = "Page " + (n+1) + " of 3";
  if (n === 2) render();
}

function render() {
  let html = '';
  PROVIDERS.forEach(p => {
    html += `<div class="pcard" onclick="select('${p.id}')">
      <div class="plogo" style="background:${p.c}">${p.s}</div>
      <div style="flex:1"><strong>${p.name}</strong></div>
      <div style="color:var(--mid)">$9-$12</div>
    </div>`;
  });
  document.getElementById('grid').innerHTML = html;
}

function select(id) {
  let p = PROVIDERS.find(x => x.id === id);
  document.getElementById('sel-name').textContent = p.name;
  document.getElementById('final-link').href = p.link;
  // Visual feedback for selection
  document.querySelectorAll('.pcard').forEach(c => c.style.borderColor = 'var(--faint)');
  event.currentTarget.style.borderColor = 'var(--ink)';
}
</script>
</body>
</html>
