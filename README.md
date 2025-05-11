<!DOCTYPE html>
<html>
  <head>
    <title>Gift Seller</title>
    <meta charset="utf-8">
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
      body { font-family: sans-serif; padding: 20px; background: #f3f3f3; }
      button { padding: 10px 20px; font-size: 18px; margin-top: 20px; }
    </style>
  </head>
  <body>
    <h2>Привет, <span id="username">...</span>!</h2>
    <p>Отправь сюда скрин своих подарков, и мы предложим цену.</p>
    <button onclick="confirmSend()">Хочу продать</button>

    <script>
      const tg = window.Telegram.WebApp;
      tg.expand();

      document.getElementById("username").innerText = tg.initDataUnsafe?.user?.first_name || "пользователь";

      function confirmSend() {
        tg.sendData("SELL_GIFT");
        alert("Отправьте скрин подарка в чат с ботом!");
      }
    </script>
  </body>
</html>
