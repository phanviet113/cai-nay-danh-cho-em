TYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mở khóa đoạn ghi âm</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        text-align: center;
        margin-top: 50px;
      }
      .container {
        max-width: 400px;
        margin: auto;
        padding: 20px;
        border: 1px solid #ccc;
        border-radius: 10px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      }
      input[type="password"] {
        width: 100%;
        padding: 10px;
        margin: 10px 0;
        border: 1px solid #ccc;
        border-radius: 5px;
      }
      button {
        padding: 10px 20px;
        border: none;
        background-color: #28a745;
        color: white;
        border-radius: 5px;
        cursor: pointer;
      }
      button:hover {
        background-color: #218838;
      }
      .audio-container {
        display: none;
        margin-top: 20px;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h2>Nhập mật khẩu để mở khóa đoạn ghi âm</h2>
      <input type="password" id="password" placeholder="Nhập mật khẩu">
      <button onclick="unlockAudio()">Mở khóa</button>
      <div class="audio-container" id="audioContainer">
        <h3>Đoạn ghi âm của bạn:</h3>
        <audio controls>
          <source src="https://drive.google.com/file/d/1Mm_gpW-8RicUq8dFDpIj2U1b6Di-pCpg/view?usp=drive_link" type="audio/mpeg">
          Trình duyệt của bạn không hỗ trợ audio.
        </audio>
      </div>
    </div>

    <script>
      function unlockAudio() {
        const correctPassword = "iuemne"; // Thay bằng mật khẩu của bạn
        const inputPassword = document.getElementById("password").value;
        const audioContainer = document.getElementById("audioContainer");

        if (inputPassword === correctPassword) {
          audioContainer.style.display = "block"; // Hiển thị đoạn ghi âm
        } else {
          alert("Sai mật khẩu! Vui lòng thử lại.");
        }
      }
    </script>
  </body>
  </html>
