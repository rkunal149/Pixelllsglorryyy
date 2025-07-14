<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Graphiluxe - Nature Gallery</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: #000;
      color: #fff;
    }

    .header {
      padding: 40px 20px 20px;
      text-align: center;
    }

    .header input, .header select {
      padding: 10px;
      margin: 10px;
      font-size: 16px;
      border-radius: 5px;
    }

    .gallery {
      display: flex;
      justify-content: center;
      padding: 30px;
      gap: 20px;
      flex-wrap: wrap;
    }

    .gallery-item {
      width: 260px;
      background: #1a1a1a;
      border-radius: 10px;
      padding: 15px;
      text-align: center;
      transition: transform 0.3s;
    }

    .gallery-item:hover {
      transform: scale(1.05);
    }

    .gallery-item img {
      width: 100%;
      border-radius: 8px;
    }

    .download-btn {
      margin-top: 10px;
      padding: 8px 15px;
      background-color: #800000;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    .download-btn:hover {
      background-color: #a00000;
    }

    footer {
      background: #2d2d2d;
      padding: 20px;
      text-align: center;
      font-size: 14px;
    }
  </style>
</head>
<body>

  <div class="header">
    <h1>Graphiluxe</h1>
    <input type="text" id="searchInput" placeholder="Search images...">
    <select id="categoryFilter">
      <option value="all">All</option>
      <option value="nature">Nature</option>
    </select>
  </div>

  <div class="gallery" id="gallery">
    <div class="gallery-item nature">
      <img src="https://i.postimg.cc/nV5vQcLg/1000058918.jpg" alt="Natural View">
      <p>Natural View</p>
      <button class="download-btn" onclick="incrementCount(this)">Download (<span>0</span>)</button>
    </div>
  </div>

  <footer>
    Contact: meshiv9359@gmail.com | Instagram: @kunal_raut_149
  </footer>

  <script>
    function incrementCount(btn) {
      const span = btn.querySelector("span");
      span.textContent = parseInt(span.textContent) + 1;
    }

    document.getElementById("searchInput").addEventListener("input", function () {
      const keyword = this.value.toLowerCase();
      document.querySelectorAll(".gallery-item").forEach(function (item) {
        const text = item.innerText.toLowerCase();
        item.style.display = text.includes(keyword) ? "" : "none";
      });
    });

    document.getElementById("categoryFilter").addEventListener("change", function () {
      const value = this.value;
      document.querySelectorAll(".gallery-item").forEach(function (item) {
        if (value === "all" || item.classList.contains(value)) {
          item.style.display = "";
        } else {
          item.style.display = "none";
        }
      });
    });
  </script>
</body>
</html>
