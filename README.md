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

/* NAVIGATION */
.nav-bar{display:flex;justify-content:center;align-items:center;gap:8px;padding:14px 0;background:#0C0C0A;border-bottom:1px solid #222;position:sticky;top:0;z-index:100}
.nd{width:8px;height:8px;border-radius:4px;background:#333;transition:all .3s;cursor:pointer;border:none;padding:0}
.nd.on{width:24px;background:var(--y)}
.pg-label{font-size:11px;font-weight:700;color:#666;letter-spacing:.6px;margin-left:10px;text-transform:uppercase}

.page{display:none}
.page.active{display:block}

/* PAGE 1: HERO & CATEGORIES */
.p1-body{padding:30px 26px;display:flex;flex-direction:column}
.logo-main{font-family:var(--serif); font-size:24px; margin-bottom:20px; color:#fff;}
.logo-main span{color:var(--y)}
h1{font-family:var(--serif);font-size:42px;line-height:1.05;color:#fff;margin-bottom:16px}
h1 em{color:var(--y);font-style:normal}

.cats-grid{display:grid;grid-template-columns: 1fr 1fr;gap:12px;margin-bottom:20px}
.cat{background:#161616;border:1px solid #252525;border-radius:12px;padding:22px 5px;text-align:center;cursor:pointer;transition:0.2s;display:flex;flex-direction:column;align-items:center;gap:8px}
.cat.on{background:var(--y);border-color:var(--y)}
.cat.on .cat-label{color:#000}
.cat-label{font-size:14px;font-weight:700;color:#777}
.cat-icon{font-size:20px;}

/* PAGE 3: RESULTS */
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
  <button class="nd on" onclick="goTo(0)"></button>
  <button class="nd"    onclick="goTo(1)"></button>
  <button class="nd"    onclick="goTo(2)"></button>
  <span class="pg-label">Cab0 Comparison</span>
</div>

<div class="page active" id="pg0">
  <div class="p1-body">
    <div class="logo-main">Cab<span>0</span>.com</div>
    <h1>Every ride.<br>Every delivery.<br><em>One search.</em></h1>
    
    <div style="background:#161616; border:1px solid #252525; border-radius:16px; padding:18px; display:flex; align-items:center; gap:12px; margin-bottom:25px; cursor:pointer" onclick="goTo(1)">
      <div style="width:10px; height:10px; border-radius:50%; background:var(--y)"></div>
      <span style="color:#666">Where are we going?</span>
    </div>

    <div class="cats-grid">
      <div class="cat on" onclick="pickCat(this, 'ride')">
        <span class="cat-icon">🚗</span>
        <div class="cat-label">Rideshare</div>
      </div>
      <div class="cat" onclick="pickCat(this, 'vip')">
        <span class="cat-icon">💎</span>
        <div class="cat-label">VIP Luxury</div>
      </div>
      <div class="cat" onclick="pickCat(this, 'delivery')">
        <span class="cat-icon">🍔</span>
        <div class="cat-label">Food Delivery</div>
      </div>
      <div class="cat" onclick="pickCat(this, 'grocery')">
        <span class="cat-icon">🛒</span>
        <div class="cat-label">Grocery/Retail</div>
      </div>
    </div>
    
    <div style="background:var(--y); color:#000; padding:20px; border-radius:15px; text-align:center; font-weight:700; cursor:pointer;" onclick="goTo(1)">Start Comparison →</div>
  </div>
</div>

<div class="page" id="pg1">
  <div style="padding:40px 26px;">
    <h2>Confirm Address</h2>
    <div style="background:#161616; border:1px solid #222; border-radius:18px; padding:20px; margin-top:20px;">
      <input type="text" placeholder="123 Main St, Williamsburg, VA" style="width:100%; background:#000; border:1.5px solid #333; color:#fff; padding:15px; border-radius:11px; outline:none; font-size:16px;">
    </div>
    <div style="background:var(--y); color:#000; padding:20px; border-radius:15px; text-align:center; font-weight:700; margin-top:20px; cursor:pointer;" onclick="goTo(2)">Find Best Rate →</div>
  </div>
</div>

<div class="page" id="pg2">
  <div class="sort-strip">
    <button class="sort-btn active" id="sort-price" onclick="setSort('price')">CHEAPEST</button>
    <button class="sort-btn" id="sort-time" onclick="setSort('time')">FASTEST</button>
  </div>
  <div style="padding:18px 18px 140px;" id="p3-grid"></div>
  <div class="p3-footer">
    <div><div id="sel-name" style="font-weight:700; font-size:15px;">Select Option</div><div style="font-size:11px; color:#666;">Official Destination Link</div></div>
    <a href="#" id="final-link" target="_blank" class="open-btn">Open App</a>
  </div>
</div>

<script>
var currentCat = 'ride', currentSort = 'price', selectedId = null;

// ALL ACTIVE DESTINATION LINKS (Direct App & Mobile Web)
var LINKS = {
  'uber':'https://m.uber.com',
  'lyft':'lyft://',
  'waymo':'https://waymo.com/waymo-one/',
  'zoox':'https://zoox.com/',
  'uber_black':'uber://?action=setPickup&product_id=uberblack',
  'lyft_lux':'lyft://ridetype?id=lyft_lux',
  'doordash':'doordash://',
  'ubereats':'ubereats://',
  'grubhub':'grubhub://',
  'amazon':'https://www.amazon.com/fresh',
  'walmart':'https://www.walmart.com/plus',
  'instacart':'instacart://'
};

var PROVIDERS = {
  ride: [
    { id:'uber', name:'Uber X', s:'Ub', c:'#000', price:9.50, time:4 },
    { id:'lyft', name:'Lyft', s:'Ly', c:'#FF00BF', price:10.20, time:6 },
    { id:'waymo', name:'Waymo One', s:'Wy', c:'#00D1B2', price:8.00, time:12 }
  ],
  vip: [
    { id:'uber_black', name:'Uber Black', s:'Bk', c:'#222', price:28.50, time:5 },
    { id:'lyft_lux', name:'Lyft Lux Black', s:'Lx', c:'#000', price:31.00, time:8 }
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
