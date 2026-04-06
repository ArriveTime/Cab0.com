<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Cab0.com — Every Ride. Every Delivery. One Search.</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
/* CSS Reset and Variables */
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --ink:#0C0C0A; --y:#FACC15; --yd:#D4A10A; --bg:#F6F3EC;
  --card:#FFFFFF; --mid:#6B6760; --faint:#E4E0D6;
  --serif:'DM Serif Display',Georgia,serif; --sans:'DM Sans',system-ui,sans-serif;
}
body{font-family:var(--sans);background:#0C0C0A;color:#fff;max-width:480px;margin:0 auto;line-height:1.4}

/* NAV */
.nav-bar{display:flex;justify-content:center;align-items:center;gap:8px;padding:14px 0;background:#0C0C0A;border-bottom:1px solid #222;position:sticky;top:0;z-index:100}
.nd{width:8px;height:8px;border-radius:4px;background:#333;transition:all .3s;cursor:pointer;border:none;padding:0}
.nd.on{width:24px;background:var(--y)}
.pg-label{font-size:11px;font-weight:700;color:#666;letter-spacing:.6px;margin-left:10px;text-transform:uppercase}

.page{display:none}
.page.active{display:block}

/* PAGE 1: HERO */
.p1{background:#0C0C0A;min-height:100vh;display:flex;flex-direction:column}
.p1-nav{display:flex;justify-content:space-between;align-items:center;padding:22px 26px}
.logo{font-family:var(--serif);font-size:26px;color:#fff;display:flex;align-items:center;gap:2px}
.logo-zero{background:var(--y);border-radius:7px;padding:2px 8px;color:#0C0C0A}
.p1-body{flex:1;padding:0 26px 36px;display:flex;flex-direction:column}
h1{font-family:var(--serif);font-size:46px;line-height:1.05;color:#fff;margin-bottom:16px}
h1 em{color:var(--y);font-style:normal}
.search-bar{background:#161616;border:1px solid #252525;border-radius:16px;padding:16px 18px;display:flex;align-items:center;gap:12px;margin-bottom:18px;cursor:pointer}
.pin-y{width:10px;height:10px;border-radius:50%;background:var(--y)}
.cats{display:grid;grid-template-columns: 1fr 1fr;gap:8px;margin-bottom:28px}
.cat{background:#161616;border:1px solid #252525;border-radius:13px;padding:14px 6px;text-align:center;cursor:pointer}
.cat.on{background:var(--y)}
.cat.on .cat-label{color:#0C0C0A}
.cat-label{font-size:12px;font-weight:700;color:#666}

/* PAGE 2: FORM */
.topbar{background:#111;border-bottom:1px solid #222;padding:16px 22px;display:flex;align-items:center;gap:14px}
.back-btn{width:36px;height:36px;border-radius:10px;border:1px solid #333;display:flex;align-items:center;justify-content:center;cursor:pointer;color:#fff}
.form-card{background:#161616;border-radius:18px;border:1px solid #222;padding:20px;margin-bottom:14px}
.fl{font-size:11px;font-weight:700;color:#888;text-transform:uppercase;margin-bottom:7px;margin-top:14px}
input.fi{width:100%;background:#000;border:1.5px solid #333;border-radius:11px;padding:13px 15px;font-size:16px;outline:none;color:#fff}

/* PAGE 3: RESULTS */
.sort-strip{display:flex;background:#000;padding:10px 18px;gap:8px;border-bottom:1px solid #222;position:sticky;top:50px;z-index:90}
.sort-btn{flex:1;padding:8px;border-radius:8px;border:1px solid #333;font-size:10px;font-weight:700;background:#000;color:#888;cursor:pointer}
.sort-btn.active{background:var(--y);color:#000;border-color:var(--y)}
.pcard{background:#161616;border-radius:15px;border:1px solid #222;padding:14px 15px;margin-bottom:8px;display:flex;align-items:center;gap:12px;cursor:pointer}
.pcard.sel{border:2px solid var(--y);background:#1a1a1a}
.p3-footer{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:100%;max-width:480px;background:#000;border-top:1px solid #222;padding:15px 20px 25px;display:flex;align-items:center;justify-content:space-between;z-index:1000}
.open-btn{background:var(--y);color:#000;padding:14px 24px;border-radius:12px;text-decoration:none;font-weight:700;font-size:15px}
</style>
</head>
<body>

<div class="nav-bar">
  <button class="nd on" id="dot0" onclick="goTo(0)"></button>
  <button class="nd"    id="dot1" onclick="goTo(1)"></button>
  <button class="nd"    id="dot2" onclick="goTo(2)"></button>
  <span class="pg-label">Cab0 Hub</span>
</div>

<div class="page active" id="pg0">
  <div class="p1">
    <div class="p1-nav">
      <div class="logo">Cab<div class="logo-zero">0</div></div>
      <div style="color:#666; font-size:11px; font-weight:700;">100% FREE</div>
    </div>
    <div class="p1-body">
      <h1>Every ride.<br>Every delivery.<br><em>One search.</em></h1>
      <div class="search-bar" onclick="goTo(1)">
        <div class="pin-y"></div>
        <span style="color:#666">Where are you going?</span>
      </div>
      <div class="cats">
        <div class="cat on" onclick="pickCat(this, 'ride')"><div class="cat-label">Rideshare</div></div>
        <div class="cat" onclick="pickCat(this, 'delivery')"><div class="cat-label">Food/Grocery</div></div>
        <div class="cat" onclick="window.location.href='vegas.html'"><div class="cat-label">Vegas Loop</div></div>
        <div class="cat" onclick="pickCat(this, 'robo')"><div class="cat-label">Robo Taxi</div></div>
      </div>
      <div style="background:var(--y); color:#000; padding:20px; border-radius:15px; text-align:center; font-weight:700; cursor:pointer;" onclick="goTo(1)">Find the best ride →</div>
    </div>
  </div>
</div>

<div class="page" id="pg1">
  <div class="topbar"><div class="back-btn" onclick="goTo(0)">←</div><div class="logo">Cab<span class="logo-zero">0</span></div></div>
  <div style="padding:22px;">
    <h2>Set Destination</h2>
    <div class="form-card">
      <div class="fl">Street Address</div>
      <input class="fi" id="f-street" type="text" placeholder="123 Main St">
      <div class="fl">City, State, Zip</div>
      <input class="fi" id="f-city" type="text" placeholder="Williamsburg, VA 23185">
    </div>
    <div style="background:var(--y); color:#000; padding:18px; border-radius:15px; text-align:center; font-weight:700; cursor:pointer;" onclick="goTo(2)">Compare Providers →</div>
  </div>
</div>

<div class="page" id="pg2">
  <div class="sort-strip">
    <button class="sort-btn active" id="sort-price" onclick="setSort('price')">CHEAPEST</button>
    <button class="sort-btn" id="sort-time" onclick="setSort('time')">FASTEST</button>
  </div>
  <div style="padding:18px 18px 140px;" id="p3-grid"></div>
  <div class="p3-footer">
    <div><div id="sel-name" style="font-weight:700; font-size:15px;">Select Option</div><div style="font-size:11px; color:#666;">No hidden fees</div></div>
    <a href="#" id="final-link" target="_blank" class="open-btn">Open App</a>
  </div>
</div>

<script>
var currentCat = 'ride', currentSort = 'price', selectedId = null;

// UNIVERSAL DEEP LINKS
var LINKS = {
  'uber': 'uber://', 'lyft': 'lyft://', 'doordash': 'doordash://', 
  'ubereats': 'ubereats://', 'instacart': 'instacart://',
  'waymo': 'https://waymo.com/', 'zoox': 'https://zoox.com/'
};

var PROVIDERS = {
  ride: [
    { id:'uber', name:'Uber X', s:'Ub', c:'#000', price:9.50, time:4 },
    { id:'lyft', name:'Lyft', s:'Ly', c:'#FF00BF', price:10.20, time:6 }
  ],
  delivery: [
    { id:'doordash', name:'DoorDash', s:'DD', c:'#FF3008', price:1.99, time:25 },
    { id:'ubereats', name:'Uber Eats', s:'UE', c:'#06C167', price:2.49, time:20 }
  ],
  robo: [
    { id:'waymo', name:'Waymo One', s:'Wy', c:'#00D1B2', price:8.00, time:12 },
    { id:'zoox', name:'Zoox', s:'Zx', c:'#000', price:7.50, time:15 }
  ]
};

function goTo(n) {
  document.querySelectorAll('.page').forEach((p, i) => p.classList.toggle('active', i === n));
  if (n === 2) renderProviders();
}

function pickCat(el, cat) {
  document.querySelectorAll('.cat').forEach(c => c.classList.remove('on'));
  el.classList.add('on');
  currentCat = cat;
  selectedId = null;
}

function setSort(type) {
  currentSort = type;
  document.querySelectorAll('.sort-btn').forEach(b => b.classList.toggle('active', b.id === 'sort-'+type));
  renderProviders();
}

function renderProviders() {
  var list = [...PROVIDERS[currentCat]].sort((a,b) => a[currentSort] - b[currentSort]);
  if (list.length > 0 && !selectedId) selectProvider(list[0].id);
  var html = '';
  list.forEach(p => {
    html += `<div class="pcard ${p.id===selectedId?'sel':''}" onclick="selectProvider('${p.id}')">
      <div style="width:40px;height:40px;background:${p.c};border-radius:8px;display:flex;align-items:center;justify-content:center;font-weight:900;">${p.s}</div>
      <div style="flex:1"><strong>${p.name}</strong><div style="font-size:11px;color:#666">${p.time} min wait</div></div>
      <div style="font-family:var(--serif);font-size:18px;color:var(--y)">$${p.price.toFixed(2)}</div>
    </div>`;
  });
  document.getElementById('p3-grid').innerHTML = html;
}

function selectProvider(id) {
  selectedId = id;
  var p = Object.values(PROVIDERS).flat().find(x => x.id === id);
  if(p) {
    document.getElementById('sel-name').textContent = p.name;
    document.getElementById('final-link').href = LINKS[id] || '#';
    renderProviders();
  }
}
</script>
</body>
</html>
