<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Riftz Team</title>
<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          primary: '#22c55e',
          secondary: '#5846f8',
          dark: '#020617',
          darkSecondary: '#0f172a',
          light: '#adebad'
        }
      }
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
  
  body {
    font-family: 'Inter', sans-serif;
    background: linear-gradient(135deg, #020617, #0f172a);
    color: white;
    line-height: 1.5;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }

  .hero-bg {
    background: linear-gradient(rgba(2, 6, 23, 0.9), rgba(2, 6, 23, 0.9)), 
                url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%23020617"/><path d="M0 0L100 100M100 0L0 100" stroke="%230f172a" stroke-width="1"/></svg>');
    background-size: cover;
    background-position: center;
  }

  .card-hover {
    transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }

  .card-hover:hover {
    transform: translateY(-8px);
    box-shadow: 0 10px 25px rgba(34, 197, 94, 0.3);
  }

  .btn-hover {
    transition: all 0.3s ease;
  }

  .btn-hover:hover {
    transform: scale(1.05);
    box-shadow: 0 0 20px rgba(34, 197, 94, 0.5);
  }

  .fade-in {
    animation: fadeIn 0.5s ease-in forwards;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .gradient-text {
    background: linear-gradient(to right, #22c55e, #adebad);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .hero {
    animation: heroFloat 6s ease-in-out infinite;
  }

  @keyframes heroFloat {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
  }

  .nav-link {
    position: relative;
  }

  .nav-link::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 0;
    height: 2px;
    background: #22c55e;
    transition: width 0.3s ease;
  }

  .nav-link:hover::after,
  .nav-link:focus-visible::after {
    width: 100%;
  }
</style>

<script>
  function showFortnite(event) {
    const fortniteSection = document.getElementById('fortnite');
    const btn = event.currentTarget;
    
    const isHidden = fortniteSection.classList.contains('hidden');
    if (isHidden) {
      fortniteSection.classList.remove('hidden');
      btn.setAttribute('aria-expanded', 'true');
      setTimeout(() => fortniteSection.scrollIntoView({ behavior: 'smooth' }), 10);
    } else {
      fortniteSection.classList.add('hidden');
      btn.setAttribute('aria-expanded', 'false');
    }
  }

  document.addEventListener('DOMContentLoaded', function() {
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          window.scrollTo({
            top: target.offsetTop - 80,
            behavior: 'smooth'
          });
        }
      });
    });

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('fade-in');
        }
      });
    }, { threshold: 0.1 });

    document.querySelectorAll('.animated').forEach(el => observer.observe(el));
  });
</script>

</head>

<body class="min-h-screen flex flex-col">

<header class="flex flex-col md:flex-row justify-between items-center px-4 md:px-8 py-4 md:py-6 bg-black bg-opacity-80 sticky top-0 z-50 gap-4" role="banner">
  <h1 class="text-3xl md:text-4xl font-bold bg-gradient-to-r from-primary to-light bg-clip-text text-transparent">
    Riftz
  </h1>
  
  <nav aria-label="Main Navigation" class="flex flex-wrap justify-center gap-4 md:gap-6">
    <button class="nav-link text-white hover:text-primary focus:outline-none focus:ring-2 focus:ring-green-500 rounded" type="button" onclick="document.querySelector('#players').scrollIntoView({behavior: 'smooth'})">
      Jogadores
    </button>
    <button class="nav-link text-white hover:text-primary focus:outline-none focus:ring-2 focus:ring-green-500 rounded" type="button" onclick="document.querySelector('#results').scrollIntoView({behavior: 'smooth'})">
      Resultados
    </button>
  </nav>
  
  <button class="fortnite-btn bg-secondary hover:bg-purple-700 text-white font-semibold py-2 px-4 rounded-lg transition duration-300 focus:outline-none focus:ring-2 focus:ring-purple-500 focus:ring-opacity-50"
          onclick="showFortnite(event)"
          aria-expanded="false" 
          aria-controls="fortnite" 
          aria-label="Mostrar a seção Fortnite">
    Fortnite
  </button>
</header>

<section class="hero hero-bg flex flex-col items-center justify-center text-center py-16 md:py-24 px-4 min-h-[80vh] animated" role="main">
  <h2 class="text-4xl md:text-6xl font-bold mb-4 hero">
    Riftz <span class="gradient-text">Rocket League</span>
  </h2>
  <p class="text-xl md:text-2xl mb-8 max-w-2xl">
    Velocidade. Precisão. Vitória.
  </p>
  
  <a href="https://discord.gg/CwmNh6d3gD" target="_blank" rel="noopener noreferrer" class="btn-hover bg-primary hover:bg-green-600 text-white font-bold py-3 px-8 rounded-lg text-lg transition duration-300 focus:outline-none focus:ring-2 focus:ring-green-500 focus:ring-opacity-50" aria-label="Entrar no Discord">
    Entrar no Discord
  </a>
</section>

<!-- PLAYERS -->
<section id="players" class="py-16 px-4 bg-darkSecondary bg-opacity-70 animated" tabindex="-1">
  <h2 class="text-3xl md:text-4xl font-bold text-center mb-12 gradient-text">
    Jogadores
  </h2>

  <div class="flex flex-wrap justify-center gap-6 max-w-6xl mx-auto">
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://www.tiktok.com/@okaygibbon?_r=1&_t=ZG-95EWn4bZAGW" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Perfil OkayGibbon965 no TikTok">
        OkayGibbon965
      </a>
    </div>
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://www.tiktok.com/@algravito?_r=1&_t=ZG-95EWi3v0vw0" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Perfil TIKTOK_algravito no TikTok">
        TIKTOK_algravito
      </a>
    </div>
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://www.tiktok.com/@._santiago89?_r=1&_t=ZG-95EWR9use8X" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Perfil santi111012 no TikTok">
        santi111012
      </a>
    </div>
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://www.instagram.com/ze_pedro_______?igsh=MTBtdWtwcjV6MzBpaQ==" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Perfil Zezocas007 no Instagram">
        Zezocas007
      </a>
    </div>
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://www.tiktok.com/@filipemoreirafigu?_r=1&_t=ZG-95EVuiB6vqa" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Perfil Ricardo_Nikita no TikTok">
        Ricardo_Nikita
      </a>
    </div>
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://www.tiktok.com/@kogetada?_r=1&_t=ZG-95EVdPrNFoG" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Perfil HummingBirdMain no TikTok">
        HummingBirdMain
      </a>
    </div>
  </div>
</section>

<!-- RESULTS -->
<section id="results" class="py-16 px-4 bg-darkSecondary bg-opacity-70 animated" tabindex="-1">
  <h2 class="text-3xl md:text-4xl font-bold text-center mb-12 gradient-text">
    Resultados
  </h2>

  <div class="max-w-2xl mx-auto space-y-4">
    <div class="bg-dark p-6 rounded-xl shadow-lg text-light text-xl font-semibold text-center hover:bg-green-900 hover:bg-opacity-30 transition duration-300" role="region" aria-label="Resultado da partida Riftz 10 por 5 contra Team Tuga">
      Riftz 10 - 5 Team Tuga
    </div>
    <div class="bg-dark p-6 rounded-xl shadow-lg text-light text-xl font-semibold text-center hover:bg-green-900 hover:bg-opacity-30 transition duration-300" role="region" aria-label="Resultado da partida Riftz 5 por 0 contra Team Fúria">
      Riftz 5 - 0 Team Fúria
    </div>
  </div>
</section>

<!-- FORTNITE -->
<section id="fortnite" class="hidden py-16 px-4 bg-gradient-to-br from-blue-900 to-blue-700 rounded-xl mx-4 md:mx-8 my-12 animated" tabindex="-1" aria-live="polite" aria-label="Seção Fortnite da equipe Riftz">
  <h2 class="text-3xl md:text-4xl font-bold text-center mb-12 gradient-text">
    Riftz Fortnite
  </h2>
  
  <div class="flex flex-wrap justify-center gap-6 max-w-6xl mx-auto">
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://link1.example.com" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Membro Fortnite 1">
        MembroFortnite1
      </a>
    </div>
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://link2.example.com" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Membro Fortnite 2">
        MembroFortnite2
      </a>
    </div>
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://link3.example.com" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Membro Fortnite 3">
        MembroFortnite3
      </a>
    </div>
    <div class="card-hover bg-dark p-6 rounded-xl w-40 md:w-48 shadow-lg hover:shadow-primary">
      <a href="https://link4.example.com" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-light font-medium block" aria-label="Membro Fortnite 4">
        MembroFortnite4
      </a>
    </div>
  </div>
</section>

<!-- DISCORD -->
<section id="discord" class="py-16 px-4 bg-darkSecondary bg-opacity-70 animated" tabindex="-1">
  <div class="max-w-4xl mx-auto text-center">
    <h2 class="text-3xl md:text-4xl font-bold mb-6 gradient-text">
      Discord
    </h2>
    <p class="text-xl mb-8">
      Junte-se à nossa comunidade e fique por dentro das últimas novidades!
    </p>
    <a href="https://discord.gg/CwmNh6d3gD" target="_blank" rel="noopener noreferrer" class="btn-hover bg-primary hover:bg-green-600 text-white font-bold py-3 px-8 rounded-lg text-lg transition duration-300 focus:outline-none focus:ring-2 focus:ring-green-500 focus:ring-opacity-50" aria-label="Entrar no Discord">
      Entrar no Discord
    </a>
  </div>
</section>

<footer class="text-center py-6 text-gray-400 text-sm bg-dark">
  © 2026 Riftz
</footer>

</body>
</html>

