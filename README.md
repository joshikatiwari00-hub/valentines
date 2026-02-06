  }

  .card {
    background:white;
    padding:20px;
    border-radius:20px;
    display:inline-block;
    margin-top:20px;
    box-shadow:0 10px 25px rgba(0,0,0,0.1);
  }

  button {
    padding:10px 20px;
    margin:10px;
    border:none;
    border-radius:20px;
    font-size:16px;
    cursor:pointer;
  }

  .yes { background:#ff6b81; color:white; }
  .no { background:#dcdcdc; }

  .heart {
    position:absolute;
    font-size:20px;
    animation: floatUp 6s linear infinite;
  }

  @keyframes floatUp {
    from { transform: translateY(100vh); opacity:1; }
    to { transform: translateY(-10vh); opacity:0; }
  }
</style>
</head>

<body>

<!-- Background music -->
<iframe width="0" height="0"
src="https://www.youtube.com/embed/c1bLvzZYXjM?autoplay=1&loop=1&playlist=c1bLvzZYXjM"
frameborder="0"
allow="autoplay">
</iframe>

<div class="container" id="start">
  <h2>Anish, this is for you ❤️</h2>
  <img src="photo.jpg" class="photo">
  <br><br>
  <button onclick="showQuestion()">Click here</button>
</div>

<script>
function showQuestion() {
  document.body.innerHTML += `
    <div class="card">
      <h3>Will you stay mine forever? ❤️</h3>
      <button class="yes" onclick="showYes()">Yes</button>
      <button class="no" onclick="moveNo(this)">No</button>
    </div>
  `;
}

function showYes() {
  document.body.innerHTML = `
    <div class="container">
      <img src="photo.jpg" class="photo">
      <div class="card">
        <h2>Yayayyayayayayyayy 💕</h2>
        <p>I love you so much bebuuu ❤️</p>
        <p>You make my life brighter every day.</p>
        <p>Forever yours 💫</p>
      </div>
    </div>
  `;
  createHearts();
}

function moveNo(btn) {
  btn.style.position = "absolute";
  btn.style.top = Math.random()*80 + "%";
  btn.style.left = Math.random()*80 + "%";
}

function createHearts() {
  setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random()*100 + "vw";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
  }, 300);
}
</script>

</body>
</html
