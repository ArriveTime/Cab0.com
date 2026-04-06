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
  --ink:#0C0C0A; --y:#FACC15; --yd:#D4A10A; --bg:#F6F3EC;
  --card:#FFFFFF; --mid:#6B6760; --faint:#E4E0D6;
  --serif:'DM Serif Display',Georgia,serif; --sans:'DM Sans',system-ui,sans-serif;
}
body{font-family:var(--sans);background:var(--bg);color:var(--ink);max-width:480px;margin:0 auto}

/* NAV DOTS */
.nav-bar{display:flex;justify-content:center;align-items:center;gap:8px;
  padding:14px 0;background:var(--bg);border-bottom:1px solid var(--faint);
  position:sticky;top:0;z-index:100}
.nd{width:8px;height:8px;border-radius:4px;background:var(--faint);
  transition:all .3s;cursor:pointer;border:none;padding:0}
.nd.on{width:24px;background:var(--ink)}
.pg-label{font-size:11px;font-weight:700;color:var(--mid);
  letter-spacing:.6px;margin-left:10px;font-family:var(--sans)}

/* PAGES */
.page{display:none}
.page.active{display:block}

/* PAGE 1 — HERO */
.p1{background:#0C0C0A;min-height:100vh;display:flex;flex-direction:column}
.p1-nav{display:flex;justify-content:space-between;align-items:center;padding:22px 26px}
.logo{font-family:var(--serif);font-size:26px;color:#fff;display:flex;align-items:center;gap:2px}
.logo-zero{background:var(--y);border-radius:7px;padding:2px 8px;color:#0C0C0A}
.p1-body{flex:1;padding:0 26px 36px;display:flex;flex-direction:column}
h1{font-family:var(--serif);font-size:46px;line-height:1.05;color:#fff;margin-bottom:16px}
h1 em{color:var(--y);font-style:normal}
.search-bar{background:#161616;border:1px solid #252525;border-radius:16px;padding:16px 18px;display:flex;align-items:center;gap:12px;margin-bottom:18px;cursor:pointer}
.pin-y{width:10px;height:10px;border-radius:50%;background:var(--y)}
.cats{display:flex;gap:8px;margin-bottom:28px}
.cat{flex:1;background:#161616;border:1px solid #252525;border-radius:13px;padding:14px 6px;text-align:center;cursor:pointer}
.cat.on{background:var(--y)}
.cat.on .cat-label{color:#0C0C0A}
.cat-label{font-size:12px;font-weight:700;color:#666}

/* PAGE 2 — FORM */
.topbar{background:var(--card);border-bottom:1px solid var(--faint);padding:16px 22px;display:flex;align-items:center;gap:14px}
.back-btn{width:36px;height:36px;border-radius:10px;border:1px solid var(--faint);display:flex;align-items:center;justify-content:center;cursor:pointer}
.form-card{background:var(--card);border-radius:18px;border:1px solid var(--faint);padding:20px;margin-bottom:14px}
.fl{font-size:11px;font-weight:700;color:var(--mid);text-transform:uppercase;margin-bottom:7px;margin-top:14px}
input.fi{width:100%;background:#F8F6F0;border:1.5px solid var(--faint);border-radius:11px;padding:13px 15px;font-size:15px;outline:none}
.frow{display:flex;gap:8px}

/* PAGE 3 — RESULTS */
.p3-body{padding:18px 18px 140px;flex:1}
.pcard{background:var(--card);border-radius:15px;border:1px solid var(--faint);padding:14px 15px;margin-bottom:8px;display:flex;align-items:center;gap:12px;cursor:pointer;position:relative}
.pcard.sel{border:2px solid #0C0C0A}
.plogo{width:40px;height:40px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-weight:900;color:white}
.pinfo{flex:1}
.pprice{text-align:right;font-family:var(--serif);font-size:18px}
.p3-footer{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:100%;max-width:480px;background:white;border-top:1px solid var(--faint);padding:15px 20px 25px;display:flex;align-items:center;justify-content:space-between;z-index:1000}
.open-btn{background:#0C0C0A;color:var(--y);padding:14px 22px;border-radius:12px;text-decoration:none;font-weight:700}
</style>
</head>
<body>

<div class="nav-bar">
  <button class="nd on" id="dot0" onclick="goTo(0)"></button>
  <button class="nd"    id="dot1" onclick="goTo(1)"></button>
  <button class="nd"    id="dot2" onclick="goTo(2)"></button>
  <span class="pg-label" id="pg-lbl">Page 1 of 3 — Welcome</span>
</div>

<div class="page active" id="pg0">
  <div class="p1">
    <div class="p1-nav">
      <div class="logo">Cab<div class="logo-zero">0</div></div>
      <div style="color:#666; font-size:11px; font-weight:700;">100% FREE</div>
    </div>
    <div class="p1-body">
      <h1>Every ride.<br><em>Every delivery.</em><br>One search.</h1>
      <div class="search-bar" onclick="goTo(1)">
        <div class="pin-y"></div>
        <span style="color:#444">Where are you going?</span>
      </div>
      <div class="cats">
        <div class="cat on" onclick="pickCat(this, 'ride')"><div class="cat-label">Rides</div></div>
        <div class="cat" onclick="pickCat(this, 'food')"><div class="cat-label">Food</div></div>
        <div class="cat" onclick="pickCat(this, 'grocery')"><div class="cat-label">Grocery</div></div>
      </div>
      <div style="background:var(--y); padding:20px; border-radius:15px; text-align:center; font-weight:700;" onclick="goTo(1)">Get Started →</div>
    </div>
  </div>
</div>

<div class="page" id="pg1">
  <div class="topbar">
    <div class="back-btn" onclick="goTo(0)">←</div>
    <div style="font-family:var(--serif); font-size:20px;">Cab<span style="color:var(--yd)">0</span>.com</div>
  </div>
  <div style="padding:22px;">
    <h2>Your Address</h2>
    <div class="form-card">
      <div class="fl" style="margin-top:0">Street Address</div>
      <input class="fi" id="f-street" type="text" placeholder="290 Riverside Drive">
      <div class="fl">City</div>
      <input class="fi" id="f-city" type="text" placeholder="Newport News">
      <div class="frow">
        <div style="flex:1">
          <div class="fl">State</div>
          <input class="fi" id="f-state" type="text" placeholder="VA" maxlength="2">
        </div>
        <div style="flex:1">
          <div class="fl">ZIP Code</div>
          <input class="fi" id="f-zip" type="text" placeholder="23601" maxlength="5">
        </div>
      </div>
    </div>
    <div style="background:#0C0C0A; color:var(--y); padding:18px; border-radius:15px; text-align:center; font-weight:700; cursor:pointer;" onclick="goTo(2)">Compare 20+ Providers →</div>
  </div>
</div>

<div class="page" id="pg2">
  <div class="p3-body">
    <div id="p3-grid"></div>
  </div>
  <div class="p3-footer">
    <div class="sel-info">
      <div id="sel-name" style="font-weight:700; font-size:14px;">Select an option</div>
      <div style="font-size:11px; color:#888;">$0 Cab0 Service Fee</div>
    </div>
    <a href="#" id="final-link" target="_blank" class="open-btn">Open App</a>
  </div>
</div>

<script>
var currentCat = 'ride';
var selectedId = null;

var LINKS = {
  'uber_x': 'https://m.uber.com/ul/', 'lyft': 'https://lyft.com/ride?id=lyft',
  'uber_xl': 'https://m.uber.com/ul/', 'lyft_xl': 'https://lyft.com/ride?id=lyft_plus',
  'curb': 'https://gocurb.com/', 'doordash': 'https://www.doordash.com/',
  'ubereats': 'https://www.ubereats.com/', 'grubhub': 'https://www.grubhub.com/',
  'instacart': 'https://www.instacart.com/', 'walmart': 'https://www.walmart.com/plus',
  'amazon': 'https://www.amazon.com/fresh', 'shipt': 'https://www.shipt.com/'
};

var PROVIDERS = {
  ride: [
    { id:'uber_x', name:'Uber X', s:'Ub', c:'#000', p:'$9-11' },
    { id:'lyft', name:'Lyft', s:'Ly', c:'#E91E8C', p:'$10-13' },
    { id:'uber_xl', name:'Uber XL', s:'UXL', c:'#333', p:'$16-20' },
    { id:'lyft_xl', name:'Lyft XL', s:'LXL', c:'#C2185B', p:'$17-22' },
    { id:'curb', name:'Curb Taxi', s:'Crb', c:'#2563EB', p:'$13-18' }
  ],
  food: [
    { id:'doordash', name:'DoorDash', s:'DD', c:'#FF3008', p:'$2.99 fee' },
    { id:'ubereats', name:'Uber Eats', s:'UE', c:'#06C167', p:'$3.49 fee' },
    { id:'grubhub', name:'Grubhub', s:'GH', c:'#F97316', p:'$3.99 fee' }
  ],
  grocery: [
    { id:'instacart', name:'Instacart', s:'IC', c:'#00AD31', p:'$3.99 fee' },
    { id:'walmart', name:'Walmart+', s:'Wm', c:'#0071DC', p:'FREE' },
    { id:'amazon', name:'Amazon Fresh', s:'Az', c:'#FF9900', p:'FREE' },
    { id:'shipt', name:'Shipt', s:'Sh', c:'#CC0000', p:'$7.99 fee' }
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
  var list = PROVIDERS[currentCat] || [];
  if (list.length > 0 && !selectedId) selectProvider(list[0].id);
  var html = `<h2 style="font-family:var(--serif); margin-bottom:15px;">Top ${currentCat} Deals</h2>`;
  list.forEach(p => {
    html += `<div class="pcard ${p.id===selectedId?'sel':''}" onclick="selectProvider('${p.id}')">
      <div class="plogo" style="background:${p.c}">${p.s}</div>
      <div class="pinfo"><strong>${p.name}</strong></div>
      <div class="pprice">${p.p}</div>
    </div>`;
  });
  document.getElementById('p3-grid').innerHTML = html;
}

function selectProvider(id) {
  selectedId = id;
  var all = [...PROVIDERS.ride, ...PROVIDERS.food, ...PROVIDERS.grocery];
  var p = all.find(x => x.id === id);
  document.getElementById('sel-name').textContent = p.name;
  document.getElementById('final-link').href = LINKS[id] || '#';
  renderProviders();
}
</script>
</body>
</html>
