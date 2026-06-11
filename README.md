<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Anderson Júnior — Engenharia de Software</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;600&family=Inter:wght@300;400;500;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0d1117;
      --surface: #161b22;
      --border: #21262d;
      --accent: #58a6ff;
      --accent2: #3fb950;
      --text: #e6edf3;
      --muted: #7d8590;
      --tag-bg: #1f2937;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Inter', sans-serif;
      font-size: 15px;
      line-height: 1.7;
    }

    /* ── HEADER ── */
    header {
      border-bottom: 1px solid var(--border);
      padding: 20px 0;
      position: sticky;
      top: 0;
      background: rgba(13,17,23,0.92);
      backdrop-filter: blur(8px);
      z-index: 100;
    }
    nav {
      max-width: 860px;
      margin: 0 auto;
      padding: 0 24px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .nav-logo {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 14px;
      color: var(--accent);
      letter-spacing: 0.04em;
    }
    .nav-links { display: flex; gap: 24px; list-style: none; }
    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 13px;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--text); }

    /* ── HERO ── */
    .hero {
      max-width: 860px;
      margin: 0 auto;
      padding: 80px 24px 64px;
    }
    .hero-tag {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 12px;
      color: var(--accent2);
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 16px;
    }
    .hero h1 {
      font-size: clamp(32px, 6vw, 52px);
      font-weight: 700;
      line-height: 1.15;
      letter-spacing: -0.02em;
      margin-bottom: 20px;
    }
    .hero h1 span { color: var(--accent); }
    .hero-sub {
      font-size: 17px;
      color: var(--muted);
      max-width: 560px;
      margin-bottom: 36px;
      font-weight: 300;
    }
    .hero-links { display: flex; flex-wrap: wrap; gap: 12px; }
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      padding: 9px 18px;
      border-radius: 6px;
      font-size: 13px;
      font-weight: 500;
      text-decoration: none;
      transition: all 0.2s;
      border: 1px solid transparent;
    }
    .btn-primary {
      background: var(--accent);
      color: #0d1117;
    }
    .btn-primary:hover { background: #79b8ff; }
    .btn-outline {
      border-color: var(--border);
      color: var(--text);
      background: var(--surface);
    }
    .btn-outline:hover { border-color: var(--accent); color: var(--accent); }

    /* ── SECTIONS ── */
    section {
      max-width: 860px;
      margin: 0 auto;
      padding: 60px 24px;
      border-top: 1px solid var(--border);
    }
    .section-label {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 11px;
      color: var(--muted);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 28px;
    }

    /* ── SKILLS GRID ── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 12px;
    }
    .skill-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 16px 18px;
      transition: border-color 0.2s;
    }
    .skill-card:hover { border-color: var(--accent); }
    .skill-category {
      font-size: 11px;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.08em;
      margin-bottom: 8px;
      font-family: 'IBM Plex Mono', monospace;
    }
    .skill-name {
      font-size: 14px;
      font-weight: 500;
      color: var(--text);
    }
    .skill-badge {
      display: inline-block;
      margin-top: 6px;
      font-size: 11px;
      padding: 2px 8px;
      border-radius: 20px;
      background: var(--tag-bg);
      color: var(--muted);
    }
    .skill-badge.learning { color: var(--accent2); }

    /* ── TIMELINE (EXPERIENCE) ── */
    .timeline { display: flex; flex-direction: column; gap: 0; }
    .timeline-item {
      display: grid;
      grid-template-columns: 1px 1fr;
      gap: 0 24px;
      padding-bottom: 36px;
      position: relative;
    }
    .timeline-item:last-child { padding-bottom: 0; }
    .timeline-line {
      background: var(--border);
      position: relative;
      margin-top: 8px;
    }
    .timeline-dot {
      width: 9px;
      height: 9px;
      border-radius: 50%;
      background: var(--accent);
      border: 2px solid var(--bg);
      position: absolute;
      left: -4px;
      top: 0;
    }
    .timeline-content { padding-left: 0; }
    .timeline-header {
      display: flex;
      flex-wrap: wrap;
      align-items: baseline;
      gap: 8px;
      margin-bottom: 6px;
    }
    .timeline-role {
      font-size: 15px;
      font-weight: 600;
    }
    .timeline-company {
      font-size: 13px;
      color: var(--accent);
    }
    .timeline-period {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 11px;
      color: var(--muted);
      margin-left: auto;
    }
    .timeline-desc {
      color: var(--muted);
      font-size: 14px;
      line-height: 1.65;
    }

    /* ── PROJECT CARD ── */
    .project-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 24px;
      transition: border-color 0.2s, transform 0.2s;
    }
    .project-card:hover {
      border-color: var(--accent);
      transform: translateY(-2px);
    }
    .project-title {
      font-size: 16px;
      font-weight: 600;
      margin-bottom: 8px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .project-desc {
      color: var(--muted);
      font-size: 14px;
      margin-bottom: 14px;
    }
    .tag-list { display: flex; flex-wrap: wrap; gap: 6px; }
    .tag {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 11px;
      padding: 3px 9px;
      border-radius: 4px;
      background: var(--tag-bg);
      color: var(--accent);
    }

    /* ── EDUCATION ── */
    .edu-grid { display: grid; gap: 14px; }
    .edu-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 18px 20px;
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      flex-wrap: wrap;
      gap: 8px;
    }
    .edu-name { font-weight: 600; font-size: 15px; }
    .edu-course { color: var(--muted); font-size: 13px; margin-top: 3px; }
    .edu-status {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 11px;
      padding: 3px 10px;
      border-radius: 20px;
      white-space: nowrap;
    }
    .status-ongoing { background: #1a2f1a; color: var(--accent2); }
    .status-done { background: #1f2937; color: var(--muted); }

    /* ── CONTACT ── */
    .contact-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 12px;
    }
    .contact-item {
      display: flex;
      align-items: center;
      gap: 12px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 14px 16px;
      text-decoration: none;
      color: var(--text);
      transition: border-color 0.2s;
    }
    .contact-item:hover { border-color: var(--accent); color: var(--accent); }
    .contact-icon { font-size: 16px; }
    .contact-label { font-size: 13px; font-weight: 500; }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--border);
      text-align: center;
      padding: 28px 24px;
      color: var(--muted);
      font-size: 12px;
      font-family: 'IBM Plex Mono', monospace;
    }

    /* ── TERMINAL BLINK ── */
    .cursor {
      display: inline-block;
      width: 3px;
      height: 1em;
      background: var(--accent);
      margin-left: 2px;
      vertical-align: text-bottom;
      animation: blink 1s step-end infinite;
    }
    @keyframes blink { 50% { opacity: 0; } }

    /* ── SCROLL REVEAL ── */
    .reveal {
      opacity: 0;
      transform: translateY(18px);
      transition: opacity 0.5s ease, transform 0.5s ease;
    }
    .reveal.visible { opacity: 1; transform: none; }

    @media (max-width: 600px) {
      .nav-links { display: none; }
      .timeline-period { margin-left: 0; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <header>
    <nav>
      <span class="nav-logo">anderson.junior ~$</span>
      <ul class="nav-links">
        <li><a href="#skills">Skills</a></li>
        <li><a href="#experience">Experiência</a></li>
        <li><a href="#projects">Projetos</a></li>
        <li><a href="#education">Formação</a></li>
        <li><a href="#contact">Contato</a></li>
      </ul>
    </nav>
  </header>

  <!-- HERO -->
  <div class="hero">
    <p class="hero-tag">// disponível para estágio &amp; júnior TI</p>
    <h1>Anderson Júnior<br><span>Engenharia de Software</span><span class="cursor"></span></h1>
    <p class="hero-sub">
      Estudante de Engenharia de Software (2º período) em BH. Foco em desenvolvimento web e suporte de TI, com experiência real em ambientes técnicos e administrativos.
    </p>
    <div class="hero-links">
      <a class="btn btn-primary" href="https://github.com/juniosilvaw" target="_blank">
        <svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8a8 8 0 005.47 7.59c.4.07.55-.17.55-.38v-1.34c-2.23.48-2.7-1.07-2.7-1.07-.36-.93-.89-1.18-.89-1.18-.73-.5.05-.49.05-.49.8.06 1.23.82 1.23.82.71 1.22 1.87.87 2.33.66.07-.52.28-.87.5-1.07-1.77-.2-3.63-.89-3.63-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82A7.7 7.7 0 018 3.8c.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.28.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48v2.19c0 .21.15.46.55.38A8 8 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
        GitHub
      </a>
      <a class="btn btn-outline" href="https://linkedin.com/in/juniosilvaw" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452H17.21v-5.569c0-1.327-.027-3.037-1.852-3.037-1.854 0-2.138 1.448-2.138 2.943v5.663H9.984V9h3.093v1.561h.044c.431-.815 1.48-1.675 3.046-1.675 3.258 0 3.862 2.145 3.862 4.934v6.632zM5.337 7.433a1.791 1.791 0 110-3.582 1.791 1.791 0 010 3.582zm1.549 13.019H3.79V9h3.096v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.226.792 24 1.771 24h20.451C23.2 24 24 23.226 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="btn btn-outline" href="mailto:anderson.junsilva@gmail.com">
        ✉ E-mail
      </a>
    </div>
  </div>

  <!-- SKILLS -->
  <section id="skills">
    <p class="section-label">// conhecimentos técnicos</p>
    <div class="skills-grid reveal">
      <div class="skill-card">
        <div class="skill-category">Linguagens</div>
        <div class="skill-name">JavaScript</div>
        <span class="skill-badge learning">em andamento</span>
      </div>
      <div class="skill-card">
        <div class="skill-category">Linguagens</div>
        <div class="skill-name">Linguagem C</div>
        <span class="skill-badge learning">em andamento</span>
      </div>
      <div class="skill-card">
        <div class="skill-category">Front-end</div>
        <div class="skill-name">HTML &amp; CSS</div>
        <span class="skill-badge">concluído</span>
      </div>
      <div class="skill-card">
        <div class="skill-category">Fundamentos</div>
        <div class="skill-name">Lógica de Programação</div>
        <span class="skill-badge learning">em andamento</span>
      </div>
      <div class="skill-card">
        <div class="skill-category">Ferramentas</div>
        <div class="skill-name">Git &amp; GitHub</div>
        <span class="skill-badge learning">em andamento</span>
      </div>
      <div class="skill-card">
        <div class="skill-category">Suporte</div>
        <div class="skill-name">Suporte TI</div>
        <span class="skill-badge">experiência real</span>
      </div>
    </div>
  </section>

  <!-- EXPERIENCE -->
  <section id="experience">
    <p class="section-label">// experiência profissional</p>
    <div class="timeline reveal">

      <div class="timeline-item">
        <div class="timeline-line"><div class="timeline-dot"></div></div>
        <div class="timeline-content">
          <div class="timeline-header">
            <span class="timeline-role">Estagiário de TI</span>
            <span class="timeline-company">FUNASA</span>
            <span class="timeline-period">9 meses</span>
          </div>
          <p class="timeline-desc">
            Prestei suporte técnico de 1º nível aos usuários, realizei organização e controle de documentação técnica, e auxiliei nas rotinas de infraestrutura interna. Primeiro contato direto com ambiente de TI corporativo.
          </p>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-line"><div class="timeline-dot"></div></div>
        <div class="timeline-content">
          <div class="timeline-header">
            <span class="timeline-role">Técnico em Secretariado</span>
            <span class="timeline-company">Pluma Terceirizações</span>
            <span class="timeline-period">6 anos</span>
          </div>
          <p class="timeline-desc">
            Gestão e controle de documentos físicos e digitais, operação de sistemas internos, cumprimento rigoroso de prazos e apoio a processos administrativos. Desenvolvi organização, atenção a detalhes e responsabilidade em ambiente profissional.
          </p>
        </div>
      </div>

    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <p class="section-label">// projetos</p>
    <div class="reveal" style="display: grid; gap: 14px;">

      <div class="project-card">
        <div class="project-title">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="#58a6ff"><path d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8z"/></svg>
          Currículo Online
        </div>
        <p class="project-desc">
          Site de currículo pessoal desenvolvido com HTML, CSS e JavaScript puro. Design responsivo com tema escuro, inspirado em interfaces de terminal — pensado para funcionar como portfólio público no GitHub Pages.
        </p>
        <div class="tag-list">
          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
          <span class="tag">JavaScript</span>
          <span class="tag">GitHub Pages</span>
        </div>
      </div>

      <div class="project-card" style="border-style: dashed; opacity: 0.6;">
        <div class="project-title">🚧 Próximo projeto</div>
        <p class="project-desc">Em breve — calculadora ou app de lista de tarefas em JavaScript puro.</p>
        <div class="tag-list">
          <span class="tag">JavaScript</span>
          <span class="tag">DOM</span>
        </div>
      </div>

    </div>
  </section>

  <!-- EDUCATION -->
  <section id="education">
    <p class="section-label">// formação</p>
    <div class="edu-grid reveal">
      <div class="edu-card">
        <div>
          <div class="edu-name">Estácio de Sá</div>
          <div class="edu-course">Bacharelado em Engenharia de Software · 2º período</div>
        </div>
        <span class="edu-status status-ongoing">Em andamento</span>
      </div>
      <div class="edu-card">
        <div>
          <div class="edu-name">Instituto Universal Brasileiro</div>
          <div class="edu-course">Curso Técnico em Secretariado</div>
        </div>
        <span class="edu-status status-done">Concluído</span>
      </div>
    </div>

    <div style="margin-top: 20px;" class="reveal">
      <p style="font-family: 'IBM Plex Mono', monospace; font-size: 11px; color: var(--muted); letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 14px;">// cursos complementares</p>
      <div class="tag-list">
        <span class="tag" style="color: var(--accent2);">HTML &amp; CSS ✓</span>
        <span class="tag" style="color: var(--accent2);">Introdução a Programação Front-End ✓</span>
        <span class="tag">JavaScript</span>
        <span class="tag">Linguagem C</span>
        <span class="tag">Lógica de Programação</span>
        <span class="tag">Git &amp; GitHub</span>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <p class="section-label">// contato</p>
    <div class="contact-grid reveal">
      <a class="contact-item" href="mailto:anderson.junsilva@gmail.com">
        <span class="contact-icon">✉</span>
        <div>
          <div class="contact-label">E-mail</div>
          <div style="font-size:12px; color: var(--muted);">anderson.junsilva@gmail.com</div>
        </div>
      </a>
      <a class="contact-item" href="https://linkedin.com/in/juniosilvaw" target="_blank">
        <span class="contact-icon">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452H17.21v-5.569c0-1.327-.027-3.037-1.852-3.037-1.854 0-2.138 1.448-2.138 2.943v5.663H9.984V9h3.093v1.561h.044c.431-.815 1.48-1.675 3.046-1.675 3.258 0 3.862 2.145 3.862 4.934v6.632zM5.337 7.433a1.791 1.791 0 110-3.582 1.791 1.791 0 010 3.582zm1.549 13.019H3.79V9h3.096v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.226.792 24 1.771 24h20.451C23.2 24 24 23.226 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        </span>
        <div>
          <div class="contact-label">LinkedIn</div>
          <div style="font-size:12px; color: var(--muted);">linkedin.com/in/juniosilvaw</div>
        </div>
      </a>
      <a class="contact-item" href="https://github.com/juniosilvaw" target="_blank">
        <span class="contact-icon">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8a8 8 0 005.47 7.59c.4.07.55-.17.55-.38v-1.34c-2.23.48-2.7-1.07-2.7-1.07-.36-.93-.89-1.18-.89-1.18-.73-.5.05-.49.05-.49.8.06 1.23.82 1.23.82.71 1.22 1.87.87 2.33.66.07-.52.28-.87.5-1.07-1.77-.2-3.63-.89-3.63-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82A7.7 7.7 0 018 3.8c.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.28.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48v2.19c0 .21.15.46.55.38A8 8 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
        </span>
        <div>
          <div class="contact-label">GitHub</div>
          <div style="font-size:12px; color: var(--muted);">github.com/juniosilvaw</div>
        </div>
      </a>
      <a class="contact-item" href="tel:+5531973582158">
        <span class="contact-icon">📱</span>
        <div>
          <div class="contact-label">Telefone</div>
          <div style="font-size:12px; color: var(--muted);">+55 31 9 7358-2158</div>
        </div>
      </a>
    </div>
  </section>

  <footer>
    <p>Anderson Júnior Cardoso Silva · Belo Horizonte, MG · 2026</p>
  </footer>

  <script>
    // Scroll reveal
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
    }, { threshold: 0.1 });
    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  </script>
</body>
</html>

