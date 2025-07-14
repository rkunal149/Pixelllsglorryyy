<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Graphiluxe - Auth Dashboard</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #121212;
      color: white;
      padding: 20px;
    }input, button {
  padding: 10px;
  margin: 5px 0;
  width: 100%;
  max-width: 300px;
}

button {
  background-color: maroon;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 5px;
}

.navbar {
  display: flex;
  justify-content: space-between;
  background: #1e1e1e;
  padding: 10px 20px;
}

.navbar h2 {
  margin: 0;
}

.navbar button {
  background: none;
  border: 1px solid white;
}

  </style>  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";
    import { getAuth, onAuthStateChanged, createUserWithEmailAndPassword, signInWithEmailAndPassword, signOut, sendPasswordResetEmail } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-auth.js";

    const firebaseConfig = {
      apiKey: "AIzaSyCYl48BKBznp56rwGXRfYPK52Q3lZUbdw8",
      authDomain: "glxhub-main.firebaseapp.com",
      projectId: "glxhub-main",
      storageBucket: "glxhub-main.firebasestorage.app",
      messagingSenderId: "415822108868",
      appId: "1:415822108868:web:8a20b0c03f6028a0111191"
    };

    const app = initializeApp(firebaseConfig);
    const auth = getAuth(app);

    window.signup = () => {
      const email = emailInput.value;
      const password = passwordInput.value;
      createUserWithEmailAndPassword(auth, email, password)
        .then(() => alert("Signup Success!"))
        .catch(e => alert(e.message));
    }

    window.login = () => {
      const email = emailInput.value;
      const password = passwordInput.value;
      signInWithEmailAndPassword(auth, email, password)
        .then(() => location.href = "dashboard")
        .catch(e => alert(e.message));
    }

    window.logout = () => {
      signOut(auth).then(() => location.href = "index")
    }

    window.resetPassword = () => {
      const email = document.getElementById("resetEmail").value;
      sendPasswordResetEmail(auth, email)
        .then(() => alert("Reset email sent!"))
        .catch(e => alert(e.message));
    }

    window.onload = () => {
      const path = window.location.pathname;
      if (path.includes("dashboard")) {
        onAuthStateChanged(auth, user => {
          if (!user) location.href = "index";
          else {
            document.getElementById("userInfo").innerText = "Welcome " + user.email;
            document.getElementById("uid").innerText = user.uid;
          }
        });
      }
    }
  </script></head>
<body>
  <div class="navbar">
    <h2>Graphiluxe</h2>
    <div>
      <a href="dashboard">Dashboard</a> |
      <a href="profile">Profile</a> |
      <a href="reset">Reset Password</a> |
      <button onclick="logout()">Logout</button>
    </div>
  </div>  <div id="main">
    <h2>Login / Signup</h2>
    <input id="emailInput" type="email" placeholder="Email">
    <input id="passwordInput" type="password" placeholder="Password">
    <button onclick="login()">Login</button>
    <button onclick="signup()">Signup</button>
  </div>  <div id="dashboard" style="display:none">
    <h3 id="userInfo">Loading...</h3>
    <p><strong>UID:</strong> <span id="uid"></span></p>
  </div>  <div id="reset" style="display:none">
    <h2>Reset Password</h2>
    <input id="resetEmail" type="email" placeholder="Enter your email">
    <button onclick="resetPassword()">Send Reset Email</button>
  </div>
</body>
</html>
