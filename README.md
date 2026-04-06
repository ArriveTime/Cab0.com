<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cab0.com | Logistics Engine</title>
    <style>
        body { margin: 0; padding: 0; background-color: #000; color: #fff; font-family: 'Helvetica', sans-serif; height: 100vh; display: flex; flex-direction: column; overflow: hidden; }
        .header { background: #000; padding: 50px 20px; text-align: center; border-bottom: 3px solid #333; }
        .logo { color: #FFCC00; font-size: 48px; font-weight: 900; letter-spacing: 4px; }
        .status-box { background: #111; padding: 15px; text-align: center; border-bottom: 1px solid #222; }
        .status-text { color: #00FF00; font-family: monospace; font-size: 16px; text-transform: uppercase; }
        .main-display { flex-grow: 1; display: flex; flex-direction: column; align-items: center; justify-content: center; background: #080808; }
        .ready-text { color: #555; font-size: 22px; font-weight: bold; letter-spacing: 1px; }
        .footer { padding: 40px; background: #1a1a1a; }
        .request-btn { background-color: #FFCC00; color: #000; border: none; padding: 30px; width: 100%; border-radius: 15px; font-size: 28px; font-weight: 900; cursor: pointer; text-transform: uppercase; box-shadow: 0 4px 15px rgba(255, 204, 0, 0.3); }
    </style>
</head>
<body>
    <div class="header"><div class="logo">CAB0.COM</div></div>
    <div class="status-box"><div class="status-text">● SYSTEM ACTIVE // GPS SECURED</div></div>
    <div class="main-display"><div class="ready-text">READY FOR LOGISTICS INPUT</div></div>
    <div class="footer">
        <button class="request-btn" onclick="alert('SYSTEM INITIALIZING: Locating nearest logistics hubs...')">REQUEST PROTOTYPE</button>
    </div>
</body>
</html>
