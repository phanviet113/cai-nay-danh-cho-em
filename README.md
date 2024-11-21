<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bức Thư Bí Mật</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      text-align: center;
      background: linear-gradient(to top, #87CEFA, #FFB6C1);
      overflow: hidden;
      height: 100vh;
    }

    .container {
      position: absolute;
      top: 30%;
      left: 50%;
      transform: translate(-50%, -50%);
      padding: 20px;
      background: rgba(255, 255, 255, 0.7);
      border-radius: 10px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
    }

    input[type="password"] {
      padding: 10px;
      width: 80%;
      margin: 10px 0;
      border: 2px solid #d81b60;
      border-radius: 5px;
    }

    button {
      padding: 10px 20px;
      border: none;
      background-color: #d81b60;
      color: white;
      border-radius: 5px;
      font-size: 1em;
      cursor: pointer;
    }

    button:hover {
      background-color: #ad1457;
    }

    /* Bao thư */
    .envelope {
      width: 300px;
      height: 150px;
      background-color: #ffebcd;
      border-radius: 15px;
      position: relative;
      margin: 0 auto;
      overflow: hidden;
      transition: all 1s ease;
      transform-origin: top;
    }

    .envelope .flap-top,
    .envelope .flap-bottom {
      position: absolute;
      width: 100%;
      height: 50%;
      background-color: #dcdcdc;
      z-index: 1;
      transition: all 1s ease;
    }

    .envelope .flap-top {
      top: 0;
      clip-path: polygon(0% 100%, 100% 100%, 100% 0%, 0% 0%);
    }

    .envelope .flap-bottom {
      bottom: 0;
      clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%);
    }

    /* Lá thư */
    .letter {
      width: 260px;
      height: 100px;
      background-color: #fff;
      border-radius: 5px;
      position: absolute;
      top: 25%;
      left: 50%;
      transform: translateX(-50%);
      padding: 20px;
      box-sizing: border-box;
      display: none;
      z-index: 2;
      opacity: 0;
      transition: opacity 1s ease-in-out;
    }

    /* Nội dung thư */
    #message {
      font-size: 1.2em;
      color: #333;
      line-height: 1.6;
    }
  </style>
</head>
<body>

  <div class="container">
    <h2>Nhập mật khẩu để mở bức thư</h2>
    <input type="password" id="password" placeholder="Nhập mật khẩu">
    <button onclick="unlockLetter()">Mở thư</button>
  </div>

  <!-- Bao thư -->
  <div class="envelope" id="envelope">
    <div class="flap-top"></div>
    <div class="flap-bottom"></div>
    <div class="letter" id="letter">
      <div id="message">
       Hôm nay là ngày 21 tháng 11 năm 2024, và anh muốn viết những dòng này cho em từ bây giờ vì anh muốn chuẩn bị thật tốt cho mọi thứ. Em là người đặc biệt với anh, và anh cũng muốn món quà này dành cho em phải thật sự đặc biệt.

Anh hy vọng rằng vào ngày 3/12, chúng ta sẽ chính thức bước vào một mối quan hệ mới. Nếu mọi thứ diễn ra tốt đẹp, đó sẽ là thời điểm mà chúng ta bắt đầu cùng nhau, không chỉ là những cuộc trò chuyện nữa mà là sự đồng hành thật sự. Anh rất vui và hạnh phúc vì em đã đến bên anh, cho anh cơ hội để yêu thương và quan tâm em.

Anh hiểu rằng trong một mối quan hệ, không phải lúc nào cũng hoàn hảo. Sẽ có những lúc chúng ta không đồng quan điểm, nhưng anh mong rằng thay vì cãi nhau, chúng ta sẽ luôn tìm cách trò chuyện và hiểu nhau hơn. Nếu em gặp phải bất kỳ điều gì khiến em buồn hoặc khó chịu, đừng ngần ngại chia sẻ với anh. Anh luôn sẵn sàng lắng nghe và ở đây để cùng em vượt qua mọi khó khăn.

Cuộc sống sẽ không phải lúc nào cũng dễ dàng. Công việc, học tập, gia đình… những vấn đề đó đôi khi có thể làm chúng ta cảm thấy căng thẳng và mệt mỏi. Nhưng anh hy vọng chúng ta sẽ luôn bên nhau để giúp đỡ nhau, thay vì để những áp lực đó làm ảnh hưởng đến chúng ta. Em luôn có anh ở đây, sẵn sàng hỗ trợ khi em cần.

Cảm ơn em vì đã đọc những dòng này. Anh yêu em, rất nhiều.!
      </div>
    </div>
  </div>

  <script>
    function unlockLetter() {
      const correctPassword = "iuemnhieu";  // Thay mật khẩu tại đây
      const inputPassword = document.getElementById("password").value;
      const envelope = document.getElementById("envelope");
      const letter = document.getElementById("letter");

      if (inputPassword === correctPassword) {
        // Mở bao thư
        envelope.style.transform = "rotateX(180deg)";
        envelope.style.transition = "transform 2s ease-in-out";

        // Hiển thị lá thư
        setTimeout(function() {
          letter.style.display = "block";
          letter.style.opacity = "1";
        }, 2000); // Đợi 2 giây để bao thư mở ra
      } else {
        alert("Sai mật khẩu! Vui lòng thử lại.");
      }
    }
  </script>

</body>
</html>
