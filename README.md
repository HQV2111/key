<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>KEY</title>
  <style>
    body {
      background-color: #36021b;
      color: #f976b4;
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 100px;
    }

    .envelope {
      background: linear-gradient(to top, #b30000 50%, #1a1a1a 50%);
      width: 200px;
      height: 200px;
      margin: 50px auto;
      border-radius: 5px;
      cursor: pointer;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .key-text {
      color: #fff;
      font-size: 18px;
    }

    .copied {
      color: lightgreen;
      margin-top: 20px;
      display: none;
    }
  </style>
</head>
<body>
  <h1>KEY</h1>
  <p>Chúc mừng bạn đã nhận được key thành công!</p>
  <p>Nhấn vào phong bì để copy key</p>

  <div class="envelope" onclick="copyKey()">
    <span class="key-text" id="keyText">abc123xyz</span>
  </div>
  <div class="copied" id="copiedMsg">Đã copy key!</div>

  <script>
    function copyKey() {
      const key = document.getElementById("keyText").textContent;
      navigator.clipboard.writeText(key).then(() => {
        document.getElementById("copiedMsg").style.display = "block";
        setTimeout(() => {
          document.getElementById("copiedMsg").style.display = "none";
        }, 2000);
      });
    }
  </script>
</body>
</html>
