<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Graphiluxe - Premium Design Resources</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to right, #ffffff, #800000);
      color: #333;
    }header {
  text-align: center;
  padding: 40px 20px 10px;
  background-color: #2d2d2d;
  color: white;
}

header h1 {
  font-size: 36px;
  margin: 0;
}

header p {
  font-size: 14px;
  color: #ccc;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  background: #fff0f0;
}

.logo {
  font-weight: bold;
  font-size: 20px;
}

.nav-links {
  display: flex;
  gap: 15px;
}

.nav-links a {
  text-decoration: none;
  color: #800000;
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
  gap: 20px;
  padding: 20px;
}

.item {
  background: #fff;
  border-radius: 10px;
  width: 200px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease;
}

.item:hover {
  transform: scale(1.03);
}

.item img {
  width: 100%;
  height: 150px;
  object-fit: cover;
}

.desc {
  padding: 10px;
  font-size: 14px;
  font-weight: bold;
  text-align: center;
}

.download-btn {
  display: block;
  margin: 0 auto 15px;
  padding: 6px 14px;
  background-color: #800000;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
}

.section-heading {
  text-align: center;
  padding: 30px 10px 10px;
  font-size: 22px;
  font-weight: bold;
}

.popular-tags {
  text-align: center;
  margin-bottom: 20px;
}

.popular-tags button {
  background: #ffcccc;
  border: none;
  margin: 5px;
  padding: 8px 16px;
  border-radius: 5px;
  cursor: pointer;
}

footer {
  background-color: #2d2d2d;
  color: white;
  text-align: center;
  padding: 20px;
  font-size: 14px;
}

.auth-section {
  max-width: 400px;
  margin: 30px auto;
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.auth-section input {
  width: 100%;
  padding: 10px;
  margin-bottom: 15px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.auth-section button {
  background-color: #800000;
  color: white;
  border: none;
  padding: 10px;
  border-radius: 5px;
  width: 100%;
  cursor: pointer;
}

  </style>
</head>
<body><nav>
  <div class="logo">Pixelllsglorryyy</div>
  <div class="nav-links">
    <a href="#login">Login</a>
    <a href="#signup">Sign Up</a>
    <a href="#dashboard">Dashboard</a>
  </div>
</nav><header>
  <h1>Graphiluxe</h1>
  <p>Premium PNGs • Fonts • Vectors • Wallpapers</p>
</header><div class="section-heading">Download Free Vectors, Stock Photos, Stock Videos, and More</div>
<div class="popular-tags">
  <button onclick="window.location.href='popular.html?tag=background'">Background</button>
  <button onclick="window.location.href='popular.html?tag=summer'">Summer</button>
  <button onclick="window.location.href='popular.html?tag=happy-birthday'">Happy Birthday</button>
</div><div class="controls">
  <input type="text" id="searchInput" placeholder="Search...">
  <select id="categoryFilter">
    <option value="all">All Categories</option>
    <option value="png">PNGs</option>
    <option value="vector">Vectors</option>
    <option value="font">Fonts</option>
    <option value="wallpaper">Wallpapers</option>
  </select>
</div><div class="gallery" id="gallery">
  <div class="item png">
    <img src="https://i.postimg.cc/nV5vQcLg/1000058918.jpg" alt="Stylish PNG">
    <div class="desc">Stylish PNG #1</div>
    <button class="download-btn" onclick="increment(this)">Download (<span>0</span>)</button>
  </div>
</div><div id="login" class="auth-section">
  <h3>Login</h3>
  <input type="text" placeholder="Email">
  <input type="password" placeholder="Password">
  <button>Login</button>
</div><div id="signup" class="auth-section">
  <h3>Sign Up</h3>
  <input type="text" placeholder="Full Name">
  <input type="email" placeholder="Email">
  <input type="password" placeholder="Password">
  <button>Register</button>
</div><div id="dashboard" class="auth-section">
  <h3>User Dashboard</h3>
  <p>Welcome to your dashboard. Here you can manage your downloads, favorites, and profile.</p>
</div><footer>
  Contact: meshiv9359@gmail.com | Instagram: @kunal_raut_149
</footer><script>
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
</script></body>
</html>
