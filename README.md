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
body{font-family:var(--sans);background:var(--bg);color:var(--ink);margin:0}

.nav-bar{display:flex;justify-content:center;align-items:center;gap:8px;
  padding:14px 0;background:var(--bg);border-bottom:1px solid var(--faint);
  position:sticky;top:0;z-index:100}
.nd{width:8px;height:8px;border-radius:4px;background:var(--faint);
  transition:all .3s;cursor:pointer;border:none;padding:0}
.nd.on{width:24px;background:var(--ink)}
.pg-label{font-size:11px;font-weight:700;color:var(--mid);
  letter-spacing:.6px;margin-left:10px;font-family:var(--sans)}

.page{display:none}
.page.active{display:block}

/* PAGE 1 */
.p1{background:#0C0C0A;min-height:100vh;display:flex;flex-direction:column}
.p1-nav{display:flex;justify-content:space-between;align-items:center;
  padding:22px 40px;max-width:960px;margin:0 auto;width:100%}
.logo{font-family:var(--serif);font-size:28px;color:#fff;
  display:flex;align-items:center;gap:2px;letter-spacing:-1px}
.logo-zero{background:var(--y);border-radius:7px;padding:2px 9px;
  margin-left:2px;font-family:var(--serif);font-size:28px;
  color:#0C0C0A;line-height:1.3}
.logo-ext{font-family:var(--sans);font-size:13px;color:#444;
  margin-left:4px;font-weight:600}
.free-chip{background:#161616;border:1px solid #252525;color:#666;
  font-size:11px;font-weight:700;padding:6px 14px;
  border-radius:20px;letter-spacing:.8px}

.p1-body{flex:1;max-width:960px;margin:0 auto;width:100%;
  padding:0 40px 60px;display:grid;
  grid-template-columns:1fr 1fr;gap:60px;align-items:start}
.p1-left{display:flex;flex-direction:column}
.p1-right{display:flex;flex-direction:column;gap:16px;padding-top:20px}

.kicker{display:inline-flex;align-items:center;gap:8px;
  background:#161616;border:1px solid #252525;border-radius:20px;
  padding:6px 14px;margin-bottom:24px;align-self:flex-start}
.kicker-dot{width:7px;height:7px;border-radius:50%;background:var(--y)}
.kicker-text{font-size:11px;font-weight:600;color:#666;letter-spacing:.8px}

h1{font-family:var(--serif);font-size:54px;line-height:1.0;
  color:#fff;letter-spacing:-2.5px;margin-bottom:20px}
h1 em{color:var(--y);font-style:normal}
.p1-sub{font-size:16px;color:#777;line-height:1.7;margin-bottom:32px}

.search-bar{background:#161616;border:1px solid #252525;border-radius:16px;
  padding:16px 18px;display:flex;align-items:center;gap:12px;
  margin-bottom:16px;cursor:pointer;transition:border-color .2s}
.search-bar:hover{border-color:#3a3a3a}
.pin-y{width:10px;height:10px;border-radius:50%;
  background:var(--y);flex-shrink:0}
.search-ph{font-size:15px;color:#444;flex:1}
.search-btn{width:36px;height:36px;border-radius:10px;
  background:var(--y);display:flex;align-items:center;
  justify-content:center;flex-shrink:0;
  font-size:16px;font-weight:700;color:#0C0C0A}

.cats{display:flex;gap:8px;margin-bottom:24px}
.cat{flex:1;background:#161616;border:1px solid #252525;
  border-radius:13px;padding:14px 6px;text-align:center;
  cursor:pointer;transition:all .2s}
.cat.on,.cat:hover{background:var(--y);border-color:var(--y)}
.cat-dot{width:14px;height:14px;border-radius:7px;
  margin:0 auto 8px;transition:background .2s}
.cat.on .cat-dot,.cat:hover .cat-dot{background:#0C0C0A}
.cat-label{font-size:12px;font-weight:700;color:#666;transition:color .2s}
.cat.on .cat-label,.cat:hover .cat-label{color:#0C0C0A}

.stats{display:flex;border:1px solid #1c1c1c;
  border-radius:16px;overflow:hidden;margin-bottom:20px}
.stat{flex:1;padding:18px 8px;text-align:center;background:#111}
.stat+.stat{border-left:1px solid #1c1c1c}
.stat-n{font-family:var(--serif);font-size:26px;
  color:#fff;letter-spacing:-1px}
.stat-l{font-size:10px;color:#444;font-weight:700;
  letter-spacing:.7px;text-transform:uppercase;margin-top:3px}

.cta-btn{background:var(--y);border-radius:16px;padding:20px;
  text-align:center;cursor:pointer;margin-bottom:20px;
  transition:opacity .15s}
.cta-btn:hover{opacity:.92}
.cta-main{font-size:18px;font-weight:700;color:#0C0C0A;letter-spacing:.2px}
.cta-sub{font-size:12px;color:var(--yd);margin-top:4px;font-weight:600}

.proof{display:flex;align-items:center;gap:12px}
.faces{display:flex}
.face{width:32px;height:32px;border-radius:50%;
  border:2px solid #0C0C0A;margin-left:-8px;
  display:flex;align-items:center;justify-content:center;
  font-size:10px;font-weight:700}
.face:first-child{margin-left:0}
.proof-text{font-size:12px;color:#555;line-height:1.55}
.proof-text strong{color:#888}

.preview-card{background:#111;border:1px solid #1e1e1e;
  border-radius:16px;padding:18px}
.preview-label{font-size:10px;font-weight:700;color:#444;
  letter-spacing:.8px;text-transform:uppercase;margin-bottom:14px}
.preview-row{display:flex;align-items:center;gap:12px;
  background:#1a1a1a;border-radius:12px;padding:12px 14px;
  margin-bottom:8px;border:1px solid #222}
.pr-logo{width:36px;height:36px;border-radius:9px;
  display:flex;align-items:center;justify-content:center;
  font-size:12px;font-weight:900;flex-shrink:0}
.pr-name{font-size:13px;font-weight:700;color:#ddd}
.pr-eta{font-size:11px;color:#555;margin-top:2px}
.pr-price{margin-left:auto;font-family:var(--serif);
  font-size:18px;color:var(--y);letter-spacing:-1px}
.pr-best{background:var(--y);font-size:9px;font-weight:800;
  color:#0C0C0A;padding:2px 7px;border-radius:5px;margin-left:8px}

/* PAGE 2 */
.p2{background:var(--bg);min-height:100vh;display:flex;flex-direction:column}
.topbar{background:var(--card);border-bottom:1px solid var(--faint);
  padding:16px 40px;display:flex;align-items:center;gap:14px}
.back-btn{width:36px;height:36px;border-radius:10px;
  border:1px solid var(--faint);display:flex;align-items:center;
  justify-content:center;cursor:pointer;font-size:18px;
  color:var(--mid);background:var(--card)}
.tb-logo{font-family:var(--serif);font-size:22px;color:var(--ink)}
.tb-logo span{color:var(--yd)}
.tb-step{margin-left:auto;font-size:12px;font-weight:700;color:var(--mid)}

.p2-body{padding:40px;max-width:680px;margin:0 auto;width:100%;flex:1}
.step-track{display:flex;align-items:center;margin-bottom:36px}
.snode{width:32px;height:32px;border-radius:16px;display:flex;
  align-items:center;justify-content:center;font-size:13px;
  font-weight:700;flex-shrink:0;z-index:1}
.sline{flex:1;height:2px;background:var(--faint)}
.s-active{background:var(--y);color:#0C0C0A}
.s-future{background:var(--faint);color:var(--mid)}

.eyebrow{font-size:11px;font-weight:700;color:var(--yd);
  letter-spacing:1.2px;text-transform:uppercase;margin-bottom:10px}
h2{font-family:var(--serif);font-size:36px;color:var(--ink);
  letter-spacing:-1.5px;line-height:1.15;margin-bottom:10px}
.p2-sub{font-size:15px;color:var(--mid);line-height:1.6;margin-bottom:24px}

.detect-bar{display:flex;align-items:center;gap:12px;
  background:#F0EDE4;border:1px solid var(--faint);
  border-radius:13px;padding:14px 18px;margin-bottom:16px;
  cursor:pointer;transition:border-color .2s}
.detect-bar:hover{border-color:var(--ink)}
.detect-icon{width:34px;height:34px;border-radius:9px;
  background:#0C0C0A;display:flex;align-items:center;
  justify-content:center;flex-shrink:0}
.detect-title{font-size:14px;font-weight:700;color:var(--ink)}
.detect-sub{font-size:11px;color:var(--mid);margin-top:2px}

.form-card{background:var(--card);border-radius:20px;
  border:1px solid var(--faint);padding:24px;margin-bottom:16px}
.fl{font-size:11px;font-weight:700;color:var(--mid);
  letter-spacing:.8px;text-transform:uppercase;
  margin-bottom:8px;margin-top:16px}
.fl:first-child{margin-top:0}
input.fi{width:100%;background:#F8F6F0;border:1.5px solid var(--faint);
  border-radius:12px;padding:14px 16px;font-size:15px;color:var(--ink);
  font-family:var(--sans);outline:none;transition:border-color .2s}
input.fi:focus{border-color:var(--ink)}
.frow{display:flex;gap:12px;margin-top:14px}
.fgroup{flex:1;display:flex;flex-direction:column}

.why-box{background:#FDFBF5;border:1px solid var(--faint);
  border-radius:14px;padding:18px;margin-bottom:20px}
.why-title{font-size:11px;font-weight:700;color:var(--mid);
  letter-spacing:.6px;text-transform:uppercase;margin-bottom:12px}
.why-row{display:flex;align-items:flex-start;gap:10px;margin-bottom:10px}
.why-dot{width:7px;height:7px;border-radius:50%;
  background:var(--y);flex-shrink:0;margin-top:5px}
.why-text{font-size:13px;color:var(--mid);line-height:1.55}

.p2-cta{background:#0C0C0A;border-radius:16px;padding:20px;
  text-align:center;cursor:pointer;margin-bottom:12px;
  transition:opacity .15s}
.p2-cta:hover{opacity:.9}
.p2-cta-text{font-size:17px;font-weight:700;color:var(--y)}
.skip{text-align:center;padding:12px;font-size:13px;
  color:var(--mid);cursor:pointer}
.skip:hover{color:var(--ink)}

/* PAGE 3 */
.p3{background:var(--bg);min-height:100vh;display:flex;flex-direction:column}
.p3-topbar{background:var(--card);border-bottom:1px solid var(--faint);
  padding:14px 40px;display:flex;align-items:center;gap:12px}
.free-badge{margin-left:auto;background:#F0FDF4;
  border:1px solid #86efac;border-radius:20px;
  padding:5px 14px;font-size:11px;font-weight:700;color:#166534}

.p3-body{padding:24px 40px 140px;max-width:960px;margin:0 auto;width:100%}
.trip-card{background:var(--card);border-radius:14px;
  border:1px solid var(--faint);padding:14px 18px;
  margin-bottom:18px;display:flex;align-items:center;gap:14px}
.trip-pins{display:flex;flex-direction:column;
  align-items:center;gap:4px;flex-shrink:0}
.pin-y2{width:9px;height:9px;border-radius:50%;
  background:var(--y);border:2px solid #0C0C0A}
.pin-line{width:1.5px;height:12px;background:var(--faint)}
.pin-r{width:9px;height:9px;border-radius:50%;
  background:#EF4444;border:2px solid #0C0C0A}
.trip-from{font-size:12px;color:var(--mid);margin-bottom:3px}
.trip-to{font-size:15px;font-weight:700;color:var(--ink)}
.trip-dist{font-size:13px;font-weight:700;color:var(--mid);
  margin-left:auto;flex-shrink:0}

.cat-tabs{display:flex;gap:8px;margin-bottom:16px}
.ctab{padding:10px 22px;border-radius:24px;border:1px solid var(--faint);
  background:var(--card);font-size:14px;font-weight:700;
  color:var(--mid);cursor:pointer;transition:all .15s;white-space:nowrap}
.ctab.on{background:#0C0C0A;border-color:#0C0C0A;color:var(--y)}

.sort-row{display:flex;justify-content:space-between;
  align-items:center;margin-bottom:14px}
.sort-lbl{font-size:11px;font-weight:700;color:var(--mid);
  letter-spacing:.8px;text-transform:uppercase}
.sort-btns{display:flex;gap:6px}
.sbtn{padding:7px 14px;border-radius:9px;border:1px solid var(--faint);
  background:var(--card);font-size:12px;font-weight:700;
  color:var(--mid);cursor:pointer;transition:all .15s}
.sbtn.on{background:#0C0C0A;border-color:#0C0C0A;color:var(--y)}

.p3-grid{display:grid;grid-template-columns:1fr 1fr;
  gap:10px;margin-bottom:12px}
.pcard{background:var(--card);border-radius:15px;
  border:1px solid var(--faint);padding:16px;
  display:flex;align-items:flex-start;gap:12px;
  cursor:pointer;transition:border-color .15s;
  position:relative;overflow:hidden}
.pcard:hover{border-color:#bbb}
.pcard.best{border:2px solid var(--y)}
.pcard.sel{border:2px solid #0C0C0A}
.pcard-sel-bar{position:absolute;left:0;top:0;
  bottom:0;width:4px;background:#0C0C0A}
.plogo{width:46px;height:46px;border-radius:12px;
  display:flex;align-items:center;justify-content:center;
  font-size:14px;font-weight:900;flex-shrink:0;
  font-family:var(--sans)}
.pinfo{flex:1;min-width:0}
.pname{font-size:14px;font-weight:700;color:var(--ink)}
.pmeta{font-size:11px;color:var(--mid);margin-top:2px}
.ptags{display:flex;gap:5px;margin-top:8px;flex-wrap:wrap}
.ptag{font-size:10px;font-weight:700;padding:3px 8px;border-radius:6px}
.tg{background:#F0FDF4;color:#166534}
.tb{background:#EFF6FF;color:#1e40af}
.ta{background:#FFFBEB;color:#92400e}
.tm{background:#F8F6F0;color:var(--mid);border:1px solid var(--faint)}
.pprice{text-align:right;flex-shrink:0}
.price-big{font-family:var(--serif);font-size:20px;
  color:var(--ink);letter-spacing:-1px}
.price-label{font-size:10px;color:var(--mid);margin-top:1px}
.eta-chip{background:var(--bg);border-radius:7px;padding:3px 9px;
  font-size:11px;font-weight:700;color:var(--ink);
  margin-top:5px;display:inline-block}
.best-badge{background:var(--y);font-size:9px;font-weight:800;
  color:#0C0C0A;padding:2px 8px;border-radius:5px;
  letter-spacing:.5px;position:absolute;top:10px;right:12px}

.disclaimer{font-size:11px;color:var(--mid);text-align:center;
  line-height:1.6;padding:14px;border-top:1px solid var(--faint)}

.p3-footer{position:fixed;bottom:0;left:0;right:0;
  background:var(--card);border-top:1px solid var(--faint);
  padding:16px 40px 24px;display:flex;align-items:center;
  justify-content:center;gap:20px;z-index:50}
.footer-inner{display:flex;align-items:center;
  justify-content:space-between;gap:20px;
  width:100%;max-width:960px}
.sel-info{flex:1;min-width:0}
.sel-name{font-size:15px;font-weight:700;color:var(--ink)}
.sel-price{font-size:12px;color:var(--mid);margin-top:2px}
.open-btn{background:#0C0C0A;border-radius:14px;
  padding:14px 28px;font-size:15px;font-weight:700;
  color:var(--y);cursor:pointer;white-space:nowrap;flex-shrink:0}
.open-btn:hover{opacity:.88}

@keyframes fadeUp{
  from{opacity:0;transform:translateY(6px)}
  to{opacity:1;transform:translateY(0)}
}

@media(max-width:700px){
  .p1-body{grid-template-columns:1fr;gap:32px;padding:0 24px 40px}
  .p1-right{display:none}
  .p1-nav,.topbar,.p3-topbar{padding-left:24px;padding-right:24px}
  .p2-body,.p3-body{padding-left:20px;padding-right:20px}
  .p3-grid{grid-template-columns:1fr}
  .p3-footer{padding-left:20px;padding-right:20px}
}
</style>
</head>
<body>

<div class="nav-bar">
  <button class="nd on" onclick="goTo(0)"></button>
  <button class="nd"    onclick="goTo(1)"></button>
  <button class="nd"    onclick="goTo(2)"></button>
  <span class="pg-label" id="pg-lbl">Page 1 of 3 — Welcome</span>
</div>


<!-- PAGE 1 -->
<div class="page active" id="pg0">
<div class="p1">

  <div class="p1-nav">
    <div class="logo">
      Cab<div class="logo-zero">0</div>
      <span class="logo-ext">.com</span>
    </div>
    <div class="free-chip">100% FREE</div>
  </div>

  <div class="p1-body">
    <div class="p1-left">
      <div class="kicker">
        <div class="kicker-dot"></div>
        <span class="kicker-text">No fees · No sign-up · No API keys</span>
      </div>
      <h1>Every ride.<br><em>Every delivery.</em><br>One search.</h1>
      <p class="p1-sub">Compare Uber, Lyft, DoorDash, Instacart and 16 more platforms side by side — instantly. Cab0 is completely free, always.</p>
      <div class="search-bar" onclick="goTo(1)">
        <div class="pin-y"></div>
        <span class="search-ph">Where are you going?</span>
        <div class="search-btn">→</div>
      </div>
      <div class="cats">
        <div class="cat on" onclick="pickCat(this)">
          <div class="cat-dot" style="background:#FACC15"></div>
          <div class="cat-label">Rides</div>
        </div>
        <div class="cat" onclick="pickCat(this)">
          <div class="cat-dot" style="background:#f97316"></div>
          <div class="cat-label">Food</div>
        </div>
        <div class="cat" onclick="pickCat(this)">
          <div class="cat-dot" style="background:#22c55e"></div>
          <div class="cat-label">Grocery</div>
        </div>
      </div>
      <div class="stats">
        <div class="stat">
          <div class="stat-n">20</div>
          <div class="stat-l">Providers</div>
        </div>
        <div class="stat">
          <div class="stat-n">$0</div>
          <div class="stat-l">Cab0 fee</div>
        </div>
        <div class="stat">
          <div class="stat-n">3</div>
          <div class="stat-l">Taps to book</div>
        </div>
      </div>
      <div class="cta-btn" onclick="goTo(1)">
        <div class="cta-main">Get started — it's free →</div>
        <div class="cta-sub">Set your address in 20 seconds</div>
      </div>
      <div class="proof">
        <div class="faces">
          <div class="face" style="background:#2d3748;color:#a0aec0">JR</div>
          <div class="face" style="background:#744210;color:#f6ad55">MA</div>
          <div class="face" style="background:#1a365d;color:#90cdf4">TK</div>
          <div class="face" style="background:#276749;color:#9ae6b4">SL</div>
        </div>
        <div class="proof-text">
          <strong>Trusted by thousands</strong> of daily commuters.<br>
          Save money on every single trip.
        </div>
      </div>
    </div>

    <div class="p1-right">
      <div class="preview-card">
        <div class="preview-label">Live comparison — rides</div>
        <div class="preview-row">
          <div class="pr-logo" style="background:#000;color:#fff">Ub</div>
          <div>
            <div class="pr-name">Uber X <span class="pr-best">BEST</span></div>
            <div class="pr-eta">6 min · 4.8 stars</div>
          </div>
          <div class="pr-price">$9–$11</div>
        </div>
        <div class="preview-row">
          <div class="pr-logo" style="background:#E91E8C;color:#fff">Ly</div>
          <div>
            <div class="pr-name">Lyft</div>
            <div class="pr-eta">7 min · 4.7 stars</div>
          </div>
          <div class="pr-price">$10–$13</div>
        </div>
        <div class="preview-row">
          <div class="pr-logo" style="background:#1FB954;color:#fff">Via</div>
          <div>
            <div class="pr-name">Via Share</div>
            <div class="pr-eta">16 min · 4.5 stars</div>
          </div>
          <div class="pr-price">$6–$8</div>
        </div>
        <div class="preview-row">
          <div class="pr-logo" style="background:#2563EB;color:#fff">Crb</div>
          <div>
            <div class="pr-name">Curb Taxi</div>
            <div class="pr-eta">10 min · 4.4 stars</div>
          </div>
          <div class="pr-price">$13–$18</div>
        </div>
      </div>
    </div>
  </div>

</div>
</div>


<!-- PAGE 2 -->
<div class="page" id="pg1">
<div class="p2">

  <div class="topbar">
    <div class="back-btn" onclick="goTo(0)">←</div>
    <div class="tb-logo">Cab<span>0</span>.com</div>
    <div class="tb-step">Step 1 of 2</div>
  </div>

  <div class="p2-body">
    <div class="step-track">
      <div class="snode s-active">1</div>
      <div class="sline"></div>
      <div class="snode s-future">2</div>
      <div class="sline"></div>
      <div class="snode s-future">3</div>
    </div>
    <div class="eyebrow">Quick setup</div>
    <h2>Set your home address</h2>
    <p class="p2-sub">Save it once — Cab0 pre-fills your pickup every time. No account ever needed.</p>

    <div class="detect-bar" onclick="fillAddress()">
      <div class="detect-icon">
        <svg width="18" height="18" viewBox="0 0 16 16" fill="none">
          <circle cx="8" cy="8" r="2.5" fill="#FACC15"/>
          <circle cx="8" cy="8" r="5" stroke="#FACC15" stroke-width="1.5" fill="none"/>
          <line x1="8" y1="1" x2="8" y2="3" stroke="#FACC15" stroke-width="1.5" stroke-linecap="round"/>
          <line x1="8" y1="13" x2="8" y2="15" stroke="#FACC15" stroke-width="1.5" stroke-linecap="round"/>
          <line x1="1" y1="8" x2="3" y2="8" stroke="#FACC15" stroke-width="1.5" stroke-linecap="round"/>
          <line x1="13" y1="8" x2="15" y2="8" stroke="#FACC15" stroke-width="1.5" stroke-linecap="round"/>
        </svg>
      </div>
      <div>
        <div class="detect-title">Use my current location</div>
        <div class="detect-sub">Auto-detect address via GPS</div>
      </div>
    </div>

    <div class="form-card">
      <div class="fl">Street address</div>
      <input class="fi" id="f-street" type="text" placeholder="290 Riverside Drive">
      <div class="fl">City</div>
      <input class="fi" id="f-city" type="text" placeholder="Newport News">
      <div class="frow">
        <div class="fgroup">
          <div class="fl" style="margin-top:0">State</div>
          <input class="fi" id="f-state" type="text" placeholder="VA" maxlength="2" style="text-transform:uppercase">
        </div>
        <div class="fgroup" style="flex:1.5">
          <div class="fl" style="margin-top:0">ZIP code</div>
          <input class="fi" id="f-zip" type="text" placeholder="23601" maxlength="5">
        </div>
      </div>
    </div>

    <div class="why-box">
      <div class="why-title">Why we ask</div>
      <div class="why-row">
        <div class="why-dot"></div>
        <div class="why-text">Pre-fills your pickup so you never retype your address again</div>
      </div>
      <div class="why-row">
        <div class="why-dot"></div>
        <div class="why-text">Stored only on your device — never sent to any server</div>
      </div>
      <div class="why-row">
        <div class="why-dot"></div>
        <div class="why-text">Cab0 earns $0 from your data — we never sell or share it</div>
      </div>
    </div>

    <div class="p2-cta" onclick="goTo(2)">
      <div class="p2-cta-text">Save &amp; compare options →</div>
    </div>
    <div class="skip" onclick="goTo(2)">Skip for now — set it later</div>
  </div>

</div>
</div>


<!-- PAGE 3 -->
<div class="page" id="pg2">
<div class="p3">

  <div class="p3-topbar">
    <div class="back-btn" onclick="goTo(1)">←</div>
    <div class="tb-logo" style="font-family:var(--serif);font-size:22px;color:var(--ink)">
      Cab<span style="color:var(--yd)">0</span>.com
    </div>
    <div class="free-badge">FREE forever</div>
  </div>

  <div class="p3-body">
    <div class="trip-card">
      <div class="trip-pins">
        <div class="pin-y2"></div>
        <div class="pin-line"></div>
        <div class="pin-r"></div>
      </div>
      <div style="flex:1;min-width:0">
        <div class="trip-from" id="trip-from">290 Riverside Dr, Newport News</div>
        <div class="trip-to">Newport News Airport (PHF)</div>
      </div>
      <div class="trip-dist">6.2 mi</div>
    </div>

    <div class="cat-tabs">
      <div class="ctab on" onclick="switchCat('ride',this)">Rides</div>
      <div class="ctab"    onclick="switchCat('food',this)">Food</div>
      <div class="ctab"    onclick="switchCat('grocery',this)">Grocery</div>
    </div>

    <div class="sort-row">
      <div class="sort-lbl">Sort by</div>
      <div class="sort-btns">
        <div class="sbtn on" onclick="sortBy('price',this)">Price</div>
        <div class="sbtn"    onclick="sortBy('eta',this)">Speed</div>
        <div class="sbtn"    onclick="sortBy('rating',this)">Rating</div>
      </div>
    </div>

    <div class="p3-grid" id="p3-grid"></div>

    <div class="disclaimer">
      Estimates calculated from publicly available per-mile rate tables.
      Actual fares set by each provider. Cab0 charges nothing — ever.
      Tapping any option opens the provider's own app to complete your booking.
    </div>
  </div>

  <div class="p3-footer">
    <div class="footer-inner">
      <div class="sel-info">
        <div class="sel-name" id="sel-name">Select an option above</div>
        <div class="sel-price" id="sel-price">Cab0 is always free — $0 fee</div>
      </div>
      <div class="open-btn" onclick="openProvider()">Open app →</div>
    </div>
  </div>

</div>
</div>


<script>
var currentCat  = 'ride';
var currentSort = 'price';
var selectedId  = null;

var PAGE_LABELS = [
  'Page 1 of 3 — Welcome',
  'Page 2 of 3 — Home address',
  'Page 3 of 3 — Compare providers'
];

var PROVIDERS = {
  ride: [
    { id:'uber_x',  name:'Uber X',      s:'Ub',  c:'#000000', t:'#fff',
      p:[9,11],   eta:6,  r:4.8, tags:['Most popular','3 min away'],  tc:['tg','tb'] },
    { id:'lyft',    name:'Lyft',        s:'Ly',  c:'#E91E8C', t:'#fff',
      p:[10,13],  eta:7,  r:4.7, tags:['Competitive','US & Canada'],  tc:['tg','tb'] },
    { id:'via',     name:'Via Share',   s:'Via', c:'#1FB954', t:'#fff',
      p:[6,8],    eta:16, r:4.5, tags:['Cheapest','Shared ride'],     tc:['tg','tm'] },
    { id:'uber_c',  name:'Uber Comfort',s:'UC',  c:'#222222', t:'#fff',
      p:[14,17],  eta:8,  r:4.9, tags:['Extra legroom','Quiet mode'], tc:['ta','tm'] },
    { id:'uber_xl', name:'Uber XL',     s:'UXL', c:'#333333', t:'#fff',
      p:[16,20],  eta:9,  r:4.7, tags:['6 seats','Groups'],           tc:['tb','tm'] },
    { id:'lyft_xl', name:'Lyft XL',    s:'LXL', c:'#C2185B', t:'#fff',
      p:[17,22],  eta:11, r:4.6, tags:['SUV','6 passengers'],         tc:['tb','tm'] },
    { id:'curb',    name:'Curb Taxi',   s:'Crb', c:'#2563EB', t:'#fff',
      p:[13,18],  eta:10, r:4.4, tags:['Licensed taxi','Meter rate'], tc:['tb','tm'] }
  ],
  food: [
    { id:'doordash', name:'DoorDash',  s:'DD', c:'#FF3008', t:'#fff',
      p:[2.99,4.99], eta:28, r:4.6, tags:['#1 in US','Fastest'],      tc:['tg','tb'] },
    { id:'ubereats', name:'Uber Eats', s:'UE', c:'#06C167', t:'#000',
      p:[3.49,5.99], eta:22, r:4.7, tags:['Global reach','Uber One'], tc:['tg','ta'] },
    { id:'gopuff',   name:'Gopuff',   s:'GP', c:'#5B21B6', t:'#FCD34D',
      p:[3.95,3.95], eta:25, r:4.4, tags:['Flat fee','30 min'],       tc:['tg','ta'] },
    { id:'grubhub',  name:'Grubhub',  s:'GH', c:'#F97316', t:'#fff',
      p:[3.99,6.49], eta:34, r:4.4, tags:['Wide selection','Dinner'], tc:['tb','ta'] },
    { id:'postmates',name:'Postmates',s:'PM', c:'#111827', t:'#FCD34D',
      p:[4.99,7.99], eta:30, r:4.3, tags:['Alcohol + food','24hr'],   tc:['ta','tm'] },
    { id:'caviar',   name:'Caviar',   s:'Cv', c:'#7C3AED', t:'#fff',
      p:[4.99,7.49], eta:40, r:4.6, tags:['Premium picks','Upscale'], tc:['ta','tm'] }
  ],
  grocery: [
    { id:'instacart',name:'Instacart',    s:'IC', c:'#00AD31', t:'#fff',
      p:[3.99,5.99], eta:55, r:4.7, tags:['500+ stores','Same-day'],  tc:['tg','tb'] },
    { id:'amazon',   name:'Amazon Fresh', s:'Az', c:'#FF9900', t:'#000',
      p:[0,0],       eta:90, r:4.8, tags:['Free w/ Prime','Reliable'],tc:['tg','tb'] },
    { id:'walmart',  name:'Walmart+',     s:'Wm', c:'#0071DC', t:'#fff',
      p:[0,0],       eta:75, r:4.5, tags:['Lowest prices','Free+'],   tc:['tg','tb'] },
    { id:'shipt',    name:'Shipt/Target', s:'Sh', c:'#CC0000', t:'#fff',
      p:[7.99,9.99], eta:80, r:4.6, tags:['Target partner','Shopper'],tc:['tb','tm'] }
  ]
};

function goTo(n) {
  document.querySelectorAll('.page').forEach(function(p,i){
    p.classList.toggle('active', i===n);
  });
  document.querySelectorAll('.nd').forEach(function(d,i){
    d.classList.toggle('on', i===n);
  });
  document.getElementById('pg-lbl').textContent = PAGE_LABELS[n];
  if (n===2) renderProviders();
}

function pickCat(el) {
  document.querySelectorAll('.cat').forEach(function(c){ c.classList.remove('on'); });
  el.classList.add('on');
}

function fillAddress() {
  document.getElementById('f-street').value = '290 Riverside Drive';
  document.getElementById('f-city').value   = 'Newport News';
  document.getElementById('f-state').value  = 'VA';
  document.getElementById('f-zip').value    = '23601';
  var fromEl = document.getElementById('trip-from');
  if (fromEl) fromEl.textContent = '290 Riverside Dr, Newport News';
}

function switchCat(cat, el) {
  currentCat = cat;
  selectedId = null;
  document.querySelectorAll('.ctab').forEach(function(t){ t.classList.remove('on'); });
  el.classList.add('on');
  renderProviders();
}

function sortBy(mode, el) {
  currentSort = mode;
  document.querySelectorAll('.sbtn').forEach(function(b){ b.classList.remove('on'); });
  el.classList.add('on');
  renderProviders();
}

function formatPrice(p) {
  if (p[0]===0 && p[1]===0) return 'FREE';
  if (currentCat==='ride')   return '$'+p[0]+'–$'+p[1];
  if (p[0]===p[1])           return '$'+p[0].toFixed(2);
  return '$'+p[0].toFixed(2)+'–$'+p[1].toFixed(2);
}

function renderProviders() {
  var list = (PROVIDERS[currentCat]||[]).slice();
  if (currentSort==='price')  list.sort(function(a,b){ return a.p[0]-b.p[0]; });
  if (currentSort==='eta')    list.sort(function(a,b){ return a.eta-b.eta; });
  if (currentSort==='rating') list.sort(function(a,b){ return b.r-a.r; });
  if (!selectedId && list.length) selectedId = list[0].id;
  var html = '';
  list.forEach(function(p,i){
    var isBest = (i===0);
    var isSel  = (p.id===selectedId);
    var tagHtml = p.tags.map(function(tag,ti){
      return '<span class="ptag '+p.tc[ti]+'">'+tag+'</span>';
    }).join('');
    html +=
      '<div class="pcard'+(isBest?' best':'')+(isSel?' sel':'')+'"'
      +' onclick="selectProvider(\''+p.id+'\')"'
      +' style="animation:fadeUp .2s '+(i*0.05)+'s both">'
      +(isSel?'<div class="pcard-sel-bar"></div>':'')
      +(isBest?'<div class="best-badge">BEST MATCH</div>':'')
      +'<div class="plogo" style="background:'+p.c+';color:'+p.t+'">'+p.s+'</div>'
      +'<div class="pinfo">'
      +'<div class="pname">'+p.name+'</div>'
      +'<div class="pmeta">'+p.r+' ★  ·  '+p.eta+' min ETA</div>'
      +'<div class="ptags">'+tagHtml+'</div>'
      +'</div>'
      +'<div class="pprice">'
      +'<div class="price-big">'+formatPrice(p.p)+'</div>'
      +'<div class="price-label">'+(currentCat==='ride'?'estimated':'delivery fee')+'</div>'
      +'<div class="eta-chip">'+p.eta+' min</div>'
      +'</div>'
      +'</div>';
  });
  document.getElementById('p3-grid').innerHTML = html;
  updateFooter(list);
}

function selectProvider(id) {
  selectedId = id;
  renderProviders();
}

function updateFooter(list) {
  var p = list.find(function(x){ return x.id===selectedId; });
  if (!p) return;
  document.getElementById('sel-name').textContent  = p.name+' selected';
  document.getElementById('sel-price').textContent =
    'est. '+formatPrice(p.p)+' · '+p.eta+' min · $0.00 Cab0 fee';
}

function openProvider() {
  var list = PROVIDERS[currentCat]||[];
  var p    = list.find(function(x){ return x.id===selectedId; });
  if (!p) return;
  var btn  = document.querySelector('.open-btn');
  var orig = btn.textContent;
  btn.textContent      = 'Opening '+p.name+'…';
  btn.style.background = '#166534';
  btn.style.color      = '#fff';
  setTimeout(function(){
    btn.textContent      = orig;
    btn.style.background = '#0C0C0A';
    btn.style.color      = 'var(--y)';
  }, 2000);
}
</script>

</body>
</html>
