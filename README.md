# Pixelllsglorryyy
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Graphiluxe - 3D Animation</title>
  <link rel="stylesheet" href="style.css">
  <script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>
</head>
<body>
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background: linear-gradient(to right, #ffffff, #800000);
  color: #fff;
  text-align: center;
}

.header {
  padding: 40px 20px;
}

.logo-container img.rotate3d {
  width: 200px;
  animation: spin 8s linear infinite;
  transform-style: preserve-3d;
}

@keyframes spin {
  from { transform: rotateY(0deg); }
  to   { transform: rotateY(360deg); }
}

.lottie-section {
  margin: 40px auto;
}

footer {
  background: #2d2d2d;
  padding: 20px;
  font-size: 14px;
}


  <div class="header">
    <div class="logo-container">
      <img src="https://i.imgur.com/klbN8dd.png" class="rotate3d" alt="Graphiluxe Logo">
    </div>
    <h1>Graphiluxe</h1>
    <p>Premium PNGs, Fonts, and 3D Animations</p>
  </div>

  <div class="lottie-section">
    <lottie-player src="https://assets2.lottiefiles.com/packages/lf20_c9lvse3g.json"
      background="transparent" speed="1" style="width: 300px; height: 300px;" loop autoplay>
    </lottie-player>
  </div>

  <footer>
    Contact: meshiv9359@gmail.com | Instagram: @kunal_raut_149
  </footer>

</body>
</html>
