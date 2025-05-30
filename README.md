<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>DieguinhoNaVoz</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&family=Orbitron:wght@600&display=swap" rel="stylesheet" />
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
<style>
  /* Reset básico */
  * {
    box-sizing: border-box;
    margin: 0; padding: 0;
  }
  body, html {
    height: 100%;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(135deg, #c4e8d4, #b29feb);
    color: #1f2937;
    display: flex;
  }
  /* Sidebar */
  nav.sidebar {
    width: 260px;
    background: #5b21b6;
    color: #e0e7ff;
    display: flex;
    flex-direction: column;
    padding: 30px 20px;
    box-shadow: 3px 0 10px rgba(0,0,0,0.15);
    position: fixed;
    height: 100%;
  }
  nav.sidebar h1 {
    font-family: 'Orbitron', monospace;
    font-weight: 600;
    font-size: 2.4rem;
    letter-spacing: 0.1em;
    margin-bottom: 40px;
    text-transform: uppercase;
  }
  nav.sidebar a {
    color: #d1d5db;
    text-decoration: none;
    font-weight: 600;
    margin-bottom: 24px;
    font-size: 1.1rem;
    transition: color 0.3s;
    padding-left: 8px;
    border-left: 4px solid transparent;
  }
  nav.sidebar a:hover,
  nav.sidebar a.active {
    color: #22c55e;
    border-left-color: #22c55e;
  }
  /* Conteúdo principal */
  main.content {
    margin-left: 260px;
    padding: 40px 60px;
    flex-grow: 1;
    overflow-y: auto;
  }
  main.content section {
    background: #f9fafbcc;
    border-radius: 16px;
    padding: 30px 36px;
    box-shadow: 0 8px 20px rgba(34, 197, 94, 0.12);
    margin-bottom: 48px;
    transition: box-shadow 0.3s ease;
  }
  main.content section:hover {
    box-shadow: 0 12px 28px rgba(34, 197, 94, 0.25);
  }
  h2.section-title {
    font-family: 'Orbitron', monospace;
    font-weight: 700;
    font-size: 2.2rem;
    color: #4c1d95;
    margin-bottom: 24px;
    letter-spacing: 0.07em;
    text-transform: uppercase;
  }
  p {
    font-size: 1.1rem;
    color: #334155;
    line-height: 1.6;
    font-weight: 500;
  }
  /* Blog cards */
  article.blog-post {
    background: white;
    border-radius: 12px;
    box-shadow: 0 6px 15px rgba(34, 197, 94, 0.1);
    padding: 20px 28px;
    margin-bottom: 24px;
    transition: transform 0.25s ease, box-shadow 0.25s ease;
  }
  article.blog-post:hover {
    transform: translateY(-6px);
    box-shadow: 0 10px 30px rgba(34, 197, 94, 0.2);
  }
  article.blog-post h3 {
    font-family: 'Orbitron', monospace;
    color: #15803d;
    font-size: 1.4rem;
    margin-bottom: 12px;
    letter-spacing: 0.04em;
    text-transform: uppercase;
  }
  /* Botões de links plataformas */
  .platform-links {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
  }
  .platform-links a {
    flex: 1 1 140px;
    background: #22c55e;
    color: white;
    text-decoration: none;
    font-weight: 700;
    font-size: 1.1rem;
    padding: 14px 18px;
    border-radius: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    box-shadow: 0 6px 15px rgb(34 197 94 / 0.45);
    transition: background-color 0.3s ease, box-shadow 0.3s ease;
  }
  .platform-links a:hover {
    background: #15803d;
    box-shadow: 0 8px 22px rgb(21 128 61 / 0.75);
  }
  .platform-links a .icon {
    font-size: 1.5rem;
  }
  /* Footer */
  footer {
    background: #5b21b6;
    color: #e0e7ff;
    font-family: 'Orbitron', monospace;
    font-weight: 600;
    text-align: center;
    padding: 22px 15px;
    letter-spacing: 0.12em;
    position: fixed;
    bottom: 0;
    width: calc(100% - 260px);
    margin-left: 260px;
    user-select: none;
    box-shadow: 0 -6px 15px rgba(34, 197, 94, 0.3);
  }
  /* Scrollbar personalizado */
  main.content::-webkit-scrollbar {
    width: 10px;
  }
  main.content::-webkit-scrollbar-track {
    background: #f0fdfa;
    border-radius: 8px;
  }
  main.content::-webkit-scrollbar-thumb {
    background: #22c55e;
    border-radius: 8px;
  }
  /* Responsividade */
  @media (max-width: 900px) {
    nav.sidebar {
      position: relative;
      width: 100%;
      height: auto;
      flex-direction: row;
      padding: 12px 15px;
      justify-content: center;
      box-shadow: none;
    }
    nav.sidebar h1 {
      display: none;
    }
    nav.sidebar a {
      margin: 0 16px;
      padding-left: 0;
      border-left: none;
      font-size: 1rem;
    }
    nav.sidebar a.active {
      border-bottom: 3px solid #22c55e;
      border-left: none;
    }
    main.content {
      margin: 0;
      padding: 20px 15px 80px;
      overflow: visible;
    }
    footer {
      width: 100%;
      margin-left: 0;
      position: relative;
      box-shadow: none;
    }
  }
</style>
</head>
<body>
  <nav class="sidebar" role="navigation" aria-label="Menu principal">
    <h1>DieguinhoNaVoz</h1>
    <a href="#home" class="active" aria-current="page">Início</a>
    <a href="#sobre">Sobre</a>
    <a href="#blog">Blog</a>
    <a href="#plataformas">Plataformas</a>
  </nav>
  <main class="content">
    <section id="home" tabindex="0" aria-label="Seção de boas-vindas">
      <h2 class="section-title">Bem-vindo à minha jornada musical</h2>
      <p>
        Olá! Sou DieguinhoNaVoz, um jovem cantor e compositor de 15 anos com uma paixão por criar músicas que tocam o coração e exploram novos horizontes. Minha missão é compartilhar histórias autênticas e sons que inspiram.
      </p>
    </section>

    <section id="sobre" tabindex="0" aria-label="Seção sobre o artista">
      <h2 class="section-title">Sobre mim</h2>
      <p>
        Meu nome é Diego e estou no início da minha carreira como cantor e compositor. Cada canção que componho é uma pequena exploração, uma história que quero compartilhar com o mundo. Busco criar músicas que inspirem e unam pessoas, oferecendo uma experiência sonora autêntica e envolvente.
      </p>
    </section>

    <section id="blog" tabindex="0" aria-label="Seção do blog com novidades">
      <h2 class="section-title">Novidades no blog</h2>

      <article class="blog-post" tabindex="0">
        <h3>🎵 Em breve: novo single futurista</h3>
        <p>
          Estou preparando uma faixa que mistura sons eletrônicos e melodias que evocam paisagens de futuros possíveis. Fique atento para as novidades e prévias exclusivas nas minhas redes sociais!
        </p>
      </article>

      <article class="blog-post" tabindex="0">
        <h3>🎙️ Por trás da criação</h3>
        <p>
          Cada composição começa com uma inspiração, uma ideia que cresce até se tornar uma canção. No blog, vou compartilhar meus processos criativos e as tecnologias que uso para dar vida à minha música.
        </p>
      </article>
    </section>

    <section id="plataformas" tabindex="0" aria-label="Seção com links para plataformas">
      <h2 class="section-title">Me acompanhe nas plataformas</h2>
      <div class="platform-links">
        <a href="#" target="_blank" rel="noopener" aria-label="Instagram do DieguinhoNaVoz">
          <i class="fab fa-instagram icon" aria-hidden="true"></i> Instagram
        </a>
        <a href="#" target="_blank" rel="noopener" aria-label="YouTube do DieguinhoNaVoz">
          <i class="fab fa-youtube icon" aria-hidden="true"></i> YouTube
        </a>
        <a href="#" target="_blank" rel="noopener" aria-label="Spotify do DieguinhoNaVoz">
          <i class="fab fa-spotify icon" aria-hidden="true"></i> Spotify
        </a>
      </div>
    </section>
  </main>
  <footer>
    © 2025 DieguinhoNaVoz — Música, inspiração e futuro
  </footer>
</body>
</html>
