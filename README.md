# od1lovv.music
OD1 MUSIC website

<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>OD1 MUSIC</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      background: #090b12;
      color: white;
      font-family: Arial, sans-serif;
    }
    header {
      padding: 24px 18px;
      background: #121522;
      border-bottom: 1px solid #292d3c;
    }
    header h1 { margin: 0; color: #45e6b0; }
    header p { color: #aab0c3; margin-bottom: 0; }
    main { padding: 20px; max-width: 650px; margin: auto; }
    input {
      width: 100%;
      padding: 14px;
      border-radius: 12px;
      border: 1px solid #34394a;
      background: #171b29;
      color: white;
      font-size: 16px;
    }
    .song {
      display: flex;
      align-items: center;
      gap: 14px;
      background: #171b29;
      margin-top: 14px;
      padding: 15px;
      border-radius: 14px;
    }
    .cover {
      width: 55px;
      height: 55px;
      display: grid;
      place-items: center;
      background: #263d40;
      border-radius: 12px;
      font-size: 25px;
    }
    .song h3 { margin: 0 0 6px; }
    .song p { margin: 0; color: #aab0c3; }
    button {
      margin-left: auto;
      border: 0;
      border-radius: 50%;
      width: 43px;
      height: 43px;
      background: #45e6b0;
      font-size: 19px;
    }
    #player { width: 100%; margin-top: 22px; }
    footer { text-align: center; padding: 25px; color: #aab0c3; }
  </style>
</head>
<body>
  <header>
    <h1>🎵 OD1 MUSIC</h1>
    <p>Musiqani his qil. O'z ritmingni top.</p>
  </header>

  <main>
    <h2>Musiqalar</h2>
    <input id="search" placeholder="Musiqa nomini qidiring...">

    <div id="songs">
      <div class="song" data-name="demo music">
        <div class="cover">🎧</div>
        <div>
          <h3>Demo Music</h3>
          <p>Sinov uchun audio</p>
        </div>
        <button onclick="playDemo()" aria-label="Sinov musiqasini ijro etish">▶</button>
      </div>
    </div>

    <audio id="player" controls></audio>
    <p id="message">Musiqa tinglash uchun ▶ tugmasini bosing.</p>
  </main>

  <footer>© 2026 OD1 MUSIC</footer>

  <script>
    const search = document.getElementById('search');

    search.addEventListener('input', function () {
      document.querySelectorAll('.song').forEach(song => {
        song.style.display =
          song.dataset.name.includes(this.value.toLowerCase())
          ? 'flex' : 'none';
      });
    });

    function playDemo() {
      document.getElementById('message').textContent =
        "Haqiqiy musiqa ijro etish uchun audio fayl qo‘shish kerak.";
      document.getElementById('player').scrollIntoView({
        behavior: 'smooth', block: 'center'
      });
    }
  </script>
</body>
</html>

