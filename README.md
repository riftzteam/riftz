<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Riftz Team</title>

<link rel="stylesheet" href="styles.css" />

<style>
  /* Reset e estilos base */
  * {
    box-sizing: border-box;
  }
  body {
    margin: 0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #020617, #0f172a);
    color: white;
    line-height: 1.5;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }

  /* HEADER */
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 40px;
    background: rgba(2, 6, 23, 0.85);
    position: sticky;
    top: 0;
    z-index: 1000;
    gap: 20px;
  }

  .logo {
    font-size: 32px;
    font-weight: 900;
    color: #22c55e;
    letter-spacing: 2px;
  }

  nav a {
    margin-left: 20px;
    text-decoration: none;
    color: white;
    font-weight: 600;
    transition: color 0.3s ease;
  }

  nav a:hover,
  nav a:focus {
    color: #22c55e;
    outline: none;
  }

  button.fortnite-btn {
    margin-left: 20px;
    padding: 8px 18px;
    font-weight: 600;
    font-size: 1rem;
    border-radius: 8px;
    border: none;
    background-color: #5846f8;
    color: white;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  button.fortnite-btn:hover,
  button.fortnite-btn:focus {
    background-color: #4633c5;
    outline: none;
  }

  /* HERO */
  .hero {
    height: 90vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    text-align: center;
    padding: 0 15px;
  }

  .hero h1 {
    font-size: clamp(2.5rem, 8vw, 4rem);
    margin-bottom: 10px;
  }

  .hero span {
    color: #22c55e;
  }

  .hero p {
    font-size: 1.25rem;
    margin-bottom: 30px;
  }

  .btn {
    padding: 14px 30px;
    background: #22c55e;
    border: none;
    border-radius: 8px;
    font-weight: 700;
    font-size: 1.1rem;
    cursor: pointer;
    color: #fff;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .btn:hover,
  .btn:focus {
    transform: scale(1.1);
    box-shadow: 0 0 20px #22c55e;
    outline: none;
  }

  /* PLAYERS */
  .players {
    padding: 50px 20px;
    text-align: center;
    background: rgba(2, 6, 23, 0.7);
  }

  .players h2 {
    font-size: 2.5rem;
    margin-bottom: 30px;
    color: #22c55e;
  }

  .cards {
    display: flex;
    justify-content: center;
    gap: 25px;
    flex-wrap: wrap;
  }

  .card {
    background: #020617;
    padding: 20px 15px;
    border-radius: 12px;
    width: 180px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    box-shadow: 0 0 8px #111827;
  }

  .card:hover,
  .card:focus-within {
    transform: translateY(-8px);
    box-shadow: 0 0 20px #22c55e;
  }

  .card a {
    color: #22c55e;
    font-weight: 600;
    text-decoration: none;
    word-break: break-word;
    display: inline-block;
  }

  .card a:hover,
  .card a:focus {
    color: #adebad;
    outline: none;
    text-decoration: underline;
  }

  /* RESULTS */
  .results {
    padding: 50px 20px;
    text-align: center;
    background: rgba(2, 6, 23, 0.7);
  }

  .results h2 {
    font-size: 2.5rem;
    margin-bottom: 30px;
    color: #22c55e;
  }

  .match {
    background: #020617;
    margin: 12px auto;
    padding: 18px;
    width: 320px;
    border-radius: 12px;
    box-shadow: 0 0 10px #111827;
    font-weight: 600;
    font-size: 1.15rem;
    color: #adebad;
    transition: background 0.3s ease;
  }

  .match:hover {
    background: #162c1a;
  }

  /* FORTNITE SECTION */
  #fortnite {
    display: none;
    padding: 50px 20px;
    background: linear-gradient(135deg, #002f6c, #0059b3);
    color: #fff;
    border-radius: 12px;
    margin: 50px 0;
  }

  #fortnite h2 {
    font-size: 2.5rem;
    margin-bottom: 30px;
    color: #adebad;
    text-align: center;
  }

  /* FORTNITE CARDS */
  #fortnite .cards {
    justify-content: center;
  }

  /* DISCORD */
  .discord {
    padding: 50px 20px;
    text-align: center;
    background: rgba(2, 6, 23, 0.7);
  }

  /* FOOTER */
  footer {
    text-align: center;
    padding: 20px;
    opacity: 0.5;
    font-size: 0.9rem;
    background: #020617;
  }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    header {
      flex-direction: column;
      gap: 10px;
      padding: 15px 20px;
    }

    .cards {
      gap: 15px;
    }

    .card {
      width: 140px;
      padding: 15px 10px;
    }

    .match {
      width: 90%;
      max-width: 320px;
    }
  }
</style>

<script>
  function showFortnite() {
    const fortniteSection = document.getElementById('fortnite');
    if (fortniteSection.style.display === 'flex' || fortniteSection.style.display === 'block') {
      fortniteSection.style.display = 'none';
    } else {
      fortniteSection.style.display = 'block';
      fortniteSection.scrollIntoView({behavior: 'smooth'});
    }
  }
</script>

</head>

<body>

<header>
  <div class="logo">Riftz</div>
  <nav>
    <a href="#">Início</a>
    <a href="#players">Jogadores</a>
    <a href="#results">Resultados</a>
  </nav>
  <button class="fortnite-btn" onclick="showFortnite()" aria-expanded="false" aria-controls="fortnite">Fortnite</button>
</header>

<section class="hero">
  <h1>Riftz <span>Rocket League</span></h1>
  <p>Velocidade. Precisão. Vitória.</p>

  <a href="https://discord.gg/CwmNh6d3gD" target="_blank" rel="noopener noreferrer">
    <button class="btn">Entrar no Discord</button>
  </a>
</section>

<!-- PLAYERS -->
<section id="players" class="players">
  <h2>Jogadores</h2>

  <div class="cards">
    <div class="card"><a href="https://www.tiktok.com/@okaygibbon?_r=1&_t=ZG-95EWn4bZAGW" target="_blank" rel="noopener noreferrer">OkayGibbon965</a></div>
    <div class="card"><a href="https://www.tiktok.com/@algravito?_r=1&_t=ZG-95EWi3v0vw0" target="_blank" rel="noopener noreferrer">TIKTOK_algravito</a></div>
    <div class="card"><a href="https://www.tiktok.com/@._santiago89?_r=1&_t=ZG-95EWR9use8X" target="_blank" rel="noopener noreferrer">santi111012</a></div>
    <div class="card"><a href="https://www.instagram.com/ze_pedro_______?igsh=MTBtdWtwcjV6MzBpaQ==" target="_blank" rel="noopener noreferrer">Zezocas007</a></div>
    <div class="card"><a href="https://www.tiktok.com/@filipemoreirafigu?_r=1&_t=ZG-95EVuiB6vqa" target="_blank" rel="noopener noreferrer">Ricardo_Nikita</a></div>
    <div class="card"><a href="https://www.tiktok.com/@kogetada?_r=1&_t=ZG-95EVdPrNFoG" target="_blank" rel="noopener noreferrer">HummingBirdMain</a></div>
  </div>
</section>

<!-- RESULTS -->
<section id="results" class="results">
  <h2>Resultados</h2>

  <div class="match">Riftz 10 - 5 Team Tuga</div>
  <div class="match">Riftz 5 - 0 Team Fúria</div>
</section>

<!-- FORTNITE -->
<section id="fortnite" role="region" aria-label="Seção Riftz Fortnite">
  <h2>Riftz Fortnite</h2>
  <div class="cards">
    <div class="card"><a href="https://link1.example.com" target="_blank" rel="noopener noreferrer">MembroFortnite1</a></div>
    <div class="card"><a href="https://link2.example.com" target="_blank" rel="noopener noreferrer">MembroFortnite2</a></div>
    <div class="card"><a href="https://link3.example.com" target="_blank" rel="noopener noreferrer">MembroFortnite3</a></div>
    <div class="card"><a href="https://link4.example.com" target="_blank" rel="noopener noreferrer">MembroFortnite4</a></div>
  </div>
</section>

<!-- DISCORD -->
<section id="discord" class="discord">
  <!-- Placeholder for future Discord embed or content -->
</section>

<footer>
  © 2026 Riftz
</footer>

</body>
</html>


