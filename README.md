<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body { font-family: sans-serif; margin: 0; background: #000; color: #fff; height: 100vh; display: flex; flex-direction: column; overflow: hidden; }
        .header { padding: 40px; text-align: center; font-size: 36px; font-weight: bold; border-bottom: 2px solid #333; color: #ffcc00; }
        .status-bar { background: #111; padding: 10px; text-align: center; color: #00ff00; font-size: 14px; font-family: monospace; border-bottom: 1px solid #222; }
        .content { flex-grow: 1; display: flex; align-items: center; justify-content: center; background: #111; color: #444; font-size: 18px; letter-spacing: 2px; }
        .footer { padding: 40px; background: #222; }
        .button { background: #ffcc00; color: #000; padding: 25px; width: 100%; border: none; border-radius: 12px; font-size: 24px; font-weight: bold; cursor: pointer; }
    </style>
</head>
<body>
    <div class="header">CAB0.COM</div>
    <div class="status-bar">SYSTEM ACTIVE // GPS SECURED</div>
    <div class="content">READY FOR LOGISTICS INPUT</div>
    <div class="footer">
        <button class="button" onclick="alert('SEARCHING FOR NEAREST COURIER...')">REQUEST PROTOTYPE</button>
    </div>
</body>
</html>
