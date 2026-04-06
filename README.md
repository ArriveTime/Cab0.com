<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Cab0.com — Every Ride. Every Delivery. One Search.</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --ink:#0C0C0A; --y:#FACC15; --yd:#D4A10A; --bg:#F6F3EC;
  --serif:'DM Serif Display',Georgia,serif; --sans:'DM Sans',system-ui,sans-serif;
}
body{font-family:var(--sans);background:#0C0C0A;color:#fff;max-width:480px;margin:0 auto;line-height:1.4}

/* Navigation */
.nav-bar{display:flex;justify-content:center;align-items:center;gap:8px;padding:14px 0;background:#0C0C0A;border-bottom:1px solid #222;position:sticky;top:0;z-index:100}
.nd{width:8px;height:8px;border-radius:4px;background:#333;transition:all .3s;cursor:pointer;border:none;padding:0}
.nd.on{width:24px;background:var(--y)}
.pg-label{font-size:11px;font-weight:700;color:#666;letter-spacing:.6px;margin-left:10px;text-transform:uppercase}

.page{display:none}
.page.active{display:block}

/* Page 1: Branding & Categories */
.p1-body{padding:40px 26px;display:flex;flex-direction:column;min-height:90vh}
h1{font-family:var(--serif);font-size:46px;line-height:1.05;color:#fff;margin-bottom:16px}
h1 em{color:var(--y);font-style:normal}
.search-bar{background:#161616;border:1px solid #252525;border-radius:16px;padding:18px;display:flex;align-items:center;gap:12px;margin-bottom:24px;cursor:pointer}
.pin-y{width:10px;height:10px;border-radius:50%;background:var(--y)}
.cats{display:grid;grid-template-columns: 1fr 1fr;gap:12px;margin-bottom:30px}
.cat{background:#161616;border:1px solid #252525;border-radius:14px;padding:22px 10px;text-align:center;cursor:pointer;transition:0.2s}
.cat.on{background:var(--y);border-color:var(--y)}
.cat.on .cat-label{color:#000}
.cat-label{font-size:14px;font-weight:700;color:#888}

/* Page 3: Comparison View */
.sort-strip{display:flex;background:#000;padding:10px 18px;gap:8px;border-bottom:1px solid #222;position:sticky;top:52px;z-index:90}
.sort-btn{flex:1;padding:10px;border-radius:8px;border:1px solid #333;font-size:11px;font-weight:700;background:#000;color:#888;cursor:pointer}
.sort-btn.active{background:var(--y);color:#000;border-color:var(--y)}
.pcard{background:#161616;border-radius:15px;border:1px solid #222;padding:16px;margin-bottom:10px;display:flex;align-items:center;gap:15px;cursor:pointer}
.pcard.sel{border:2px solid var(--y);background:#1a1a1a}
.p3-footer{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:100%;max-width:480px;background:#000;border-top:1px solid #222;padding:20px;display:flex;align-items:center;justify-content:space-between;z-index:1000}
.open-btn{background:var(--y);color:#000;padding:14px 28px;border-radius:12px;text-decoration:none;font-weight:700;font-size:16px}
</style>
</head>
<body>

<div class="nav-bar">
  <button class="nd on" id="dot0" onclick="goTo(0)"></button>
  <button class="nd"    id="dot1" onclick="goTo(1)"></button>
  <button class="nd"    id="dot2" onclick="goTo(2)"></button>
  <span class="pg-label" id="cur-label">Cab0 Hub</span>
</div>

<div class="page active" id="pg0">
  <div class="p1-body">
    <div style="font-family:var(--serif); font-size:24px; margin-bottom:40px;">Cab<span style="color:var(--y)">0</span>.com</div>
    <h1>Every ride.<br>Every delivery.<br><em>One search.</em></h1>
    <div class="search-bar" onclick="goTo(1)">
      <div class="pin-y"></div>
      <span style="color:#666">Enter destination...</span>
    </div>
    <div class="cats">
      <div class="cat on" onclick="pickCat(this, 'ride')"><div class="cat-label">Rideshare</div></div>
      <div class="cat" onclick="pickCat(this, 'food')"><div class="cat-label">Food</div></div>
      <div class="cat" onclick="pickCat(this, 'grocery')"><div class="cat-label">Grocery</div></div>
      <div class="cat" onclick="pickCat(this, 'retail')"><div class="cat-label">Package/Retail</div></div>
    </div>
    <div style="background:var(--y); color:#000; padding:20px; border-radius:15px; text-align:center; font-weight:700; cursor:pointer;" onclick="goTo(1)">Find the best rate →</div>
  </div>
</div>

<div class="page" id="pg1">
  <div style="padding:40px 26px;">
    <h2 style="margin-bottom:20px;">Pickup Details</h2>
    <div style="background:#161616; border:1px solid #222; border-radius:18px; padding:20px;">
      <div style="font-size:11px; color:#666; text-transform:uppercase; margin-bottom:8px;">Location</div>
      <input type="text" placeholder="123 Main St, Williamsburg, VA" style="width:100%; background:#000; border:1.5px solid #333; color:#fff; padding:15px; border-radius:11px; outline:none; font-size:16px;">
    </div>
    <div style="background:var(--y); color:#000; padding:20px; border-radius:15px; text-align:center; font-weight:700; margin-top:20px; cursor:pointer;" onclick="goTo(2)">Compare Providers →</div>
    <div style="text-align:center; margin-top:20px; color:#666; font-size:12px;" onclick="goTo(0)">← Back to Home</div>
  </div>
</div>

<div class="page" id="pg2">
  <div class="sort-strip">
    <button class="sort-btn active" id="sort-price" onclick="setSort('price')">CHEAPEST</button>
    <button class="sort-btn" id="sort-time" onclick="setSort('time')">FASTEST</button>
  </div>
  <div style="padding:18px 18px 140px;" id="p3-grid"></div>
  <div class="p3-footer">
    <div><div id="sel-name" style="font-weight:700; font-size:15px;">Select Option</div><div style="font-size:11px; color:#666;">Direct App Connection</div></div>
    <a href="#" id="final-link" target="_blank" class="open-btn">Open App</a>
  </div>
</div>

<script>
var currentCat = 'ride', currentSort = 'price', selectedId = null;

// APP SCHEMES & DESTINATIONS
var LINKS = {
  'uber':'https://m.uber.com', 'lyft':'lyft://', 'curb':'https://gocurb.com',
  'doordash':'doordash://', 'ubereats':'ubereats://', 'grubhub':'grubhub://', 'postmates':'postmates://',
  'instacart':'instacart://', 'shipt':'shipt://', 'amazon':'https://amazon.com/fresh', 'walmart':'walmart://'
};

var PROVIDERS = {
  ride: [
    { id:'uber', name:'Uber X', s:'Ub', c:'#000', price:9.50, time:4 },
    { id:'lyft', name:'Lyft', s:'Ly', c:'#FF00BF', price:10.20, time:6 },
    { id:'curb', name:'Curb Taxi', s:'Cb', c:'#007AFF', price:12.00, time:3 }
  ],
  food: [
    { id:'doordash', name:'DoorDash', s:'DD', c:'#FF3008', price:1.99, time:25 },
    { id:'ubereats', name:'Uber Eats', s:'UE', c:'#06C167', price:2.49, time:20 },
    { id:'grubhub', name:'Grubhub', s:'GH', c:'#F97316', price:3.00, time:35 }
  ],
  grocery: [
    { id:'instacart', name:'Instacart', s:'IC', c:'#00AD31', price:3.99, time:60 },
    { id:'shipt', name:'Shipt', s:'Sh', c:'#E0162B', price:5.00, time:45 },
    { id:'amazon', name:'Amazon Fresh', s:'Az', c:'#FF9900', price:0.00, time:90 }
  ],
  retail: [
    { id:'walmart', name:'Walmart+', s:'Wm', c:'#0071DC', price:0.00, time:120 },
    { id:'doordash', name:'DoorDash DashMart', s:'DD', c:'#FF3008', price:2.99, time:30 }
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
