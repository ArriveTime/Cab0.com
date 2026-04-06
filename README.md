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

.cat-tabs{display:flex;gap:6px;margin-bottom:14px}
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
.ptag{font-size:10
