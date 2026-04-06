<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Cab0.com — Every Ride. One Search.</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
<style>
/* 1. RESET & BASE STYLES */
*{box-sizing:border-box; margin:0; padding:0;}
:root{
  --ink:#0C0C0A; --y:#FACC15; --yd:#D4A10A; --bg:#F6F3EC;
  --card:#FFFFFF; --mid:#6B6760; --faint:#E4E0D6;
  --serif:'DM Serif Display', Georgia, serif; --sans:'DM Sans', sans-serif;
}
html, body { height: 100%; overflow-x: hidden; background: var(--bg); }
body{ font-family: var(--sans); color: var(--ink); max-width: 480px; margin: 0 auto; display: flex; flex-direction: column; }

/* 2. NAVIGATION BAR (Sticky at top) */
.nav-bar{ display:flex; justify-content:center; align-items:center; gap:8px; padding:15px; background:var(--bg); border-bottom:1px solid var(--faint); position:sticky; top:0; z-index:100; }
.nd{ width:8px; height:8px; border-radius:4px; background:var(--faint); border:none; cursor:pointer; transition: 0.3s; }
.nd.on{ width:24px; background:var(--ink); }
.pg-label{ font-size:11px; font-weight:700; color:var(--mid); margin-left:10px; text-transform: uppercase; letter-spacing: 0.5px; }

/* 3. PAGE LOGIC */
.page { display:none; width: 100%; min-height: calc(100vh - 50px); padding-bottom: 100px; } /* Extra padding so footer doesn't hide text */
.page.active { display:block; animation: fadeIn 0.3s ease-in; }
@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

/* 4. GRAPHICS & COMPONENTS */
.logo{ font-family:var(--serif); font-size:28px; display:flex; align-items:center; gap:4px; color: white; }
.logo-zero{ background:var(--y); border-radius:7px; padding:0 8px; color:var(--ink); line-height:1.2; }

/* PAGE 1 DESIGN */
.p1-hero{ background:#0C0C0A; padding:40px 26px; color:white; min-height: 50vh; border-radius: 0 0 30px 30px; }
h1{ font-family:var(--serif); font-size:48px; line-height:1.0; margin:20px 0; letter-spacing: -1.5px; }
h1 em{ color:var(--y); font-style:normal; }
.search-btn-large { background:#161616; border:1px solid #252525; border-radius:16px; padding:20px; display:flex; align-items:center; cursor:pointer; margin-top:20px; }

/* PAGE 2 & 3 CARDS */
.card-container { padding: 20px; }
.input-field { width:100%; padding:16px; border-radius:12px; border:1.5px solid var(--faint); margin-bottom:12px; font-size: 16px; outline: none; }
.input-field:focus { border-color: var(--ink); }
.primary-btn { width:100%; padding:18px; background:var(--ink); color:var(--y); border-radius:15px; font-weight:700; border:none; font-size:16px; cursor:pointer; }

.pcard{ background:var(--card); border-radius:16px; border:1px solid var(--faint); padding:16px; margin-bottom:10px; display:flex; align-items:center; gap:15px; cursor:pointer; transition: 0.2s; position: relative;}
.pcard.selected { border: 2px solid var(--ink); box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
.plogo{ width:48px; height:48px; border-radius:12px; display:flex; align-items:center; justify-content:center; font-weight:900; color:white; font-size:18px; }

/* 5. STICKY FOOTER */
.sticky-footer{ position:fixed; bottom:0; left:50%; transform:translateX(-50%); width:100%; max-width:480px; background:white; padding:20px; display:flex; align-items:center; justify-content:space-between; border-top:1px solid var(--faint); box-shadow: 0 -5px 15px rgba(0,0,0,0.05); z-index: 1000; }
.open-btn{ background:var(--ink); color:var(--y); padding:14px 24px; border-radius:14px; text-decoration:none; font-weight:700; font-size: 15px; }
</style>
</head>
<body>

<nav class="nav-bar">
  <button class="nd on" id="dot0" onclick="goTo(0)"></button>
  <button class="nd" id="dot1" onclick="goTo(1)"></button>
  <button class="nd" id="dot2" onclick="goTo(2)"></button>
  <span class="pg-label" id="pg-lbl">Welcome</span>
</nav>

<section class="page active" id="pg0">
  <div class="p1-hero">
    <div class="logo">Cab<div class="logo-zero">0</div></div>
    <h1>Every ride.<br><em>Every delivery.</em><br>One search.</h1>
    <p style="color:#888; font-size:16px; line-height:1.5;">Compare Uber, Lyft, DoorDash and more. Save money instantly.</p>
    <div class="search-btn-large" onclick="goTo(1)">
      <div style="width:12px; height:12px; background:var(--y); border-radius:50%; margin-right:15px"></div>
      <span style="color:#666; font-weight:500;">Where to? Set your address...</span>
    </div>
  </div>
</section>

<section class="page" id="pg1">
  <div class="card-container">
    <h2 style="font-family:var(--serif); font-size:32px; margin-bottom:10px;">Setup Address</h2>
    <p style="color:var(--mid); margin-bottom:25px;">We use this to pre-fill your requests. Nothing is saved on our servers.</p>
    <input type="text" class="input-field" placeholder="Street Address">
    <input type="text" class="input-field" placeholder="City">
    <button class="primary-btn" onclick="goTo(2)">Find Best Prices →</button>
  </div>
</section>

<section class="page" id="pg2">
  <div class="card-container" id="provider-grid">
    </div>
  <div class="sticky-footer">
    <div>
      <div id="sel-name" style="font-weight:700; font-size:16px;">Select a provider</div>
      <div style="font-size:12px; color:var(--mid);">$0.00 Cab0 service fee</div>
    </div>
    <a href="https://m.uber.com/ul/" id="final-link" target="_blank" class="open-btn">Open App</a>
  </div>
</section>

<script>
// The Data - Updated links for Uber, Lyft, and DoorDash
var PROVIDERS = [
  { id:'uber', name:'Uber X', short:'Ub', color:'#000', link:'https://m.uber.com/ul/' },
  { id:'lyft', name:'Lyft', short:'Ly', color:'#E91E8C', link:'https://lyft.com/ride?id=lyft' },
  { id:'dash', name:'DoorDash', short:'DD', color:'#FF3008', link:'https://www.doordash.com/' }
];

var selectedId = 'uber';

function goTo(n) {
  // Toggle Page Visibility
  document.querySelectorAll('.page').forEach((p, i) => p.classList.toggle('active', i === n));
  // Toggle Nav Dots
  document.querySelectorAll('.nd').forEach((d, i) => d.classList.toggle('on', i === n));
  
  // Update Label
  const labels = ["Welcome", "Set Address", "Compare"];
  document.getElementById('pg-lbl').textContent = labels[n];

  if (n === 2) render();
  window.scrollTo(0,0); // Reset scroll to top when changing page
}

function render() {
  let grid = document.getElementById('provider-grid');
  grid.innerHTML = '';
  PROVIDERS.forEach(p => {
    let card = document.createElement('div');
    card.className = `pcard ${p.id === selectedId ? 'selected' : ''}`;
    card.onclick = () => selectProvider(p.id);
    card.innerHTML = `
      <div class="plogo" style="background:${p.color}">${p.short}</div>
      <div style="flex:1">
        <div style="font-weight:700">${p.name}</div>
        <div style="font-size:12px; color:#888">Best match found</div>
      </div>
      <div style="text-align:right">
        <div style="font-weight:700; color:var(--ink)">$9.45</div>
        <div style="font-size:10px; color:#888">estimated</div>
      </div>
    `;
    grid.appendChild(card);
  });
}

function selectProvider(id) {
  selectedId = id;
  let p = PROVIDERS.find(x => x.id === id);
  document.getElementById('sel-name').textContent = p.name;
  document.getElementById('final-link').href = p.link;
  render();
}
</script>

</body>
</html>
