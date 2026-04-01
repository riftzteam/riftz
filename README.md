<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Riftz Team</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #020617, #0f172a);
    color: white;
}

/* HEADER */
header {
    display: flex;
    justify-content: space-between;
    padding: 20px 40px;
}

.logo {
    font-size: 30px;
    font-weight: bold;
    color: #22c55e;
}

nav a {
    margin-left: 20px;
    text-decoration: none;
    color: white;
    transition: 0.3s;
}

nav a:hover {
    color: #22c55e;
}

/* HERO */
.hero {
    height: 90vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    text-align: center;
}

.hero h1 {
    font-size: 60px;
}

.hero span {
    color: #22c55e;
}

.btn {
    padding: 12px 25px;
    background: #22c55e;
    border: none;
    border-radius: 8px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.3s;
}

.btn:hover {
    transform: scale(1.1);
    box-shadow: 0 0 20px #22c55e;
}

/* PLAYERS */
.players {
    padding: 50px;
    text-align: center;
}

.cards {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
}

.card {
    background: #020617;
    padding: 20px;
    border-radius: 10px;
    width: 200px;
    transition: 0.3s;
}

.card:hover {
    transform: translateY(-10px);
    box-shadow: 0 0 15px #22c55e;
}

/* RESULTS */
.results {
    padding: 50px;
    text-align: center;
}

.match {
    background: #020617;
    margin: 10px auto;
    padding: 15px;
    width: 300px;
    border-radius: 10px;
}

/* DISCORD */
.discord {
    padding: 50px;
    text-align: center;
}

/* FOOTER */
footer {
    text-align: center;
    padding: 20px;
    opacity: 0.5;
}
</style>

</head>

<body>

<header>
    <div class="logo">Riftz</div>
    <nav>
        <a href="#">Início</a>
        <a href="#players">Jogadores</a>
        <a href="#results">Resultados</a>
        <a href="#discord">Discord</a>
    </nav>
</header>

<section class="hero">
    <h1>Riftz <span>Rocket League</span></h1>
    <p>Velocidade. Precisão. Vitória.</p>

    <a href="https://discord.gg/CwmNh6d3gD" target="_blank">
        <button class="btn">Entrar no Discord</button>
    </a>
</section>

<!-- PLAYERS -->
<section id="players" class="players">
    <h2>Jogadores</h2>

    <div class="cards">
        <div class="card">OkayGibbon<br></div>
        <div class="card">TIKTOK_algravito<br></div>
        <div class="card">santi111012<br></div>
        <div class="card">Zezocas007<br></div>
        <div class="card">Ricardo_Nikita<br></div>
    </div>
</section>

<!-- RESULTS -->
<section id="results" class="results">
    <h2>Resultados</h2>

    <div class="match">Riftz 6 - 1 Team Tuga </div>
    <div class="match">Riftz 2 - 2 Team Y</div>
</section>

<!-- DISCORD -->
<section id="discord" class="discord">

</section>

<footer>
    © 2026 Riftz 
</footer>

</body>
</html>
