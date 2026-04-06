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
  --ink:#0C0C0A;
  --y:#FACC15;
  --yd:#D4A10A;
  --bg:#F6F3EC;
  --card:#FFFFFF;
  --mid:#6B6760;
  --faint:#E4E0D6;
  --serif:'DM Serif Display',Georgia,serif;
  --sans:'DM Sans',system-ui,sans-serif;
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

/* PAGE 1 — WELCOME */
.p1{background:#0C0C0A;min-height:100vh;display:flex;flex-direction:column}
.p1-nav{display:flex;justify-content:space-between;align-items:center;padding:22px 26px}
.logo{font-family:var(--serif);font-size:26px;color:#fff;
  display:flex;align-items:center;gap:2px;letter-spacing:-1px}
.logo-zero{background:var(--y);border-radius:7px;padding:2px 8px;
  margin-left:1px;font-family:var(--serif);font-size:26px;color:#0C0C0A;line-height:1.3}
.logo-ext{font-family:var(--sans);font-size:12px;color:#444;margin-left:4px;font-weight:600}
.free-chip{background:#161616;border:1px solid #252525;color:#666;
  font-size:11px;font-weight:700;padding:5px 13px;border-radius:20px;letter-spacing:.8px}

.p1-body{flex:1;padding:0 26px 36px;display:flex;flex-direction:column}
.kicker{display:inline-flex;align-items:center;gap:8px;background:#161616;
  border:1px solid #252525;border-radius:20px;padding:6px 14px;
  margin-bottom:26px;align-self:flex-start}
.kicker-dot{width:7px;height:7px;border-radius:50%;background:var(--y)}
.kicker-text{font-size:11px;font-weight:600;color:#666;letter-spacing:.8px}
h1{font-family:var(--serif);font-size:46px;line-height:1.05;
  color:#fff;letter-spacing:-2px;margin-bottom:16px}
h1 em{color:var(--y);font-style:normal}
.p1-sub{font-size:15px;color:#777;line-height:1.65;margin-bottom:32px}

.search-bar{background:#161616;border:1px solid #252525;border-radius:16px;
  padding:16px 18px;display:flex;align-items:center;gap:12px;
  margin-bottom:18px;cursor:pointer;transition:border-color .2s}
.search-bar:hover{border-color:#3a3a3a}
.pin-y{width:10px;height:10px;border-radius:50%;background:var(--y);flex-shrink:0}
.search-ph{font-size:15px;color:#444;flex:1}
.search-btn{width:36px;height:36px;border-radius:10px;background:var(--y);
  display:flex;align-items:center;justify-content:center;
  flex-shrink:0;font-size:16px;font-weight:700;color:#0C0C0A}

.cats{display:flex;gap:8px;margin-bottom:28px}
.cat{flex:1;background:#161616;border:1px solid #252525;border-radius:13px;
  padding:14px 6px;text-align:center;cursor:pointer;transition:all .2s}
.cat.on,.cat:hover{background:var(--y);border-color:var(--y)}
.cat-dot{width:14px;height:14px;border-radius:7px;margin:0 auto 8px;transition:background .2s}
.cat.on .cat-dot,.cat:hover .cat-dot{background:#0C0C0A}
.cat-label{font-size:12px;font-weight:700;color:#666;transition:color .2s}
.cat.on .cat-label,.cat:hover .cat-label{color:#0C0C0A}

.stats{display:flex;border:1px solid #1c1c1c;border-radius:16px;
  overflow:hidden;margin-bottom:22px}
.stat{flex:1;padding:16px 8px;text-align:center;background:#111}
.stat+.stat{border-left:1px solid #1c1c1c}
.stat-n{font-family:var(--serif);font-size:24px;color:#fff;letter-spacing:-1px}
.stat-l{font-size:10px;color:#444;font-weight:700;letter-spacing:.7px;
  text-transform:uppercase;margin-top:3px}

.cta-btn{background:var(--y);border-radius:16px;padding:19px;
  text-align:center;cursor:pointer;margin-bottom:22px;transition:opacity .15s}
.cta-btn:hover{opacity:.92}
.cta-main{font-size:17px;font-weight:700;color:#0C0C0A;letter-spacing:.2px}
.cta-sub{font-size:12px;color:var(--yd);margin-top:3px;font-weight:600}

.proof{display:flex;align-items:center;gap:12px}
.faces{display:flex}
.face{width:30px;height:30px;border-radius:50%;border:2px solid #0C0C0A;
  margin-left:-7px;display:flex;align-items:center;justify-content:center;
  font-size:10px;font-weight:700}
.face:first-child{margin-left:0}
.proof-text{font-size:12px;color:#555;line-height:1.55}
.proof-text strong{color:#888}

/* PAGE 2 — HOME ADDRESS */
.p2{background:var(--bg);min-height:100vh;display:flex;flex-direction:column}
.topbar{background:var(--card);border-bottom:1px solid var(--faint);
  padding:16px 22px;display:flex;align-items:center;gap:14px}
.back-btn{width:36px;height:36px;border-radius:10px;border:1px solid var(--faint);
  display:flex;align-items:center;justify-content:center;
  cursor:pointer;font-size:18px;color:var(--mid);background:var(--card)}
.tb-logo{font-family:var(--serif);font-size:20px;color:var(--ink)}
.tb-logo span{color:var(--yd)}
.tb-step{margin-left:auto;font-size:12px;font-weight:700;color:var(--mid)}

.p2-body{padding:26px 22px;flex:1}
.step-track{display:flex;align-items:center;margin-bottom:30px}
.snode{width:30px;height:30px;border-radius:15px;display:flex;align-items:center;
  justify-content:center;font-size:13px;font-weight:700;flex-shrink:0;z-index:1}
.sline{flex:1;height:2px;background:var(--faint)}
.s-active{background:var(--y);color:#0C0C0A}
.s-future{background:var(--faint);color:var(--mid)}

.eyebrow{font-size:11px;font-weight:700;color:var(--yd);
  letter-spacing:1.2px;text-transform:uppercase;margin-bottom:8px}
h2{font-family:var(--serif);font-size:30px;color:var(--ink);
  letter-spacing:-1px;line-height:1.15;margin-bottom:8px}
.p2-sub{font-size:14px;color:var(--mid);line-height:1.6;margin-bottom:22px}

.detect-bar{display:flex;align-items:center;gap:12px;
  background:#F0EDE4;border:1px solid var(--faint);border-radius:13px;
  padding:14px 16px;margin-bottom:14px;cursor:pointer}
.detect-bar:hover{border-color:var(--ink)}
.detect-icon{width:32px;height:32px;border-radius:9px;background:#0C0C0A;
  display:flex;align-items:center;justify-content:center;flex-shrink:0}
.detect-title{font-size:14px;font-weight:700;color:var(--ink)}
.detect-sub{font-size:11px;color:var(--mid);margin-top:2px}

.form-card{background:var(--card);border-radius:18px;border:1px solid var(--faint);
  padding:20px;margin-bottom:14px}
.fl{font-size:11px;font-weight:700;color:var(--mid);letter-spacing:.8px;
  text-transform:uppercase;margin-bottom:7px;margin-top:14px}
.fl:first-child{margin-top:0}
input.fi{width:100%;background:#F8F6F0;border:1.5px solid var(--faint);
  border-radius:11px;padding:13px 15px;font-size:15px;color:var(--ink);
  font-family:var(--sans);outline:none;transition:border-color .2s}
input.fi:focus{border-color:var(--ink)}
.frow{display:flex;gap:8px}
.fgroup{flex:1;display:flex;flex-direction:column}

.why-box{background:#FDFBF5;border:1px solid var(--faint);
  border-radius:13px;padding:16px;margin-bottom:18px}
.why-title{font-size:11px;font-weight:700;color:var(--mid);
  letter-spacing:.6px;text-transform:uppercase;margin-bottom:10px}
.why-row{display:flex;align-items:flex-start;gap:9px;margin-bottom:8px}
.why-dot{width:7px;height:7px;border-radius:50%;background:var(--y);
  flex-shrink:0;margin-top:5px}
.why-text{font-size:13px;color:var(--mid);line-height:1.55}

.p2-cta{background:#0C0C0A;border-radius:15px;padding:18px;
  text-align:center;cursor:pointer;margin-bottom:10px;transition:opacity .15s}
.p2-cta:hover{opacity:.9}
.p2-cta-text{font-size:16px;font-weight:700;color:var(--y)}
.skip{text-align:center;padding:12px;font-size:13px;color:var(--mid);cursor:pointer}
.skip:hover{color:var(--ink)}

/* PAGE 3 — PROVIDER COMPARISON */
.p3{background:var(--bg);min-height:100vh;display:flex;flex-direction:column}
.p3-topbar{background:var(--card);border-bottom:1px solid var(--faint);
  padding:14px 20px;display:flex;align-items:center;gap:12px}
.free-badge{margin-left:auto;background:#F0FDF4;border:1px solid #86efac;
  border-radius:20px;padding:4px 12px;font-size:11px;font-weight:700;color:#166534}

.p3-body{padding:18px 18px 120px;flex:1}
.trip-card{background:var(--card);border-radius:14px;border:1px solid var(--faint);
  padding:14px 16px;margin-bottom:16px;display:flex;align-items:center;gap:12px}
.trip-pins{display:flex;flex-direction:column;align-items:center;gap:4px;flex-shrink:0}
.pin-y2{width:9px;height:9px;border-radius:50%;
  background:var(--y);border:2px solid #0C0C0A}
.pin-line{width:1.5px;height:12px;background:var(--faint)}
.pin-r{width:9px;height:9px;border-radius:50%;
  background:#EF4444;border:2px solid #0C0C0A}
.trip-from{font-size:12px;color:var(--mid);margin-bottom:3px}
.trip-to{font-size:14px;font-weight:700;color:var(--ink)}
.trip-dist{font-size:13px;font-weight:700;color:var(--mid);
  margin-left:auto;flex-shrink:0}

.cat-tabs{display:flex;gap:6px;margin-bottom:14px;overflow-x:auto;padding-bottom:5px}
.ctab{padding:9px 18px;border-radius:24px;border:1px solid var(--faint);
  background:var(--card);font-size:13px;font-weight:700;color:var(--mid);
  cursor:pointer;transition:all .15s;white-space:nowrap}
.ctab.on{background:#0C0C0A;border-color:#0C0C0A;color:var(--y)}

.sort-row{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
.sort-lbl{font-size:11px;font-weight:700;color:var(--mid);
  letter-spacing:.8px;text-transform:uppercase}
.sort-btns{display:flex;gap:5px}
.sbtn{padding:6px 12px;border-radius:8px;border:1px solid var(--faint);
  background:var(--card);font-size:11px;font-weight:700;
  color:var(--mid);cursor:pointer;transition:all .15s}
.sbtn.on{background:#0C0C0A;border-color:#0C0C0A;color:var(--y)}

.pcard{background:var(--card);border-radius:15px;border:1px solid var(--faint);
  padding:14px 15px;margin-bottom:8px;display:flex;align-items:flex-start;
  gap:12px;cursor:pointer;transition:border-color .15s;
  position:relative;overflow:hidden}
.pcard:hover{border-color:#bbb}
.pcard.best{border:2px solid var(--y)}
.pcard.sel{border:2px solid #0C0C0A}
.pcard-sel-bar{position:absolute;left:0;top:0;bottom:0;width:4px;background:#0C0C0A}
.plogo{width:44px;height:44px;border-radius:11px;
  display:flex;align-items:center;justify-content:center;
  font-size:13px;font-weight:900;flex-shrink:0;font-family:var(--sans)}
.pinfo{flex:1;min-width:0}
.pname{font-size:14px;font-weight:700;color:var(--ink)}
.pmeta{font-size:11px;color:var(--mid);margin-top:2px}
.ptags{display:flex;gap:5px;margin-top:7px;flex-wrap:wrap}
.ptag{font-size:10px;font-weight:700;padding:3px 8px;border-radius:6px}
.tg{background:#F0FDF4;color:#166534}
.tb{background:#EFF6FF;color:#1e40af}
.ta{background:#FFFBEB;color:#92400e}
.tm{background:#F8F6F0;color:var(--mid);border:1px solid var(--faint)}
.pprice{text-align:right;flex-shrink:0}
.price-big{font-family:var(--serif);font-size:19px;
  color:var(--ink);letter-spacing:-1px}
.price-label{font-size:10px;color:var(--mid);margin-top:1px}
.eta-chip{background:var(--bg);border-radius:7px;padding:3px 8px;
  font-size:11px;font-weight:700;color:var(--ink);
  margin-top:5px;display:inline-block}
.best-badge{background:var(--y);font-size:9px;font-weight:800;
  color:#0C0C0A;padding:2px 8px;border-radius:5px;letter-spacing:.5px;
  position:absolute;top:10px;right:12px}

.disclaimer{font-size:11px;color:var(--mid);text-align:center;
  line-height:1.6;padding:12px 8px;border-top:1px solid var(--faint);margin-top:8px}

.p3-footer{position:fixed;bottom:0;left:50%;transform:translateX(-50%);
  width:100%;max-width:480px;background:var(--card);
  border-top:1px solid var(--faint);padding:14px 18px 24px;
  display:flex;align-items:center;justify-content:space-between;gap:12px;
  z-index:50}
.sel-info{flex:1;min-width:0}
.sel-name{font-size:14px;font-weight:700;color:var(--ink);
  white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.sel-price{font-size:12px;color:var(--mid);margin-top:2px}
.open-btn{background:#0C0C0A;border-radius:13px;padding:13px 22px;
  font-size:14px;font-weight:700;color:var(--y);
  cursor:pointer;white-space:nowrap;flex-shrink:0; text-decoration:none; display:inline-block; text-align:center;}
.open-btn:hover{opacity:.88}

@keyframes fadeUp{
  from{opacity:0;transform:translateY(6px)}
  to{opacity:1;transform:translateY(0)}
}
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
    <div class="logo">Cab<div class="logo-zero">0</div><span class="logo-ext">.com</span></div>
    <div class="free-chip">100% FREE</div>
  </div>
  <div class="p1-body">
    <div class="kicker"><div class="kicker-dot"></div><span class="kicker-text">No fees · No sign-up · No API keys</span></div>
    <h1>Every ride.<br><em>Every delivery.</em><br>One search.</h1>
    <p class="p1-sub">Compare Uber, Lyft, DoorDash, Instacart and 16 more platforms side by side — instantly.</p>
    <div class="search-bar" onclick="goTo(1)">
      <div class="pin-y"></div>
      <span class="search-ph">Where are you going?</span>
      <div class="search-btn">→</div>
    </div>
    <div class="cats">
      <div class="cat on" onclick="pickCat(this, 'ride')"><div class="cat-dot" style="background:#FACC15"></div><div class="cat-label">Rides</div></div>
      <div class="cat" onclick="pickCat(this, 'food')"><div class="cat-dot" style="background:#f97316"></div><div class="cat-label">Food</div></div>
      <div class="cat" onclick="pickCat(this, 'grocery')"><div class="cat-dot" style="background:#22c55e"></div><div class="cat-label">Grocery</div></div>
    </div>
    <div class="stats">
      <div class="stat"><div class="stat-n">20</div><div class="stat-l">Providers</div></div>
      <div class="stat"><div class="stat-n">$0</div><div class="stat-l">Cab0 fee</div></div>
      <div class="stat"><div class="stat-n">3</div><div class="stat-l">Taps to book</div></div>
    </div>
    <div class="cta-btn" onclick="goTo(1)">
      <div class="cta-main">Get started — it's free →</div>
      <div class="cta-sub">Set your address in 20 seconds</div>
    </div>
  </div>
</div>
</div>

<div class="page" id="pg1">
<div class="p2">
  <div class="topbar">
    <div class="back-btn" onclick="goTo(0)">←</div>
    <div class="tb-logo">Cab<span>0</span>.com</div>
    <div class="tb-step" id="step-txt">Step 1 of 2</div>
  </div>
  <div class="p2-body">
    <div class="step-track">
      <div class="snode s-active">1</div><div class="sline"></div><div class="snode s-future">2</div><div class="sline"></div><div class="snode s-future">3</div>
    </div>
    <div class="eyebrow">Quick setup</div>
    <h2>Set your home address</h2>
    <p class="p2-sub">Save it once — Cab0 pre-fills your pickup every time.</p>
    <div class="detect-bar" onclick="fillAddress()">
      <div class="detect-icon"><svg width="16" height="16" fill="none"><circle cx="8" cy="8" r="2.5" fill="#FACC15"/><circle cx="8" cy="8" r="5" stroke="#FACC15" stroke-width="1.5"/><line x1="8" y1="1" x2="8" y2="3" stroke="#FACC15"/><line x1="8" y1="13" x2="8" y2="15" stroke="#FACC15"/><line x1="1" y1="8" x2="3" y2="8" stroke="#FACC15"/><line x1="13" y1="8" x2="15" y2="8" stroke="#FACC15"/></svg></div>
      <div><div class="detect-title">Use my current location</div><div class="detect-sub">Auto-detect address via GPS</div></div>
    </div>
    <div class="form-card">
      <div class="fl">Street address</div><input class="fi" id="f-street" type="text" placeholder="290 Riverside Drive">
      <div class="fl">City</div><input class="fi" id="f-city" type="text" placeholder="Newport News">
    </div>
    <div class="p2-cta" onclick="goTo(2)"><div class="p2-cta-text">Save & compare options →</div></div>
    <div class="skip" onclick="goTo(2)">Skip for now — set it later</div>
  </div>
</div>
</div>

<div class="page" id="pg2">
<div class="p3">
  <div class="p3-topbar">
    <div class="back-btn" onclick="goTo(1)">←</div>
    <div class="tb-logo">Cab<span style="color:var(--yd)">0</span>.com</div>
    <div class="free-badge">FREE forever</div>
  </div>
  <div class="p3-body">
    <div class="trip-card">
      <div class="trip-pins"><div class="pin-y2"></div><div class="pin-line"></div><div class="pin-r"></div></div>
      <div style="flex:1"><div class="trip-from" id="trip-from">Set your pickup</div><div class="trip-to">Newport News Airport (PHF)</div></div>
      <div class="trip-dist">6.2 mi</div>
    </div>
    <div class="cat-tabs">
      <div class="ctab on" onclick="switchCat('ride',this)">Rides</div>
      <div class="ctab" onclick="switchCat('food',this)">Food</div>
      <div class="ctab" onclick="switchCat('grocery',this)">Grocery</div>
    </div>
    <div id="p3-grid"></div>
    <div class="disclaimer">Estimates from public rates. Tapping opens the provider app.</div>
  </div>
  <div class="p3-footer">
    <div class="sel-info"><div class="sel-name" id="sel-name">Select an option above</div><div class="sel-price" id="sel-price">$0.00 Cab0 fee</div></div>
    <a href="#" id="final-link" target="_blank" class="open-btn" onclick="trackClick()">Open app →</a>
  </div>
</div>
</div>

<script>
var currentCat = 'ride';
var selectedId = null;

// LINK MAP - Connects IDs to actual websites/apps
var LINKS = {
  'uber_x': 'https://m.uber.com/ul/',
  'lyft': 'https://lyft.com/ride?id=lyft',
  'via': 'https://ridewithvia.com/',
  'doordash': 'https://www.doordash.com/',
  'ubereats': 'https://www.ubereats.com/',
  'instacart': 'https://www.instacart.com/',
  'grubhub': 'https://www.grubhub.com/'
};

var PROVIDERS = {
  ride: [
    { id:'uber_x', name:'Uber X', s:'Ub', c:'#000', t:'#fff', p:[9,11], eta:6, r:4.8, tags:['Most popular'] },
    { id:'lyft', name:'Lyft', s:'Ly', c:'#E91E8C', t:'#fff', p:[10,13], eta:7, r:4.7, tags:['Competitive'] },
    { id:'via', name:'Via Share', s:'Via', c:'#1FB954', t:'#fff', p:[6,8], eta:16, r:4.5, tags:['Cheapest'] }
  ],
  food: [
    { id:'doordash', name:'DoorDash', s:'DD', c:'#FF3008', t:'#fff', p:[2.99,4.99], eta:28, r:4.6, tags:['Fastest'] },
    { id:'ubereats', name:'Uber Eats', s:'UE', c:'#06C167', t:'#000', p:[3.49,5.99], eta:22, r:4.7, tags:['Uber One'] },
    { id:'grubhub', name:'Grubhub', s:'GH', c:'#F97316', t:'#fff', p:[3.99,6.49], eta:34, r:4.4, tags:['Dinner'] }
  ],
  grocery: [
    { id:'instacart', name:'Instacart', s:'IC', c:'#00AD31', t:'#fff', p:[3.99,5.99], eta:55, r:4.7, tags:['500+ stores'] }
  ]
};

function goTo(n) {
  document.querySelectorAll('.page').forEach((p, i) => p.classList.toggle('active', i === n));
  document.querySelectorAll('.nd').forEach((d, i) => d.classList.toggle('on', i === n));
  const labels = ['Welcome', 'Home Address', 'Compare Providers'];
  document.getElementById('pg-lbl').textContent = 'Page ' + (n+1) + ' of 3 — ' + labels[n];
  if (n === 2) renderProviders();
  window.scrollTo(0,0);
}

function pickCat(el, cat) {
  document.querySelectorAll('.cat').forEach(c => c.classList.remove('on'));
  el.classList.add('on');
  currentCat = cat;
}

function fillAddress() {
  document.getElementById('f-street').value = '290 Riverside Drive';
  document.getElementById('f-city').value = 'Newport News';
  document.getElementById('trip-from').textContent = '290 Riverside Dr, Newport News';
}

function switchCat(cat, el) {
  currentCat = cat;
  selectedId = null;
  document.querySelectorAll('.ctab').forEach(t => t.classList.remove('on'));
  el.classList.add('on');
  renderProviders();
}

function renderProviders() {
  var list = PROVIDERS[currentCat] || [];
  if (!selectedId && list.length) selectProvider(list[0].id);
  var html = '';
  list.forEach((p, i) => {
    var isSel = (p.id === selectedId);
    html += `<div class="pcard ${isSel?'sel':''}" onclick="selectProvider('${p.id}')">
      ${isSel?'<div class="pcard-sel-bar"></div>':''}
      <div class="plogo" style="background:${p.c};color:${p.t}">${p.s}</div>
      <div class="pinfo">
        <div class="pname">${p.name}</div>
        <div class="pmeta">${p.r} ★ · ${p.eta} min</div>
      </div>
      <div class="pprice"><div class="price-big">$${p.p[0]}</div></div>
    </div>`;
  });
  document.getElementById('p3-grid').innerHTML = html;
}

function selectProvider(id) {
  selectedId = id;
  var p = (PROVIDERS.ride.concat(PROVIDERS.food, PROVIDERS.grocery)).find(x => x.id === id);
  document.getElementById('sel-name').textContent = p.name + ' selected';
  document.getElementById('final-link').href = LINKS[id] || '#';
  renderProviders();
}

function trackClick() {
  const btn = document.querySelector('.open-btn');
  btn.textContent = 'Launching App...';
  setTimeout(() => { btn.textContent = 'Open app →'; }, 2000);
}
</script>
</body>
</html>
