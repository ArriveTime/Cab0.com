<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body { font-family: sans-serif; margin: 0; background: #000; color: #fff; height: 100vh; display: flex; flex-direction: column; }
        .header { padding: 40px; text-align: center; font-size: 36px; font-weight: bold; border-bottom: 2px solid #333; color: #ffcc00; }
        .content { flex-grow: 1; display: flex; align-items: center; justify-content: center; background: #111; color: #888; font-size: 20px; text-transform: uppercase; }
        .footer { padding: 40px; background: #222; }
        .button { background: #ffcc00; color: #000; padding: 25px; width: 100%; border: none; border-radius: 12px; font-size: 24px; font-weight: bold; cursor: pointer; }
    </style>
</head>
<body>
    <div class="header">CAB0.COM</div>
    <div class="content">Logistics Engine Ready</div>
    <div class="footer">
        <button class="button" onclick="alert('System Initializing... Searching for Logistics Hubs.')">REQUEST PROTOTYPE</button>
    </div>
</body>
</html>
