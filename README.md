<!DOCTYPE html>
<html lang="en" style="background-color: #000000; color: #000000;">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Cab0.com — Every Ride. Every Delivery. One Search.</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:italic,wght@400;700&display=swap" rel="stylesheet">
<style>
/* 1. HIDE STRAY TAGS: Forces top-level text to match background */
html, body {
    background-color: #000000 !important;
    color: #000000; 
    margin: 0 auto;
    max-width: 480px;
    overflow-x: hidden;
}

:root {
  --cab0-blue: #3b82f6;
  --cab0-yellow: #FACC15;
  --serif: 'DM Serif Display', serif;
  --sans: 'DM Sans', sans-serif;
  --fancy: 'Playfair Display', serif;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

.content-wrapper {
    color: #ffffff;
    font-family: var(--sans);
    min-height: 100vh;
}

/* NAVIGATION */
.nav-bar {
    display: flex;
    justify-content: center;
    gap: 8px;
    padding: 20px 0;
    background: #000000;
}
.nd { width: 8px; height: 8px; border-radius: 50%; background: #111; border:1px solid #111;}
.nd.on { width: 24px; border-radius: 4px; background: var(--cab0-yellow); border-color: var(--cab0-yellow); }

.page { display: none; }
.page.active { display: block; }

/* BRANDING */
.p1-body { padding: 0 26px 30px; }
.logo-main { font-family: var(--serif); font-size: 32px; color: var(--cab0-blue); margin-bottom: 4px; }
.logo-main span { color: var(--cab0-yellow); }

/* WOZ QUOTE */
.woz-box { margin-bottom: 30px; border-left: 2px solid var(--cab0-yellow); padding-left: 15px; margin-top: 10px; }
.woz-quote { font-family: var(--fancy); font-style: italic; font-size: 16px; color: var(--cab0-yellow); line-height: 1.4; }
.woz-attribution { display: block; font-family: var(--sans); font-size: 10px; font-weight: 700; text-transform: uppercase; margin-top: 8px; letter-spacing: 1px; color: var(--cab0-yellow); opacity: 0.9; }

h1 { font-family: var(--serif); font-size: 44px; line-height: 1.1; margin-bottom: 20px; color: #fff; }
h1 em { color: var(--cab0-yellow); font-style: normal; }

/* TILES */
.cats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 25px; }
.cat { background: #111; border: 1px solid #222; border-radius: 12px; padding: 25px 10px; text-align: center; cursor: pointer; }
.cat.on { background: var(--cab0-yellow); border-color: var(--cab0-yellow); }
.cat.on .cat-label { color: #000; }
.cat-label { font-size: 14px; font-weight: 700; color: #888; }

/* RESULTS LIST */
.sort-strip { display: flex; background: #000; padding: 10px 18px; gap: 8px; border-bottom: 1px solid #111; position: sticky; top: 0; z-index: 90; }
.sort-btn { flex: 1; padding: 12px; border-radius: 8px; border: 1px solid #222; font-size: 11px; font-weight: 700; background: #000; color: #888; cursor: pointer; }
.sort-btn.active { background: var(--cab0-yellow); color: #000; border-color: var(--cab0-yellow); }
.pcard { background: #111; border-radius: 15px; border: 1px solid #222; padding: 16px; margin-bottom: 10px; display: flex; align-items: center; gap: 15px; cursor: pointer; }
.pcard.sel { border: 2px solid var(--cab0-yellow); background: #080808; }

.p3-footer { position: fixed; bottom: 0; left: 50%; transform: translateX(-50%); width: 100%; max-width: 480px; background: #000; border-top: 1px solid #111; padding: 20px; display: flex; align-items: center; justify-content: space-between; z-index: 1000; }
.open-btn { background: var(--cab0-yellow); color: #000; padding: 14px 28px; border-radius: 12px; text-decoration: none; font-weight: 700; font-size: 16px; text-align: center; }
</style>
</head>
<body>

<div class="content-wrapper">
    <div class="nav-bar">
        <div class="nd on" id="d0"></div>
        <div class="nd" id="d1"></div>
        <div class="nd" id="d2"></div>
    </div>

    <div class="page active" id="pg0">
        <div class="p1-body">
            <div class="logo-main">Cab<span>0</span>.com</div>
            <div class="woz-box">
                <p class="woz-quote">"Best of luck to you on this worthy venture, its your turn"</p>
                <span class="woz-attribution">Steve Wozniak, Apple Co-Founder</span>
            </div>
            <h1>Every ride.<br>Every delivery.<br><em>One search.</em></h1>
            <div class="cats-grid">
                <div class="cat on" onclick="pickCat(this, 'ride')"><div class="cat-label">Rideshare</div></div>
                <div class="cat" onclick="pickCat(this, 'vip')"><div class="cat-label">VIP Luxury</div></div>
                <div class="cat" onclick="pickCat(this, 'delivery')"><div class="cat-label">Food</div></div>
                <div class="cat" onclick="pickCat(this, 'grocery')"><div class="cat-label">Grocery</div></div>
            </div>
            <div class="main-btn" onclick="goTo(1)">Find Best Rate →</div>
        </div>
    </div>

    <div class="page" id="pg1">
        <div style="padding:40px 26px;">
            <h2 style="color:#fff; margin-bottom:20px;">Confirm Destination</h2>
            <input type="text" placeholder="Enter Address..." style="width:100%; background:#111; border:1px solid #333; color:#fff; padding:18px; border-radius:12px; font-size:16px; margin-bottom:20px;">
            <div class="main-btn" onclick="goTo(2)">Compare Rates →</div>
        </div>
    </div>

    <div class="page" id="pg2">
        <div class="sort-strip">
            <button class="sort-btn active" id="sort-price" onclick="setSort('price')">CHEAPEST</button>
            <button class="sort-btn" id="sort-time" onclick="setSort('time')">FASTEST</button>
        </div>
        <div style="padding:18px 18px 140px;" id="p3-grid"></div>
        <div class="p3-footer">
            <div><div id="sel-name" style="font-weight:700; color:#fff;">Select Service</div><div style="font-size:11px; color:#666;">Secure Official Link</div></div>
            <a href="#" id="final-link" target="_blank" class="open-btn">Book Now</a>
        </div>
    </div>
</div>

<script>
var currentCat = 'ride', currentSort = 'price', selectedId = null;

// SECURE HTTPS LINKS
var LINKS = {
  'uber':'https://m.uber.com', 'lyft':'https://www.lyft.com', 'waymo':'https://waymo.com',
  'uber_black':'https://m.uber.com', 'lyft_lux':'https://www.lyft.com',
  'doordash':'https://www.doordash.com', 'ubereats':'https://www.ubereats.com', 'grubhub':'https://www.grubhub.com',
  'amazon':'https://www.amazon.com/fresh', 'walmart':'https://www.walmart.com', 'instacart':'https://www.instacart.com'
};

var PROVIDERS = {
  ride: [
    { id:'uber', name:'Uber X', s:'Ub', c:'#000', price:9.50, time:4 },
    { id:'lyft', name:'Lyft', s:'Ly', c:'#FF00BF', price:10.20, time:6 },
    { id:'waymo', name:'Waymo', s:'Wy', c:'#00D1B2', price:8.00, time:12 }
  ],
  vip: [
    { id:'uber_black', name:'Uber Black', s:'Bk', c:'#222', price:28.50, time:5 },
    { id:'lyft_lux', name:'Lyft Lux', s:'Lx', c:'#000', price:31.00, time:8 }
  ],
  delivery: [
    { id:'doordash', name:'DoorDash', s:'DD', c:'#FF3008', price:1.99, time:25 },
    { id:'ubereats', name:'Uber Eats', s:'UE', c:'#06C167', price:2.49, time:20 },
    { id:'grubhub', name:'Grubhub', s:'GH', c:'#F97316', price:2.99, time:35 }
  ],
  grocery: [
    { id:'amazon', name:'Amazon Fresh', s:'Az', c:'#FF9900', price:0.00, time:45 },
    { id:'walmart', name:'Walmart+', s:'Wm', c:'#0071DC', price:0.00, time:90 },
    { id:'instacart', name:'Instacart', s:'IC', c:'#00AD31', price:3.99, time:60 }
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
      <div style="width:40px;height:40px;background:${p.c};border-radius:8px;display:flex;align-items:center;justify-content:center;font-weight:900;color:#fff;">${p.s}</div>
      <div style="flex:1"><strong>${p.name}</strong><div style="font-size:11px;color:#666">${p.time} min wait</div></div>
      <div style="font-family:var(--serif);font-size:18px;color:var(--cab0-yellow)">$${p.price.toFixed(2)}</div>
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
