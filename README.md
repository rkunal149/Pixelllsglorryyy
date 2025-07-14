<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Graphiluxe - Explore Free Design Resources</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #121212;
      color: white;
    }
    header, footer {
      background-color: #1f1f1f;
      padding: 20px;
      text-align: center;
    }
    h1 {
      margin: 0;
    }
    nav {
      display: flex;
      justify-content: center;
      gap: 20px;
      padding: 10px;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }
    .tags, .search {
      text-align: center;
      margin: 20px 0;
    }
    .tags button, .search input {
      padding: 10px;
      margin: 5px;
      background-color: maroon;
      color: white;
      border: none;
      border-radius: 5px;
    }
    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      padding: 20px;
    }
    .item {
      background: #222;
      padding: 10px;
      border-radius: 10px;
      transition: transform 0.2s;
    }
    .item:hover {
      transform: scale(1.05);
    }
    .item img {
      width: 100%;
      height: 150px;
      object-fit: cover;
      border-radius: 8px;
    }
    .desc {
      margin-top: 10px;
    }
    .download-btn {
      display: inline-block;
      margin-top: 8px;
      background-color: #800000;
      padding: 6px 12px;
      border-radius: 5px;
      color: white;
      text-decoration: none;
    }
    .contact {
      font-size: 14px;
      color: #ccc;
      margin-top: 10px;
    }
    .admin-panel {
      display: none;
      background-color: #1e1e1e;
      padding: 20px;
      margin: 20px;
      border-radius: 10px;
    }
    .admin-panel input, .admin-panel button {
      display: block;
      width: 100%;
      margin: 10px 0;
      padding: 10px;
    }
  </style>
  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";
    import { getAuth, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-auth.js";const firebaseConfig = {
  apiKey: "AIzaSyCYl48BKBznp56rwGXRfYPK52Q3lZUbdw8",
  authDomain: "glxhub-main.firebaseapp.com",
  projectId: "glxhub-main",
  storageBucket: "glxhub-main.firebasestorage.app",
  messagingSenderId: "415822108868",
  appId: "1:415822108868:web:8a20b0c03f6028a0111191"
};

const app = initializeApp(firebaseConfig);
const auth = getAuth(app);

onAuthStateChanged(auth, (user) => {
  if (user && user.email === "meshiv9359@gmail.com") {
    document.querySelector('.admin-panel').style.display = 'block';
  }
});

  </script>
</head>
<body>
  <header>
    <h1>Graphiluxe</h1>
    <p>Download Free Vectors, Stock Photos, Stock Videos, and More</p>
  </header>  <nav>
    <a href="#">Home</a>
    <a href="#">Popular</a>
    <a href="#">Trending</a>
    <a href="#">Login</a>
  </nav>  <div class="tags">
    <strong>Popular:</strong>
    <button onclick="alert('Background tag clicked')">Background</button>
    <button onclick="alert('Summer tag clicked')">Summer</button>
    <button onclick="alert('Happy Birthday tag clicked')">Happy Birthday</button>
  </div>  <div class="search">
    <input type="text" placeholder="Search by tag or name...">
    <button>Search</button>
  </div>  <div class="gallery">
    <div class="item">
      <img src="https://i.postimg.cc/nV5vQcLg/1000058918.jpg" alt="Natural View">
      <div class="desc">Natural View<br>Downloads: 120</div>
      <a class="download-btn" href="#">Download</a>
    </div>
  </div>  <div class="admin-panel">
    <h2>Upload New Image</h2>
    <input type="text" placeholder="Title">
    <input type="text" placeholder="Tag">
    <input type="text" placeholder="Image URL">
    <button>Upload</button>
  </div>  <footer>
    <div class="contact">
      📧 Email: meshiv9359@gmail.com<br>
      📸 Instagram: @kunal_raut_149<br>
      📍 Maharashtra, India
    </div>
  </footer>
</body>
</html>
