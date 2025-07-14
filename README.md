<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Graphiluxe - Premium Design Resources</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to right, #ffffff, #800000);
      color: #333;
    }

    header {
      text-align: center;
      padding: 40px 20px 20px;
      background-color: #2d2d2d;
      color: white;
    }

    header h1 {
      font-size: 40px;
      margin-bottom: 10px;
    }

    header p {
      font-size: 16px;
      color: #ccc;
    }

    .controls {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 10px;
      padding: 20px;
      background-color: #fff0f0;
    }

    .controls input, .controls select {
      padding: 10px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 25px;
      padding: 30px;
    }

    .item {
      background: #fff;
      border-radius: 10px;
      width: 260px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
      transition: transform 0.3s ease;
    }

    .item:hover {
      transform: scale(1.05);
    }

    .item img {
      width: 100%;
      height: 180px;
      border-top-left-radius: 10px;
      border-top-right-radius: 10px;
      object-fit: cover;
    }

    .desc {
      padding: 15px;
      font-weight: bold;
      font-size: 16px;
      text-align: center;
    }

    .download-btn {
      display: block;
      margin: 0 auto 15px auto;
      padding: 8px 20px;
      background-color: #800000;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 15px;
    }

    .download-btn:hover {
      background-color: #a00000;
    }

    footer {
      background-color: #2d2d2d;
      color: white;
      text-align: center;
      padding: 20px;
      font-size: 14px;
    }
  </style>
</head>
<body>

<header>
  <h1>Graphiluxe</h1>
  <p>Premium PNGs • Fonts • Vectors • Wallpapers</p>
</header>

<div class="controls">
  <input type="text" id="searchInput" placeholder="Search...">
  <select id="categoryFilter">
    <option value="all">All Categories</option>
    <option value="png">PNGs</option>
    <option value="vector">Vectors</option>
    <option value="font">Fonts</option>
    <option value="wallpaper">Wallpapers</option>
  </select>
</div>

<div class="gallery" id="gallery">
  <div class="item png">
    <img src="https://i.imgur.com/klbN8dd.png" alt="Stylish PNG">
    <div class="desc">Stylish PNG #1</div>
    <button class="download-btn" onclick="increment(this)">Download (<span>0</span>)</button>
  </div>
  <div class="item vector">
    <img src="https://i.imgur.com/GI0iTIf.jpg" alt="Vector Art">
    <div class="desc">Vector Art #1</div>
    <button class="download-btn" onclick="increment(this)">Download (<span>0</span>)</button>
  </div>
  <div class="item font">
    <img src="https://i.imgur.com/l6GS8Ff.jpg" alt="Font Preview">
    <div class="desc">Font Pack</div>
    <button class="download-btn" onclick="increment(this)">Download (<span>0</span>)</button>
  </div>
  <div class="item wallpaper">
    <img src="https://i.imgur.com/N4Q9K4N.jpg" alt="Wallpaper">
    <div class="desc">4K Wallpaper</div>
    <button class="download-btn" onclick="increment(this)">Download (<span>0</span>)</button>
  </div>
</div>

<footer>
  Contact: meshiv9359@gmail.com | Instagram: @kunal_raut_149
</footer>

<script>
  function increment(btn) {
    const span = btn.querySelector("span");
    span.textContent = parseInt(span.textContent) + 1;
  }

  document.getElementById("searchInput").addEventListener("input", function () {
    const value = this.value.toLowerCase();
    document.querySelectorAll(".item").forEach(item => {
      item.style.display = item.innerText.toLowerCase().includes(value) ? "" : "none";
    });
  });

  document.getElementById("categoryFilter").addEventListener("change", function () {
    const category = this.value;
    document.querySelectorAll(".item").forEach(item => {
      item.style.display = (category === "all" || item.classList.contains(category)) ? "" : "none";
    });
  });
</script>

</body>
</html>
