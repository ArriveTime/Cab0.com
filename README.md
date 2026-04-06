<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cab0.com — Every Ride. Every Delivery. One Search.</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --ink:#0C0C0A; --y:#FACC15; --yd:#D4A10A; --bg:#0C0C0A;
  --card:#161616; --mid:#6B6760; --faint:#252525;
  --serif:'DM Serif Display',Georgia,serif; --sans:'DM Sans',system-ui,sans-serif;
}
body{font-family:var(--sans);background:var(--bg);color:#fff;max-width:480px;margin:0 auto}

/* NAV DOTS */
.nav-bar{display:flex;justify-content:center;align-items:center;gap:8px;
  padding:14px 0;background:var(--bg);border-bottom:1px solid var(--faint);
  position:sticky;top:0;z-index:100}
.nd{width:8px;height:8px;border-radius:4px;background:var(--faint);
  transition:all .3s;cursor:pointer;border:none;padding:0}
.nd.on{width:24px;background:var(--y)}

/* PAGES */
.page{display:none}
.page.active{display:block}

/* PAGE 1 — DARK HERO */
.p1{min-height:100vh;display:flex;flex-direction:column;padding:26px}
.p1-nav{display:flex;justify-content:space-between;align-items:center;margin-bottom:40px}
.logo{font-family:var(--sans);font-weight:900;font-size:24px;color:#fff;display:flex;align-items:center;gap:4px}
.logo-zero{background:var(--y);border-radius:6px;padding:2px 6px;color:#000}
.badge{background:rgba(255,255,255,0.1); border:1px solid var(--faint); padding:6px 12px; border-radius:20px; font-size:10px; font-weight:700; color:#888}

h1{font-family:var(--serif);font-size:48px;line-height:1.1;margin-bottom:20px}
h1 em{color:var(--y);font-style:normal}
.hero-sub{color:#888; font-size:15px; line-height:1.5; margin-bottom:30px}

.search-bar{background:#161616;border:1.5px solid var(--faint);border-radius:14px;padding:18px;display:flex;align-items:center;justify-content:space-between;margin-bottom:12px}
.cats{display:flex;gap:8px;margin-bottom:24px}
.cat{flex:1;background:#161616;border:1px solid var(--faint);border-radius:12px;padding:20px 10px;text-align:center;cursor:pointer;transition:0.2s}
.cat.on{background:var(--y);border-color:var(--y)}
.cat.on .cat-label{color:#000}
.cat-label{font-size:12px;font-weight:700;color:#666}

.stats-grid{display:grid; grid-template-columns: 1fr 1fr 1fr; border:1px solid var(--faint); border-radius:14px; margin-bottom:20px}
.stat{padding:15px; text-align:center; border-right:1px solid var(--faint)}
.stat:last-child{border-right:none}
.stat-val{display:block; font-weight:900; font-size:18px}
.stat-label{font-size:9px; text-transform:uppercase; color:#666; font-weight:700}

.cta-btn{background:var(--y); color:#000; padding:20px; border-radius:14px; text-align:center; font-weight:800; font-size:16px; cursor:pointer}

/* PAGE 2 — FORM (LIGHTER THEME FOR INPUT) */
.form-pg{background:#F6F3EC; color:#000; min-height:100vh}
.topbar{background:#fff;border-bottom:1px solid #E4E0D6;padding:16px 22px;display:flex;align-items:center;gap:14px}
.form-card{background:#fff;border-radius:18px;border:1px solid #E4E0D6;padding:20px;margin:20px}
input.fi{width:100%;background:#F8F6F0;border:1.5px solid #E4E0D6;border-radius:11px;padding:13px 15px;font-size:15px;outline:none;margin-bottom:10px}

/* PAGE 3 — RESULTS */
.p3-body{padding:18px; background:#F6F3EC; color:#000; min-height:100vh}
.pcard{background:#fff;border-radius:15px;border:1px solid #E4E0D6;padding:14px 15px;margin-bottom:8px;display:flex;align-items:center;gap:12px;cursor:pointer}
.pcard.sel{border:2px solid #000}
.plogo{width:40px;height:40px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-weight:900;color:white}
.pprice{text-align:right;font-family:var(--serif);font-size:18px}
.p3-footer{position:fixed;bottom:0;width:100%;max-width:480px;background:#fff;border-top:1px solid #E4E0D6;padding:15px 20px 25px;display:flex;align-items:center;justify-content:space-between}
</style>
</head>
<body>

<div class="nav-bar">
  <button class="nd on" id="dot0" onclick="goTo(0)"></button>
  <button class="nd"    id="dot1" onclick="goTo(1)"></button>
  <button class="nd"    id="dot2" onclick="goTo(2)"></button>
</div>

<div class="page active" id="pg0">
  <div class="p1">
    <div class="p1-nav">
      <div class="logo">Cab<div class="logo-zero">0</div>.com</div>
      <div class="badge">100% FREE</div>
    </div>
    <div class="badge" style="width:fit-content; margin-bottom:15px">● No fees · No sign-up · No API keys</div>
    <h1>Every ride.<br><em style="color:var(--y)">Every delivery.</em><br>One search.</h1>
    <p class="hero-sub">Compare Uber, Lyft, DoorDash, Instacart and 16 more platforms side by side — instantly. Cab0 is completely free, always.</p>
    
    <div class="search-bar" onclick="goTo(1)">
      <span style="color:#444">Where are you going?</span>
      <div style="background:var(--y); padding:6px; border-radius:6px; color:#000">→</div>
    </div>

    <div class="cats">
      <div class="cat on" onclick="pickCat(this, 'ride')"><div class="cat-label">Rides</div></div>
      <div class="cat" onclick="pickCat(this, 'food')"><div class="cat-label">Food</div></div>
      <div class="cat" onclick="pickCat(this, 'grocery')"><div class="cat-label">Grocery</div></div>
    </div>

    <div class="stats-grid">
      <div class="stat"><span class="stat-val">20</span><span class="stat-label">Providers</span></div>
      <div class="stat"><span class="stat-val">$0</span><span class="stat-label">Cab0 Fee</span></div>
      <div class="stat"><span class="stat-val">3</span><span class="stat-label">Taps to Book</span></div>
    </div>

    <div class="cta-btn" onclick="goTo(1)">Get started — it's free →</div>
  </div>
</div>

<div class="page" id="pg1">
  <div class="form-pg">
    <div class="topbar">
      <div class="logo" style="color:#000">Cab<div class="logo-zero">0</div></div>
      <div style="margin-left:auto; font-size:11px; font-weight:700">STEP 1 OF 2</div>
    </div>
    <div class="form-card">
      <h2 style="margin-bottom:8px">Set your home address</h2>
      <p style="font-size:13px; color:#666; margin-bottom:20px">Save it once — Cab0 pre-fills your pickup every time.</p>
      
      <div style="background:#F8F6F0; border:1px solid #E4E0D6; border-radius:12px; padding:15px; margin-bottom:20px; display:flex; align-items:center; gap:10px; cursor:pointer">
        <div style="background:#000; padding:6px; border-radius:6px">📍</div>
        <div style="font-size:13px; font-weight:700">Use my current location</div>
      </div>

      <div style="font-size:11px; font-weight:700; color:#888; text-transform:uppercase; margin-bottom:8px">Street Address</div>
      <input class="fi" id="f-street" type="text" placeholder="290 Riverside Drive">
      
      <div style="font-size:11px; font-weight:700; color:#888; text-transform:uppercase; margin-bottom:8px">City</div>
      <input class="fi" id="f-city" type="text" placeholder="Newport News">
      
      <div style="display:flex; gap:10px">
        <div style="flex:1">
          <div style="font-size:11px; font-weight:700; color:#888; text-transform:uppercase; margin-bottom:8px">State</div>
          <input class="fi" id="f-state" type="text" placeholder="VA">
        </div>
        <div style="flex:1">
          <div style="font-size:11px; font-weight:700; color:#888; text-transform:uppercase; margin-bottom:8px">ZIP Code</div>
          <input class="fi" id="f-zip" type="text" placeholder="23601">
        </div>
      </div>
      <div class="cta-btn" onclick="goTo(2)" style="margin-top:10px">Compare All Rates →</div>
    </div>
  </div>
</div>

<div class="page" id="pg2">
  <div class="p3-body">
    <div id="p3-grid"></div>
  </div>
  <div class="p3-footer">
    <div class="sel-info">
      <div id="sel-name" style="font-weight:700; font-size:14px; color:#000">Select Provider</div>
      <div style="font-size:11px; color:#888;">Optimized for your area</div>
    </div>
    <a href="#" id="final-link" target="_blank" style="background:#000; color:var(--y); padding:14px 22px; border-radius:12px; text-decoration:none; font-weight:700">Launch App</a>
  </div>
</div>

<script>
var currentCat = 'ride';
var selectedId = null;

var PROVIDERS = {
  ride: [
    { id:'waymo', name:'Waymo (Autonomous)', s:'W', c:'#00D1FF', p:'$8.50', n:8.5 },
    { id:'uber_x', name:'Uber X', s:'Ub', c:'#000', p:'$9.20', n:9.2 },
    { id:'lyft', name:'Lyft', s:'Ly', c:'#E91E8C', p:'$10.00', n:10.0 },
    { id:'cruise', name:'Cruise (Robotaxi)', s:'Cr', c:'#FF4D00', p:'$11.00', n:11.0 },
    { id:'curb', name:'Curb Taxi', s:'Cb', c:'#2563EB', p:'$13.50', n:13.5 }
  ],
  food: [
    { id:'doordash', name:'DoorDash', s:'Dd', c:'#FF3008', p:'$2.99 fee', n:2.99 },
    { id:'ubereats', name:'Uber Eats', s:'Ue', c:'#06C167', p:'$3.49 fee', n:3.49 }
  ],
  grocery: [
    { id:'walmart', name:'Walmart+', s:'W+', c:'#0071DC', p:'FREE', n:0 },
    { id:'amazon', name:'Amazon Fresh', s:'Az', c:'#FF9900', p:'FREE', n:0.1 },
    { id:'instacart', name:'Instacart', s:'Ic', c:'#00AD31', p:'$3.99 fee', n:3.99 }
  ]
};

function goTo(n) {
  document.querySelectorAll('.page').forEach((p, i) => p.classList.toggle('active', i === n));
  document.querySelectorAll('.nd').forEach((d, i) => d.classList.toggle('on', i === n));
  if (n === 2) renderProviders();
  window.scrollTo(0,0);
}

function pickCat(el, cat) {
  document.querySelectorAll('.cat').forEach(c => c.classList.remove('on'));
  el.classList.add('on');
  currentCat = cat;
}

function renderProviders() {
  var list = (PROVIDERS[currentCat] || []).sort((a,b) => a.n - b.n);
  if (list.length > 0 && !selectedId) selectProvider(list[0].id);
  
  var html = `<h2 style="font-family:var(--serif); margin-bottom:18px; color:#000">Compare ${currentCat}</h2>`;
  list.forEach(p => {
    html += `<div class="pcard ${p.id===selectedId?'sel':''}" onclick="selectProvider('${p.id}')">
      <div class="plogo" style="background:${p.c}">${p.s}</div>
      <div class="pinfo" style="color:#000; flex:1"><strong>${p.name}</strong></div>
      <div class="pprice" style="color:#000">${p.p}</div>
    </div>`;
  });
  document.getElementById('p3-grid').innerHTML = html;
}

function selectProvider(id) {
  selectedId = id;
  var all = Object.values(PROVIDERS).flat();
  var p = all.find(x => x.id === id);
  document.getElementById('sel-name').textContent = p.name;
  renderProviders();
}
</script>
</body>
</html>
