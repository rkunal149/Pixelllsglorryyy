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

.center-btn {
  text-align: center;
  margin: 40px 0;
}

.glow-btn {
  position: relative;
  padding: 15px 35px;
  font-size: 18px;
  font-weight: 600;
  color: white;
  background: linear-gradient(45deg, #800000, #ff4b2b);
  border: none;
  border-radius: 50px;
  text-decoration: none;
  transition: all 0.3s ease-in-out;
  box-shadow: 0 6px 15px rgba(0,0,0,0.2);
  overflow: hidden;
  cursor: pointer;
}

.glow-btn:hover {
  transform: scale(1.07);
  box-shadow: 0 10px 25px rgba(0,0,0,0.3);
  background: linear-gradient(45deg, #ff4b2b, #800000);
}

.stars {
  display: none;
  position: absolute;
  top: -5px;
  right: -10px;
  font-size: 24px;
  pointer-events: none;
  transition: opacity 0.3s ease-in-out;
}

.glow-btn:hover .stars {
  display: block;
  filter: drop-shadow(0 0 10px #fffdef);
}
      .center-btn {
  text-align: center;
  margin: 40px 0;
}

.animated-btn {
  padding: 15px 30px;
  font-size: 18px;
  font-weight: 600;
  color: white;
  background: linear-gradient(45deg, #800000, #ff4b2b);
  border: none;
  border-radius: 50px;
  text-decoration: none;
  transition: all 0.3s ease-in-out;
  box-shadow: 0 6px 15px rgba(0,0,0,0.2);
  display: inline-block;
}

.animated-btn:hover {
  transform: scale(1.1);
  box-shadow: 0 10px 25px rgba(0,0,0,0.3);
  background: linear-gradient(45deg, #ff4b2b, #800000);
}
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
      cursor: pointer;
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
    .auth-modal {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: #1e1e1e;
      padding: 30px;
      border-radius: 10px;
      z-index: 999;
    }
    .auth-modal input, .auth-modal button {
      display: block;
      width: 100%;
      margin: 10px 0;
      padding: 10px;
    }
  </style>
  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";
    import { getAuth, onAuthStateChanged, signInWithEmailAndPassword, createUserWithEmailAndPassword, signOut } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-auth.js";const firebaseConfig = {
  apiKey: "AIzaSyCYl48BKBznp56rwGXRfYPK52Q3lZUbdw8",
  authDomain: "glxhub-main.firebaseapp.com",
  projectId: "glxhub-main",
  storageBucket: "glxhub-main.firebasestorage.app",
  messagingSenderId: "415822108868",
  appId: "1:415822108868:web:8a20b0c03f6028a0111191"
};

const app = initializeApp(firebaseConfig);
const auth = getAuth(app);

const loginLink = document.getElementById('loginLink');
const modal = document.getElementById('authModal');
const loginBtn = document.getElementById('loginBtn');
const signupBtn = document.getElementById('signupBtn');
const logoutBtn = document.getElementById('logoutBtn');

loginLink.onclick = () => modal.style.display = 'block';

loginBtn.onclick = () => {
  const email = document.getElementById('email').value;
  const password = document.getElementById('password').value;
  signInWithEmailAndPassword(auth, email, password)
    .then(() => modal.style.display = 'none')
    .catch(err => alert(err.message));
};

signupBtn.onclick = () => {
  const email = document.getElementById('email').value;
  const password = document.getElementById('password').value;
  createUserWithEmailAndPassword(auth, email, password)
    .then(() => modal.style.display = 'none')
    .catch(err => alert(err.message));
};

logoutBtn.onclick = () => signOut(auth);

onAuthStateChanged(auth, (user) => {
  if (user) {
    loginLink.style.display = 'none';
    logoutBtn.style.display = 'inline-block';
    if (user.email === "meshiv9359@gmail.com") {
      document.querySelector('.admin-panel').style.display = 'block';
    }
  } else {
    loginLink.style.display = 'inline-block';
    logoutBtn.style.display = 'none';
    document.querySelector('.admin-panel').style.display = 'none';
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
    <a id="loginLink">Login</a>
    <button id="logoutBtn" style="display:none;">Logout</button>
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
  </div>  <div class="auth-modal" id="authModal">
    <h2>Login / Signup</h2>
    <input type="email" id="email" placeholder="Email">
    <input type="password" id="password" placeholder="Password">
    <button id="loginBtn">Login</button>
    <button id="signupBtn">Signup</button>
  </div>  <footer>
    <div class="contact">
      📧 Email: meshiv9359@gmail.com<br>
      📸 Instagram: @kunal_raut_149<br>
      📍 Maharashtra, India
    </div>
  </footer>
</body>
</html>
