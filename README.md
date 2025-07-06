<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>BMI計算アプリ</title>
  <style>
    body {
      font-family: sans-serif;
      background-color: #fcefee;
      text-align: center;
      padding: 20px;
    }
    .container {
      background: #fff;
      padding: 20px;
      border-radius: 15px;
      max-width: 400px;
      margin: auto;
      box-shadow: 0 0 10px #ccc;
    }
    input, button {
      margin: 10px 0;
      padding: 10px;
      width: 80%;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      background-color: #ff88a0;
      color: white;
      border: none;
    }
    .result {
      margin-top: 20px;
      font-weight: bold;
    }
    .info {
      margin-top: 30px;
      font-size: 14px;
      color: #555;
      background: #fff8f8;
      padding: 10px;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>BMI計算アプリ</h1>
    <p>身長と体重を入力してBMIを計算します。</p>
    <input type="number" id="height" placeholder="身長（cm）" />
    <input type="number" id="weight" placeholder="体重（kg）" />
    <button onclick="calc()">計算する</button>
    <div class="result" id="result"></div>
    <div class="info">
      <strong>BMIの目安</strong><br>
      18.5未満：低体重<br>
      18.5～24.9：標準体重<br>
      25以上：肥満
    </div>
  </div>
  <script>
    function calc() {
      const h = parseFloat(document.getElementById("height").value);
      const w = parseFloat(document.getElementById("weight").value);
      const res = document.getElementById("result");

      if (!h || !w) {
        res.textContent = "身長と体重を入力してください。";
        return;
      }
      const bmi = w / ((h / 100) ** 2);
      const result = "あなたのBMIは " + bmi.toFixed(1) + " です。";
      res.textContent = result;
    }
  </script>
</body>
</html>
