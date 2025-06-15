# Earn-Online  <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>YouTube Earn Platform</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      background-color: #f9f9f9;
    }
    h1, h2 {
      text-align: center;
    }
    .container {
      max-width: 700px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    }
    iframe {
      display: block;
      margin: 20px auto;
      width: 100%;
      height: 315px;
    }
    .section {
      margin: 20px 0;
    }
    button {
      display: inline-block;
      padding: 10px 20px;
      margin-top: 10px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    input[type="text"] {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
    }
    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Earn Online by Watching YouTube Videos</h1>

    <div class="section">
      <h2>Watch Video & Earn $0.2</h2>
      <iframe id="video" src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allowfullscreen></iframe>
      <button onclick="earnMoney()">I Watched the Video</button>
      <p><strong>Balance: $<span id="balance">0.00</span></strong></p>
    </div>

    <div class="section">
      <h2>Referral Program</h2>
      <p>Share this link to earn $0.1 per referral:</p>
      <input type="text" value="https://yourwebsite.com/?ref=yourcode" readonly />
    </div>

    <div class="section">
      <h2>Withdraw Earnings</h2>
      <p>You can request withdrawal after reaching $1</p>
      <button onclick="withdraw()">Request Withdrawal</button>
      <p id="withdrawMessage" class="hidden"></p>
    </div>
  </div>

  <script>
    let balance = 0;

    function earnMoney() {
      balance += 0.2;
      document.getElementById("balance").textContent = balance.toFixed(2);
      alert("$0.2 has been added to your balance!");
    }

    function withdraw() {
      const message = document.getElementById("withdrawMessage");
      if (balance >= 1) {
        message.textContent = "Withdrawal request submitted!";
        message.style.color = "green";
        balance = 0;
        document.getElementById("balance").textContent = balance.toFixed(2);
      } else {
        message.textContent = "You need at least $1 to withdraw.";
        message.style.color = "red";
      }
      message.classList.remove("hidden");
    }
  </script>
</body>
</html>
