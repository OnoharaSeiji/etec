<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Apostila Preparatória ETEC Vestibulinho</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Source+Sans+3:wght@300;400;600;700&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0e0f14;
    --surface: #161820;
    --surface2: #1e2029;
    --border: #2a2d3a;
    --text: #e8eaf0;
    --muted: #8890a8;
    --accent-port: #e8734a;
    --accent-mat: #4a9ede;
    --accent-bio: #5cbb7a;
    --accent-qui: #c97be8;
    --accent-fis: #f0c94a;
    --accent-his: #e85a7a;
    --accent-geo: #4ad4c8;
    --gold: #d4a843;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Source Sans 3', sans-serif;
    font-weight: 300;
    line-height: 1.7;
    font-size: 15px;
  }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 60px 20px;
    position: relative;
    overflow: hidden;
    background: radial-gradient(ellipse at 30% 40%, rgba(232,115,74,0.08) 0%, transparent 60%),
                radial-gradient(ellipse at 70% 60%, rgba(74,158,222,0.08) 0%, transparent 60%),
                var(--bg);
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      0deg, transparent, transparent 40px,
      rgba(255,255,255,0.015) 40px, rgba(255,255,255,0.015) 41px
    ),
    repeating-linear-gradient(
      90deg, transparent, transparent 40px,
      rgba(255,255,255,0.015) 40px, rgba(255,255,255,0.015) 41px
    );
  }
  .hero-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--gold);
    border: 1px solid var(--gold);
    padding: 6px 20px;
    border-radius: 2px;
    margin-bottom: 28px;
    opacity: 0;
    animation: fadeUp 0.8s 0.2s ease forwards;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(38px, 7vw, 90px);
    font-weight: 900;
    line-height: 1.05;
    letter-spacing: -2px;
    max-width: 900px;
    opacity: 0;
    animation: fadeUp 0.8s 0.4s ease forwards;
  }
  .hero h1 span { color: var(--gold); }
  .hero-sub {
    margin-top: 20px;
    font-size: 17px;
    color: var(--muted);
    max-width: 560px;
    opacity: 0;
    animation: fadeUp 0.8s 0.6s ease forwards;
  }
  .hero-meta {
    display: flex;
    gap: 32px;
    margin-top: 40px;
    opacity: 0;
    animation: fadeUp 0.8s 0.8s ease forwards;
    flex-wrap: wrap;
    justify-content: center;
  }
  .hero-stat {
    text-align: center;
  }
  .hero-stat strong {
    display: block;
    font-family: 'Playfair Display', serif;
    font-size: 32px;
    color: var(--gold);
  }
  .hero-stat span { font-size: 12px; color: var(--muted); letter-spacing: 1px; text-transform: uppercase; }
  @keyframes fadeUp {
    from { opacity:0; transform: translateY(20px); }
    to { opacity:1; transform: translateY(0); }
  }

  /* NAV */
  .nav-sticky {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(14,15,20,0.95);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    padding: 0 20px;
  }
  .nav-inner {
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    gap: 0;
    overflow-x: auto;
    scrollbar-width: none;
  }
  .nav-inner::-webkit-scrollbar { display: none; }
  .nav-tab {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 16px 20px;
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.5px;
    text-decoration: none;
    color: var(--muted);
    border-bottom: 2px solid transparent;
    transition: all 0.2s;
    white-space: nowrap;
    cursor: pointer;
  }
  .nav-tab:hover { color: var(--text); }
  .nav-tab.port { border-color: var(--accent-port); color: var(--accent-port); }
  .nav-tab.mat  { border-color: var(--accent-mat);  color: var(--accent-mat);  }
  .nav-tab.bio  { border-color: var(--accent-bio);  color: var(--accent-bio);  }
  .nav-tab.qui  { border-color: var(--accent-qui);  color: var(--accent-qui);  }
  .nav-tab.fis  { border-color: var(--accent-fis);  color: var(--accent-fis);  }
  .nav-tab.his  { border-color: var(--accent-his);  color: var(--accent-his);  }
  .nav-tab.geo  { border-color: var(--accent-geo);  color: var(--accent-geo);  }
  .nav-dot { width: 8px; height: 8px; border-radius: 50%; background: currentColor; }

  /* SUBJECT SECTION */
  .subject-section {
    padding: 80px 20px;
    border-bottom: 1px solid var(--border);
  }
  .section-inner { max-width: 1100px; margin: 0 auto; }
  .section-header {
    display: flex;
    align-items: flex-start;
    gap: 24px;
    margin-bottom: 60px;
    padding-bottom: 40px;
    border-bottom: 1px solid var(--border);
  }
  .section-icon {
    width: 64px;
    height: 64px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 28px;
    flex-shrink: 0;
  }
  .section-title-block h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(28px, 4vw, 48px);
    font-weight: 900;
    line-height: 1.1;
    margin-bottom: 8px;
  }
  .section-title-block p { color: var(--muted); font-size: 15px; max-width: 600px; }
  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  /* TOPIC GRID */
  .topic-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 24px;
    margin-bottom: 40px;
  }
  .topic-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .topic-card:hover { transform: translateY(-2px); }
  .topic-card-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 16px;
  }
  .topic-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    padding: 4px 10px;
    border-radius: 4px;
    letter-spacing: 0.5px;
  }
  .topic-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 19px;
    font-weight: 700;
  }
  .topic-card p { color: var(--muted); font-size: 14px; margin-bottom: 16px; line-height: 1.6; }

  /* CONTENT ELEMENTS */
  .concept-box {
    background: var(--surface2);
    border-left: 3px solid currentColor;
    border-radius: 0 8px 8px 0;
    padding: 16px 20px;
    margin: 12px 0;
    font-size: 14px;
  }
  .concept-box strong { display: block; font-size: 13px; letter-spacing: 0.5px; margin-bottom: 6px; opacity: 0.8; }
  .formula-box {
    background: #0a0b0f;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    margin: 12px 0;
    overflow-x: auto;
  }
  .formula-box span { color: var(--gold); font-weight: 600; }

  .tip-box {
    background: rgba(212,168,67,0.08);
    border: 1px solid rgba(212,168,67,0.3);
    border-radius: 8px;
    padding: 14px 18px;
    margin: 12px 0;
    font-size: 14px;
  }
  .tip-box::before { content: "💡 DICA: "; font-weight: 700; color: var(--gold); }

  .exam-box {
    background: rgba(255,255,255,0.03);
    border: 1px dashed var(--border);
    border-radius: 8px;
    padding: 16px 20px;
    margin: 12px 0;
    font-size: 13px;
  }
  .exam-box::before { content: "📝 CAIU NA PROVA: "; font-weight: 700; color: var(--muted); font-size: 11px; letter-spacing: 1px; }

  ul.content-list { padding-left: 20px; }
  ul.content-list li { margin-bottom: 8px; font-size: 14px; color: var(--text); }
  ul.content-list li::marker { color: var(--gold); }

  .two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  @media(max-width: 600px) { .two-col { grid-template-columns: 1fr; } }

  table.data-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
    margin: 12px 0;
  }
  table.data-table th {
    background: rgba(255,255,255,0.06);
    padding: 10px 14px;
    text-align: left;
    font-weight: 600;
    font-size: 12px;
    letter-spacing: 0.5px;
    border-bottom: 1px solid var(--border);
  }
  table.data-table td {
    padding: 9px 14px;
    border-bottom: 1px solid rgba(255,255,255,0.04);
    color: var(--muted);
  }
  table.data-table tr:hover td { color: var(--text); background: rgba(255,255,255,0.02); }

  .full-width { grid-column: 1 / -1; }

  .section-divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 32px 0;
  }

  /* Color overrides per subject */
  .port .topic-card { border-top: 2px solid var(--accent-port); }
  .port .topic-num { background: rgba(232,115,74,0.15); color: var(--accent-port); }
  .port .concept-box { color: var(--accent-port); }
  .port .section-icon { background: rgba(232,115,74,0.12); color: var(--accent-port); }
  .port .section-title-block h2 { color: var(--accent-port); }
  .port .section-label { color: var(--accent-port); }

  .mat .topic-card { border-top: 2px solid var(--accent-mat); }
  .mat .topic-num { background: rgba(74,158,222,0.15); color: var(--accent-mat); }
  .mat .concept-box { color: var(--accent-mat); }
  .mat .section-icon { background: rgba(74,158,222,0.12); color: var(--accent-mat); }
  .mat .section-title-block h2 { color: var(--accent-mat); }
  .mat .section-label { color: var(--accent-mat); }

  .bio .topic-card { border-top: 2px solid var(--accent-bio); }
  .bio .topic-num { background: rgba(92,187,122,0.15); color: var(--accent-bio); }
  .bio .concept-box { color: var(--accent-bio); }
  .bio .section-icon { background: rgba(92,187,122,0.12); color: var(--accent-bio); }
  .bio .section-title-block h2 { color: var(--accent-bio); }
  .bio .section-label { color: var(--accent-bio); }

  .qui .topic-card { border-top: 2px solid var(--accent-qui); }
  .qui .topic-num { background: rgba(201,123,232,0.15); color: var(--accent-qui); }
  .qui .concept-box { color: var(--accent-qui); }
  .qui .section-icon { background: rgba(201,123,232,0.12); color: var(--accent-qui); }
  .qui .section-title-block h2 { color: var(--accent-qui); }
  .qui .section-label { color: var(--accent-qui); }

  .fis .topic-card { border-top: 2px solid var(--accent-fis); }
  .fis .topic-num { background: rgba(240,201,74,0.15); color: var(--accent-fis); }
  .fis .concept-box { color: var(--accent-fis); }
  .fis .section-icon { background: rgba(240,201,74,0.12); color: var(--accent-fis); }
  .fis .section-title-block h2 { color: var(--accent-fis); }
  .fis .section-label { color: var(--accent-fis); }

  .his .topic-card { border-top: 2px solid var(--accent-his); }
  .his .topic-num { background: rgba(232,90,122,0.15); color: var(--accent-his); }
  .his .concept-box { color: var(--accent-his); }
  .his .section-icon { background: rgba(232,90,122,0.12); color: var(--accent-his); }
  .his .section-title-block h2 { color: var(--accent-his); }
  .his .section-label { color: var(--accent-his); }

  .geo .topic-card { border-top: 2px solid var(--accent-geo); }
  .geo .topic-num { background: rgba(74,212,200,0.15); color: var(--accent-geo); }
  .geo .concept-box { color: var(--accent-geo); }
  .geo .section-icon { background: rgba(74,212,200,0.12); color: var(--accent-geo); }
  .geo .section-title-block h2 { color: var(--accent-geo); }
  .geo .section-label { color: var(--accent-geo); }

  /* FOOTER */
  footer {
    text-align: center;
    padding: 60px 20px;
    color: var(--muted);
    font-size: 13px;
    border-top: 1px solid var(--border);
  }
  footer strong { color: var(--gold); }

  /* Back to top */
  .back-top {
    display: inline-block;
    margin-top: 20px;
    padding: 10px 24px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    color: var(--muted);
    text-decoration: none;
    font-size: 13px;
    font-weight: 600;
    transition: all 0.2s;
  }
  .back-top:hover { color: var(--text); border-color: var(--gold); }

  .highlight { color: var(--gold); font-weight: 600; }
  .tag {
    display: inline-block;
    padding: 2px 8px;
    border-radius: 4px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.5px;
    margin-right: 4px;
    margin-bottom: 4px;
  }

  /* Quiz section */
  .quiz-section {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px;
    margin-top: 24px;
  }
  .quiz-section h4 {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    margin-bottom: 20px;
  }
  .question-item {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px;
    margin-bottom: 16px;
  }
  .question-item .q-text { font-size: 14px; margin-bottom: 12px; font-weight: 400; }
  .option {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    padding: 6px 10px;
    border-radius: 4px;
    font-size: 13px;
    cursor: pointer;
    margin-bottom: 4px;
    transition: background 0.15s;
    border: 1px solid transparent;
  }
  .option:hover { background: rgba(255,255,255,0.04); }
  .option.correct { background: rgba(92,187,122,0.12); border-color: rgba(92,187,122,0.4); color: #5cbb7a; }
  .option.wrong { background: rgba(232,90,122,0.12); border-color: rgba(232,90,122,0.4); color: #e85a7a; }
  .opt-letter {
    width: 22px;
    height: 22px;
    border-radius: 4px;
    background: var(--surface2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    flex-shrink: 0;
  }
  .show-answer-btn {
    padding: 8px 16px;
    background: transparent;
    border: 1px solid var(--border);
    border-radius: 6px;
    color: var(--muted);
    font-size: 12px;
    cursor: pointer;
    font-weight: 600;
    letter-spacing: 0.5px;
    transition: all 0.2s;
    margin-top: 8px;
  }
  .show-answer-btn:hover { border-color: var(--gold); color: var(--gold); }
  .answer-reveal {
    display: none;
    margin-top: 10px;
    padding: 10px 14px;
    background: rgba(212,168,67,0.08);
    border-left: 3px solid var(--gold);
    border-radius: 0 6px 6px 0;
    font-size: 13px;
    color: #c8a840;
  }
  .answer-reveal.show { display: block; }
</style>
</head>
<body>

<!-- HERO -->
<section class="hero" id="top">
  <div class="hero-badge">Vestibulinho ETEC · 2018–2026</div>
  <h1>Apostila Preparatória<br><span>Vestibulinho ETEC</span></h1>
  <p class="hero-sub">Conteúdo completo extraído das provas reais. Teoria, exemplos e exercícios resolvidos para todas as matérias.</p>
  <div class="hero-meta">
    <div class="hero-stat"><strong>7</strong><span>Matérias</span></div>
    <div class="hero-stat"><strong>50+</strong><span>Tópicos</span></div>
    <div class="hero-stat"><strong>5</strong><span>Anos de provas</span></div>
    <div class="hero-stat"><strong>250+</strong><span>Questões analisadas</span></div>
  </div>
</section>

<!-- NAVIGATION -->
<nav class="nav-sticky">
  <div class="nav-inner">
    <a href="#portugues" class="nav-tab port"><span class="nav-dot"></span>Português</a>
    <a href="#matematica" class="nav-tab mat"><span class="nav-dot"></span>Matemática</a>
    <a href="#biologia" class="nav-tab bio"><span class="nav-dot"></span>Biologia</a>
    <a href="#quimica" class="nav-tab qui"><span class="nav-dot"></span>Química</a>
    <a href="#fisica" class="nav-tab fis"><span class="nav-dot"></span>Física</a>
    <a href="#historia" class="nav-tab his"><span class="nav-dot"></span>História</a>
    <a href="#geografia" class="nav-tab geo"><span class="nav-dot"></span>Geografia</a>
  </div>
</nav>

<!-- ═══════════════════════════════════════
     PORTUGUÊS
═══════════════════════════════════════ -->
<section class="subject-section port" id="portugues">
  <div class="section-inner">
    <div class="section-header">
      <div class="section-icon">✍️</div>
      <div class="section-title-block">
        <div class="section-label">Matéria 01</div>
        <h2>Língua Portuguesa</h2>
        <p>Interpretação de texto, gramática, figuras de linguagem, gêneros textuais e recursos expressivos. Área com maior peso nas provas do Vestibulinho.</p>
      </div>
    </div>

    <div class="topic-grid">

      <!-- INTERPRETAÇÃO DE TEXTO -->
      <div class="topic-card full-width">
        <div class="topic-card-header">
          <span class="topic-num">01</span>
          <h3>Interpretação de Texto</h3>
        </div>
        <p>A maioria das questões de português parte de um texto. O segredo é identificar o que o enunciado pede.</p>
        <div class="two-col">
          <div>
            <div class="concept-box">
              <strong>O que observar no texto:</strong>
              Tema central, intenção do autor, palavras-chave, relações de causa/consequência, argumento principal vs. exemplos.
            </div>
            <div class="concept-box">
              <strong>Como identificar a ideia principal:</strong>
              Geralmente está no 1º ou último parágrafo. Observe o que se repete ao longo do texto.
            </div>
          </div>
          <div>
            <div class="tip-box">Releia o enunciado DEPOIS de ler o texto para saber exatamente o que buscar. Nunca responda por intuição.</div>
            <div class="exam-box">Provas 2018–2026 trouxeram textos sobre sustentabilidade, animais, saúde e questões sociais. Leia jornais e revistas para se acostumar com diferentes estilos.</div>
          </div>
        </div>
      </div>

      <!-- FUNÇÕES DA LINGUAGEM -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">02</span>
          <h3>Funções da Linguagem</h3>
        </div>
        <p>Cada texto tem uma função predominante. Saber identificá-la é fundamental.</p>
        <table class="data-table">
          <tr><th>Função</th><th>Foco</th><th>Exemplo</th></tr>
          <tr><td>Referencial</td><td>Informar (3ª pessoa)</td><td>Texto científico, notícia</td></tr>
          <tr><td>Emotiva</td><td>Sentimentos do emissor (1ª pessoa)</td><td>Diário, carta pessoal</td></tr>
          <tr><td>Conativa</td><td>Convencer o receptor (2ª pessoa)</td><td>Propaganda, discurso</td></tr>
          <tr><td>Fática</td><td>Manter o contato</td><td>"Alô? Está ouvindo?"</td></tr>
          <tr><td>Metalinguística</td><td>Fala sobre a linguagem</td><td>Dicionário, gramática</td></tr>
          <tr><td>Poética</td><td>A mensagem em si (estética)</td><td>Poema, slogan criativo</td></tr>
        </table>
        <div class="exam-box">Prova 2018 (Q.19): texto dissertativo sobre consumo sustentável = função referencial (informações precisas, linguagem objetiva).</div>
      </div>

      <!-- GÊNEROS TEXTUAIS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">03</span>
          <h3>Gêneros Textuais</h3>
        </div>
        <p>Cada gênero tem características próprias de estrutura, linguagem e finalidade.</p>
        <ul class="content-list">
          <li><span class="highlight">Cartum / Charge:</span> desenho humorístico ou caricatural que satiriza comportamentos humanos; objetivo: criticar; linguagem não verbal ou mista.</li>
          <li><span class="highlight">Tirinha:</span> segmento de história em quadrinhos em faixa horizontal.</li>
          <li><span class="highlight">Infográfico:</span> informação visual com ícones e dados.</li>
          <li><span class="highlight">Texto dissertativo:</span> expõe e argumenta sobre um tema com linguagem objetiva.</li>
          <li><span class="highlight">Texto publicitário / Slogan:</span> convence o receptor; usa recursos retóricos, imperativos e pronomes de 2ª pessoa.</li>
        </ul>
        <div class="exam-box">Prova 2019 (Q.24): cartum evolutivo = características de cartum, objetivo de criticar, linguagem não verbal.</div>
      </div>

      <!-- FIGURAS DE LINGUAGEM -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">04</span>
          <h3>Figuras de Linguagem</h3>
        </div>
        <p>Recursos expressivos que enriquecem a linguagem, muito cobrados nas provas.</p>
        <ul class="content-list">
          <li><span class="highlight">Zeugma:</span> omissão de um termo já citado. Ex: "Você está no meio. E não [está] no fim." (prova 2019)</li>
          <li><span class="highlight">Metáfora:</span> comparação implícita. Ex: "O homem-caranguejo afunda na lama."</li>
          <li><span class="highlight">Metonímia:</span> substituição de um termo por outro relacionado.</li>
          <li><span class="highlight">Ironia:</span> dizer o contrário do que se quer comunicar.</li>
          <li><span class="highlight">Hipérbole:</span> exagero intencional.</li>
          <li><span class="highlight">Personificação:</span> atribuir qualidades humanas a seres inanimados.</li>
          <li><span class="highlight">Eufemismo:</span> suavizar uma ideia desagradável.</li>
          <li><span class="highlight">Antítese:</span> ideias opostas lado a lado.</li>
        </ul>
        <div class="tip-box">A zeugma é figura de SINTAXE (elipse de um elemento já mencionado). Não confunda com zeugma vs. elipse: zeugma = elemento já citado antes; elipse = elemento subentendido pelo contexto.</div>
      </div>

      <!-- GRAMÁTICA: CLASSES DE PALAVRAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">05</span>
          <h3>Classes Gramaticais</h3>
        </div>
        <p>As classes de palavras e suas funções são muito cobradas. Atenção especial a pronomes, advérbios e conjunções.</p>
        <div class="concept-box">
          <strong>Pronomes Oblíquos — cobrado na prova 2018 (Q.01):</strong>
          "ao outro" → substituído por "lhe" (pronome oblíquo de 3ª pessoa, indica destinatário). Formas: me, te, se, lhe, nos, vos, o, a, os, as, lo, la, no, na.
        </div>
        <div class="concept-box">
          <strong>Advérbio vs. Substantivo — prova 2019 (Q.01):</strong>
          "Você está no MEIO desse ambiente" → "meio" = substantivo (locução adverbial de lugar). "Campanha do MEIO ambiente" → "meio" = substantivo formando locução adjetiva.
        </div>
        <div class="concept-box">
          <strong>Conjunções Subordinativas — prova 2026 (Q.23):</strong>
          "Que o homem vem aí" → "Que" = conjunção causal = "porque". Outros valores: condicional (se), concessivo (embora/ainda que), temporal (quando), final (para que).
        </div>
      </div>

      <!-- GRAMÁTICA: VERBOS E LOCUÇÕES -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">06</span>
          <h3>Verbos, Locuções e Vozes Verbais</h3>
        </div>
        <p>Aspectos verbais e locuções verbais formadas por auxiliar + verbo principal.</p>
        <div class="concept-box">
          <strong>Locuções verbais de aspecto — prova 2026 (Q.11):</strong>
          "Acabou indo" = verbo auxiliar "acabar" + gerúndio → indica ação concluída/finalizada com ênfase no término.
        </div>
        <ul class="content-list">
          <li><span class="highlight">Estar + gerúndio:</span> ação em andamento (aspecto durativo)</li>
          <li><span class="highlight">Começar a + infinitivo:</span> início de uma ação</li>
          <li><span class="highlight">Acabar de + infinitivo:</span> ação recém concluída</li>
          <li><span class="highlight">Acabar + gerúndio:</span> ação que termina (ênfase no fim)</li>
          <li><span class="highlight">Ficar + gerúndio:</span> ação repetida ou contínua</li>
          <li><span class="highlight">Costumar + infinitivo:</span> ação habitual</li>
        </ul>
        <div class="concept-box">
          <strong>Imperativo — prova 2026 (Q.24):</strong>
          Na canção "Passaredo": "Some, anda, te esconde, voa" → verbos no imperativo afirmativo, com vocativos (rolinha, andorinha) para persuadir/alertar os pássaros.
        </div>
      </div>

      <!-- VARIEDADE LINGUÍSTICA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">07</span>
          <h3>Variedade Culta e Informal</h3>
        </div>
        <p>A prova costuma misturar registros formais e informais, pedindo para identificar desvios da norma culta.</p>
        <div class="concept-box">
          <strong>Prova 2018 (Q.10):</strong>
          No infográfico "10 Atividades Ecorretas", a frase "Me banhei por 5 min" foge à variedade culta por iniciar com pronome oblíquo (próclise proibida no início de oração na norma culta). O correto seria "Banhei-me por 5 min".
        </div>
        <div class="concept-box">
          <strong>Pronome no início de oração:</strong>
          Na variedade culta escrita, não se inicia oração com pronome oblíquo átono. Em vez de "Me disseram", usa-se "Disseram-me" ou "Eles me disseram".
        </div>
        <div class="tip-box">A prova NÃO pede que você julgue uma variedade como "errada" em sentido absoluto — ela pede que você identifique o que não pertence à variedade culta/padrão.</div>
      </div>

      <!-- FORMAÇÃO DE PALAVRAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">08</span>
          <h3>Formação de Palavras</h3>
        </div>
        <p>Os processos de formação de palavras revelam a estrutura do português.</p>
        <ul class="content-list">
          <li><span class="highlight">Composição por justaposição:</span> junção de dois ou mais radicais sem alteração. Ex: "freeganismo" (free + vegan), "vocalista", "desmatamento".</li>
          <li><span class="highlight">Composição por aglutinação:</span> junção com alteração fonética. Ex: "aguardente" (água + ardente).</li>
          <li><span class="highlight">Derivação prefixal:</span> acréscimo de prefixo. Ex: "desmatamento" (des + mato).</li>
          <li><span class="highlight">Derivação sufixal:</span> acréscimo de sufixo. Ex: "vocalista" (-ista = agente).</li>
          <li><span class="highlight">Derivação parassintética:</span> prefixo e sufixo simultaneamente. Ex: "desmatamento".</li>
          <li><span class="highlight">Hibridismo:</span> radicais de línguas diferentes. Ex: "freeganismo" (inglês + latim).</li>
        </ul>
        <div class="exam-box">Prova 2018 (Q.47): "freeganismo" = composição por justaposição de "free" + "vegan" + sufixo "-ismo". O mesmo processo ocorre em "desmatamento".</div>
      </div>

      <!-- EXERCÍCIOS RESOLVIDOS PORTUGUÊS -->
      <div class="topic-card full-width">
        <div class="quiz-section">
          <h4>🎯 Questões Resolvidas — Português</h4>

          <div class="question-item">
            <div class="q-text"><strong>Q1 (Vestibulinho 2019).</strong> No slogan "Você está no meio desse ambiente. E não no fim.", o segundo período usa zeugma. Assinale a alternativa que também usa zeugma:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> "Seu rosto imóvel logrou / uma expressão que ninguém chegou perto de imitar..."</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> "Como era dia de bacalhau, vovó mandou abrir três garrafas de vinho do Porto."</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">C</span> "Perante a morte empalidece e treme, / treme perante a Morte, empalidece."</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> "Vês?! Ninguém assistiu ao formidável / Enterro de tua última quimera."</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> "Viu uma lua no céu / Viu outra lua no mar."</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa C. "Treme perante a Morte, empalidece." — o verbo "treme" é omitido na segunda parte ("empalidece e [treme]"), e "empalidece" é omitido na primeira. Isso é zeugma: omissão de termos já expressos anteriormente.</div>
          </div>

          <div class="question-item">
            <div class="q-text"><strong>Q2 (Vestibulinho 2026).</strong> Na passagem "quando cresceu, ficou livre e acabou indo com o seu bando", a expressão "acabou indo" aponta:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> uma ação inacabada que é realizada recorrentemente.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> uma ação inacabada que se prolonga infinitamente.</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">C</span> uma ação finalizada que é enfatizada ao terminar.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> o início de uma ação que se realiza rapidamente.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> o desenvolvimento de uma ação que não se concretiza.</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa C. A locução "acabou + gerúndio" indica aspecto conclusivo com ênfase no término da ação. O auxiliar "acabar" expressa o fim de um processo (a capivara finalmente foi embora com o bando).</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     MATEMÁTICA
═══════════════════════════════════════ -->
<section class="subject-section mat" id="matematica">
  <div class="section-inner">
    <div class="section-header">
      <div class="section-icon">📐</div>
      <div class="section-title-block">
        <div class="section-label">Matéria 02</div>
        <h2>Matemática</h2>
        <p>Aritmética, álgebra, geometria, estatística e raciocínio lógico. As questões sempre partem de um contexto real e aplicado.</p>
      </div>
    </div>

    <div class="topic-grid">

      <!-- RAZÃO E PROPORÇÃO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">01</span>
          <h3>Razão, Proporção e Regra de Três</h3>
        </div>
        <p>Base de muitas questões do Vestibulinho, sempre com contexto prático.</p>
        <div class="formula-box">
          <span>Razão:</span> a/b (divisão entre duas grandezas)<br>
          <span>Proporção:</span> a/b = c/d → a·d = b·c (produto cruzado)<br>
          <span>Regra de três simples:</span><br>
          grandeza1 → grandeza2<br>
          valor1   →  x<br>
          x = (valor1 × grandeza2) / grandeza1
        </div>
        <div class="concept-box">
          <strong>Prova 2026 (Q.02):</strong>
          207 cães-guia ÷ 6.500.000 pessoas ≈ 1 para cada 31.400.
          Cálculo: 6.500.000 ÷ 207 ≈ 31.401 → alternativa C.
        </div>
        <div class="tip-box">Sempre verifique se a proporção é DIRETA (mais→mais) ou INVERSA (mais→menos). Se inversa, inverta um dos lados da razão.</div>
      </div>

      <!-- VELOCIDADE -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">02</span>
          <h3>Velocidade, Distância e Tempo</h3>
        </div>
        <p>Fórmula clássica aplicada em contextos variados.</p>
        <div class="formula-box">
          <span>v = Δd / Δt</span><br>
          v = velocidade média<br>
          Δd = distância percorrida<br>
          Δt = tempo gasto<br><br>
          <span>Atenção às unidades:</span><br>
          km/h → dividir km por hora<br>
          m/s  → dividir metros por segundo<br>
          Converter: 1 km/h = 1000/3600 m/s ≈ 0,278 m/s
        </div>
        <div class="concept-box">
          <strong>Prova 2024 (Q.40) — Andes:</strong>
          60 km em 10 dias → v = 60/10 = 6 km/dia → por hora (24h): 6/24 = 0,25 km/h. Resposta: E.
        </div>
        <div class="concept-box">
          <strong>Prova 2026 (Q.31) — Gnus:</strong>
          Manada: 240 km em 4 dias = 60 km/dia.
          Humanos: 240 km em 6 dias = 40 km/dia.
          Diferença: 60 − 40 = 20 km/dia → manada foi 20 km/dia mais rápida. Resposta: A.
        </div>
      </div>

      <!-- GEOMETRIA: ÁREA E VOLUME -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">03</span>
          <h3>Geometria: Áreas e Volumes</h3>
        </div>
        <p>Fórmulas de sólidos geométricos com aplicação prática.</p>
        <div class="formula-box">
          <span>Cilindro:</span> V = π · r² · h<br>
          <span>Cubo:</span> V = a³<br>
          <span>Esfera:</span> V = (4/3) · π · r³<br>
          <span>Cone:</span> V = (1/3) · π · r² · h<br>
          <span>Triângulo:</span> A = (base × altura) / 2<br>
          <span>Retângulo:</span> A = base × altura<br>
          <span>Círculo:</span> A = π · r²
        </div>
        <div class="concept-box">
          <strong>Prova 2018 (Q.16) — Cilindros nucleares:</strong>
          V₁ = π·6²·4 = 144π m³. Novo: r₂ = 3m, V₂ = 62,5% de 144π = 90π.
          h₂ = 90π / (π·9) = 10m. Resposta: B.
        </div>
        <div class="concept-box">
          <strong>Prova 2026 (Q.27) — Melanossomo cilíndrico:</strong>
          Diâmetro = 300nm → raio = 150nm; altura = 500nm.
          V = π · 150² · 500. Resposta: A.
        </div>
      </div>

      <!-- EQUAÇÕES DE 2º GRAU -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">04</span>
          <h3>Equações de 1º e 2º Grau</h3>
        </div>
        <p>Resolução de problemas que levam à montagem e resolução de equações.</p>
        <div class="formula-box">
          <span>Equação do 2º grau:</span> ax² + bx + c = 0<br>
          <span>Fórmula de Bhaskara:</span><br>
          Δ = b² − 4ac<br>
          x = (−b ± √Δ) / 2a
        </div>
        <div class="concept-box">
          <strong>Prova 2019 (Q.11) — Reserva Extrativista:</strong>
          Área = 4225 km². Comprimento = x + 100. Largura = x.
          x · (x + 100) = 4225 → x² + 100x − 4225 = 0. Resposta: C.
        </div>
        <div class="concept-box">
          <strong>Prova 2018 (Q.43) — Caminhão:</strong>
          Velocidade habitual = v, tempo habitual = t.
          v · t = 630 e (v+10)(t−4) = 630.
          Resolvendo: t = 18 horas. Resposta: E.
        </div>
      </div>

      <!-- SISTEMAS DE EQUAÇÕES -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">05</span>
          <h3>Sistemas de Equações</h3>
        </div>
        <p>Duas incógnitas, duas equações — método de substituição ou adição.</p>
        <div class="concept-box">
          <strong>Prova 2024 (Q.11) — Massa de neurônios e gliócitos:</strong>
          Cérebro: 16 neurônios·N + 61 gliócitos·G = 1250g<br>
          Cerebelo: 69 neurônios·N + 16 gliócitos·G = 150g<br>
          Sistema: { 16N + 61G = 1250 / 69N + 16G = 150 }. Resposta: C.
        </div>
        <div class="formula-box">
          <span>Método de substituição:</span><br>
          Isola uma variável em uma equação → substitui na outra.<br><br>
          <span>Método de adição (eliminação):</span><br>
          Multiplica equações por fatores que cancelam uma variável.
        </div>
        <div class="tip-box">Monte o sistema interpretando o problema com cuidado. Identifique as duas quantidades desconhecidas e as duas relações entre elas.</div>
      </div>

      <!-- ESTATÍSTICA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">06</span>
          <h3>Estatística: Média e Gráficos</h3>
        </div>
        <p>Cálculo de médias e leitura de gráficos são cobrados frequentemente.</p>
        <div class="formula-box">
          <span>Média aritmética simples:</span><br>
          M = (x₁ + x₂ + ... + xₙ) / n<br><br>
          <span>Gráfico de setor (pizza):</span><br>
          Percentual = (parte / total) × 100<br>
          Ângulo = (parte / total) × 360°
        </div>
        <div class="concept-box">
          <strong>Prova 2018 (Q.40) — Reciclagem de alumínio:</strong>
          Média = (96,5 + 91,5 + 98,2 + 98,0 + 98,3 + 97,9) / 6 = 580,4 / 6 ≈ 96,7%. Resposta: C.
        </div>
        <div class="concept-box">
          <strong>Prova 2026 (Q.03) — Gráfico de cães-guia:</strong>
          Total: 207. Labradores: 153/207 ≈ 74%. Golden: 16/207 ≈ 8%. Outras: 38/207 ≈ 18%.
          Resposta: D (Labradores 74%, Golden 8%, Outras 18%).
        </div>
      </div>

      <!-- NOTAÇÃO CIENTÍFICA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">07</span>
          <h3>Notação Científica</h3>
        </div>
        <p>Expressão de números muito grandes ou muito pequenos.</p>
        <div class="formula-box">
          <span>Forma:</span> a × 10ⁿ, onde 1 ≤ a < 10<br><br>
          <span>Exemplos:</span><br>
          2 000 000 000 = 2,0 × 10⁹<br>
          0,000 000 050 = 5,0 × 10⁻⁸<br>
          50 µT = 50 × 10⁻⁶ T = 5,0 × 10⁻⁵ T
        </div>
        <div class="concept-box">
          <strong>Prova 2026 (Q.19) — Ímã de geladeira:</strong>
          Campo da Terra: 50 µT = 50 × 10⁻⁶ T = 5 × 10⁻⁵ T.
          Ímã = 100× maior = 5 × 10⁻³ T. Resposta: E.
        </div>
        <div class="tip-box">Para mover o ponto decimal à direita, some ao expoente. Para mover à esquerda, subtraia. Lembre: 10⁻⁶ = micros (µ).</div>
      </div>

      <!-- TAXA DE LOTAÇÃO / REGRA PRÁTICA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">08</span>
          <h3>Problemas de Proporção Aplicada</h3>
        </div>
        <p>O Vestibulinho sempre cria problemas com contexto real usando proporções e fórmulas fornecidas.</p>
        <div class="concept-box">
          <strong>Prova 2026 (Q.43) — Taxa de Lotação:</strong>
          900 animais × 250 kg = 225.000 kg total.
          UAs = 225.000 / 450 = 500 UA.
          Taxa = 500 UA / 100 ha = 5,0 UA/ha. Resposta: B.
        </div>
        <div class="concept-box">
          <strong>Prova 2026 (Q.13) — Equoterapia:</strong>
          Dias: ter–sex = 4 dias. Cada cavalo: 3h/dia ÷ 0,5h = 6 sessões/dia.
          12 cavalos × 6 = 72 sessões/dia × 4 dias = 288 sessões/semana.
          Cada pessoa: 2 sessões → 288/2 = 144 pessoas. Resposta: A.
        </div>
        <div class="tip-box">Leia o enunciado com calma e extraia todos os dados. Faça um esquema antes de calcular. A fórmula geralmente é fornecida.</div>
      </div>

      <!-- EXERCÍCIOS RESOLVIDOS MATEMÁTICA -->
      <div class="topic-card full-width">
        <div class="quiz-section">
          <h4>🎯 Questões Resolvidas — Matemática</h4>

          <div class="question-item">
            <div class="q-text"><strong>Q1 (Vestibulinho 2018 Q.22).</strong> A Xplástico usa 6.000 toneladas de plástico para 20 bilhões de peças/ano. Os eco-copos representam 2% da produção. O número de toneladas que deixarão de ser usadas de 2018 a 2030 (13 anos) é:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> 10</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> 120</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">C</span> 1.320</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> 1.440</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> 1.560</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">2% de 6.000 ton = 120 ton/ano substituídas por bioplástico. De 2018 a 2030 = 11 anos (contando 2018 e 2030). 120 × 11 = 1.320 toneladas. Resposta: C.</div>
          </div>

          <div class="question-item">
            <div class="q-text"><strong>Q2 (Vestibulinho 2024 Q.18).</strong> Homem de 70 kg tem 60% de água = 42 L. Mulher com mesma massa tem no máximo 55% de água. Volume máximo para mulher de 70 kg:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> 36,4 L</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">B</span> 38,5 L</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">C</span> 42,0 L</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> 55,0 L</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> 70,0 L</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">55% de 70 kg = 0,55 × 70 = 38,5 kg = 38,5 L (1kg de água = 1L). Resposta: B.</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     BIOLOGIA
═══════════════════════════════════════ -->
<section class="subject-section bio" id="biologia">
  <div class="section-inner">
    <div class="section-header">
      <div class="section-icon">🧬</div>
      <div class="section-title-block">
        <div class="section-label">Matéria 03</div>
        <h2>Biologia</h2>
        <p>Corpo humano, genética, ecologia, evolução, saúde e biodiversidade. Área com altíssima frequência nas provas.</p>
      </div>
    </div>

    <div class="topic-grid">

      <!-- CORPO HUMANO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">01</span>
          <h3>Sistemas do Corpo Humano</h3>
        </div>
        <p>Questões cobram o funcionamento integrado dos sistemas corporais.</p>
        <table class="data-table">
          <tr><th>Sistema</th><th>Função principal</th><th>Cobrado em</th></tr>
          <tr><td>Digestório</td><td>Digestão e absorção de nutrientes</td><td>2024 Q.05</td></tr>
          <tr><td>Circulatório</td><td>Transporte de O₂, nutrientes, hormônios</td><td>2024 Q.38</td></tr>
          <tr><td>Respiratório</td><td>Trocas gasosas (O₂/CO₂)</td><td>2024 Q.38</td></tr>
          <tr><td>Nervoso</td><td>Coordenação, memória, aprendizado</td><td>2024 Q.06–Q.09</td></tr>
          <tr><td>Endócrino</td><td>Produção e regulação hormonal</td><td>2024 Q.42, Q.43</td></tr>
          <tr><td>Imunológico</td><td>Defesa contra agentes patogênicos</td><td>2024 Q.22</td></tr>
          <tr><td>Tegumentar</td><td>Proteção, regulação térmica</td><td>2024 Q.20</td></tr>
        </table>
      </div>

      <!-- DIGESTÃO DE LIPÍDIOS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">02</span>
          <h3>Digestão: Lipídios e Emulsificação</h3>
        </div>
        <p>Tema recorrente — compreender o papel dos sais biliares é essencial.</p>
        <div class="concept-box">
          <strong>Processo de digestão dos lipídios:</strong>
          Lipídios chegam ao duodeno → sais biliares realizam a EMULSIFICAÇÃO → agem como detergente, aumentando a superfície de contato → enzimas lipases conseguem agir → produtos absorvidos pelas células da mucosa intestinal.
        </div>
        <div class="concept-box">
          <strong>O que é emulsificação?</strong>
          Quebra das grandes gotículas de gordura em gotículas menores, SEM hidrólise química. NÃO produz aminoácidos (isso seria digestão de proteínas). NÃO é feita na boca.
        </div>
        <div class="exam-box">Prova 2024 (Q.05): emulsificação age como detergente, aumenta a superfície de contato e facilita a atuação das enzimas lipases. Resposta: E.</div>
      </div>

      <!-- NEURÔNIOS E CÉREBRO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">03</span>
          <h3>Sistema Nervoso: Neurônios e Encéfalo</h3>
        </div>
        <p>O encéfalo é dividido em cérebro, cerebelo e outras partes, cada um com características distintas.</p>
        <div class="two-col">
          <div>
            <div class="concept-box">
              <strong>Dados da prova 2024 (Q.10 e Q.11):</strong>
              Cérebro: 77 bilhões de células (16 neurônios + 61 gliócitos), 1250g.
              Cerebelo: 85 bilhões (69 neurônios + 16 gliócitos), 150g.
              Total encéfalo: > 100 bilhões de células.
            </div>
          </div>
          <div>
            <div class="concept-box">
              <strong>Neurônios × Gliócitos:</strong>
              Neurônios: transmitem impulsos nervosos.
              Gliócitos (células gliais): suporte físico e metabólico. O cerebelo tem MAIOR concentração de neurônios (69 bilhões).
            </div>
          </div>
        </div>
        <div class="tip-box">O cérebro é MAIOR em massa, mas o cerebelo tem MAIS neurônios (proporcionalmente). Atenção a essa distinção nas questões!</div>
      </div>

      <!-- GENÉTICA: ALBINISMO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">04</span>
          <h3>Genética: Herança e Alelos</h3>
        </div>
        <p>Compreender dominância e recessividade é fundamental.</p>
        <div class="concept-box">
          <strong>Albinismo — prova 2024 (Q.12):</strong>
          Característica recessiva (aa). Para ter albinismo, o indivíduo precisa de DOIS alelos recessivos.
          Pais que NÃO são albinos mas são HETEROZIGOTOS (Aa × Aa) podem ter filhos albinos (25% de chance).
        </div>
        <div class="formula-box">
          <span>Cruzamento Aa × Aa:</span><br>
          1/4 AA (normal, homozigoto dominante)<br>
          2/4 Aa (normal, heterozigoto — portador)<br>
          1/4 aa (albino)<br><br>
          <span>Proporção fenotípica:</span> 3 normais : 1 albino
        </div>
        <div class="tip-box">Homozigoto dominante (AA) ≠ heterozigoto (Aa), mas ambos têm fenótipo normal. Apenas o homozigoto recessivo (aa) manifesta a característica recessiva.</div>
      </div>

      <!-- ECOLOGIA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">05</span>
          <h3>Ecologia: Relações e Cadeias Alimentares</h3>
        </div>
        <p>Relações ecológicas, cadeias alimentares e impactos ambientais.</p>
        <table class="data-table">
          <tr><th>Relação</th><th>Espécies</th><th>Resultado</th></tr>
          <tr><td>Predatismo</td><td>Predador × Presa</td><td>+/−</td></tr>
          <tr><td>Parasitismo</td><td>Parasita × Hospedeiro</td><td>+/−</td></tr>
          <tr><td>Comensalismo</td><td>Comensal × Hospedeiro</td><td>+/0</td></tr>
          <tr><td>Inquilinismo</td><td>Inquilino × Hospedeiro</td><td>+/0 (só abrigo)</td></tr>
          <tr><td>Mutualismo/Simbiose</td><td>A × B</td><td>+/+</td></tr>
          <tr><td>Competição</td><td>Duas espécies</td><td>−/−</td></tr>
        </table>
        <div class="concept-box">
          <strong>Prova 2019 (Q.38) — Epífitas:</strong>
          Orquídeas, bromélias e samambaias vivem SOBRE outras plantas maiores usando-as como suporte para captar mais luz. Isso é INQUILINISMO: o inquilino se beneficia, o hospedeiro não é prejudicado.
        </div>
      </div>

      <!-- CICLOS BIOGEOQUÍMICOS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">06</span>
          <h3>Ciclos Biogeoquímicos</h3>
        </div>
        <p>O ciclo do carbono é o mais cobrado.</p>
        <div class="concept-box">
          <strong>Ciclo do Carbono — prova 2018 (Q.34):</strong>
          CO₂ atmosférico → FOTOSSÍNTESE → matéria orgânica (em seres autotróficos).
          Matéria orgânica → RESPIRAÇÃO/DECOMPOSIÇÃO → CO₂.
          No esquema da prova: seta 1 = fotossíntese (CO₂ → mat. orgânica); seta 2 = respiração (mat. orgânica → CO₂).
        </div>
        <div class="concept-box">
          <strong>O que retorna o carbono ao ambiente:</strong>
          Respiração dos seres vivos, decomposição por decompositores, combustão, fermentação.
        </div>
        <div class="exam-box">Prova 2018 (Q.35): "no ciclo do carbono, um dos processos que garantem o retorno do elemento dos organismos para o meio externo é a degradação da matéria orgânica pelos seres vivos". Resposta: C.</div>
      </div>

      <!-- DOENÇAS PARASITÁRIAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">07</span>
          <h3>Doenças Parasitárias e Prevenção</h3>
        </div>
        <p>Verminoses e doenças são tema recorrente — saiba causas, agentes e prevenção.</p>
        <table class="data-table">
          <tr><th>Doença</th><th>Agente</th><th>Transmissão</th><th>Prevenção</th></tr>
          <tr><td>Ascaridíase (lombriga)</td><td>Ascaris lumbricoides</td><td>Ingestão de ovos (água/alimento)</td><td>Higiene, saneamento</td></tr>
          <tr><td>Teníase (solitária)</td><td>Taenia solium/saginata</td><td>Carne contaminada mal cozida</td><td>Cozinhar bem a carne</td></tr>
          <tr><td>Ancilostomose (bicho-de-pé)</td><td>Ancylostoma</td><td>Larvas penetram pela pele</td><td>Andar calçado</td></tr>
          <tr><td>Amebíase</td><td>Entamoeba histolytica</td><td>Ingestão de cistos (água/alimento)</td><td>Higiene das mãos, água tratada</td></tr>
          <tr><td>Toxoplasmose</td><td>Toxoplasma gondii</td><td>Carne crua, fezes de gato</td><td>Cozinhar carne, higiene</td></tr>
          <tr><td>Dengue/Zika/Chikungunya</td><td>Vírus (Aedes aegypti)</td><td>Picada do mosquito</td><td>Eliminar água parada</td></tr>
        </table>
        <div class="exam-box">Prova 2026 (Q.45): ingestão de carne suína/bovina com cisticercos = TENÍASE, causada pela solitária. Resposta: B.</div>
      </div>

      <!-- BIODIVERSIDADE E ECOSSISTEMAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">08</span>
          <h3>Biodiversidade e Ecossistemas</h3>
        </div>
        <p>Biomas brasileiros, hotspots e conservação.</p>
        <div class="concept-box">
          <strong>Hotspot — prova 2019 (Q.21):</strong>
          Para ser hotspot: ≥1500 espécies endêmicas E ≤30% de vegetação original preservada.
          Mata Atlântica tem 75,88% desmatada → preservada: 24,12% → abaixo de 30% → É hotspot. Resposta: B.
        </div>
        <ul class="content-list">
          <li><span class="highlight">Amazônia:</span> maior diversidade de gimnospermas; maior bioma brasileiro.</li>
          <li><span class="highlight">Mata Atlântica:</span> hotspot de biodiversidade; muito desmatada.</li>
          <li><span class="highlight">Cerrado:</span> segunda maior área; ~900 espécies de aves, 40 endêmicas.</li>
          <li><span class="highlight">Caatinga:</span> exclusiva do Brasil; semiárido nordestino.</li>
          <li><span class="highlight">Pantanal:</span> menor área desmatada (15,43%); importante para aves migratórias.</li>
          <li><span class="highlight">Pampa:</span> campos sulinos.</li>
        </ul>
      </div>

      <!-- QUESTÕES RESOLVIDAS BIOLOGIA -->
      <div class="topic-card full-width">
        <div class="quiz-section">
          <h4>🎯 Questões Resolvidas — Biologia</h4>

          <div class="question-item">
            <div class="q-text"><strong>Q1 (Vestibulinho 2024 Q.01).</strong> Para alcançar o ideal de saúde descrito no texto, deve-se:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> Evitar refeições balanceadas pois deixam o corpo com baixa imunidade.</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">B</span> Realizar prática regular de atividades físicas, que auxiliam no controle da hipertensão e previnem osteopenia.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">C</span> Realizar acompanhamento médico pois impede o aparecimento de doenças graves.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> Ingerir quantidade reduzida de água para remover toxinas.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> Utilizar dispositivos eletrônicos antes de dormir pois promovem sono tranquilo.</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa B. Atividade física regular controla hipertensão, reduz risco de diabetes, melhora flexibilidade e previne osteopenia. As demais alternativas contêm afirmações incorretas do ponto de vista médico-científico.</div>
          </div>

          <div class="question-item">
            <div class="q-text"><strong>Q2 (Vestibulinho 2019 Q.38).</strong> Orquídeas e bromélias que vivem sobre plantas maiores para obter mais luz — esse tipo de relação ecológica é:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> Simbiose</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> Predação</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">C</span> Inquilinismo</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> Canibalismo</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> Parasitismo</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa C. O inquilinismo é uma relação em que uma espécie se beneficia ao usar outra como abrigo ou suporte, sem causar dano ao hospedeiro (+/0). As epífitas usam o tronco da planta maior apenas como suporte, não retirando nutrientes dela.</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     QUÍMICA
═══════════════════════════════════════ -->
<section class="subject-section qui" id="quimica">
  <div class="section-inner">
    <div class="section-header">
      <div class="section-icon">⚗️</div>
      <div class="section-title-block">
        <div class="section-label">Matéria 04</div>
        <h2>Química</h2>
        <p>Átomos, tabela periódica, substâncias, reações químicas, pH e radioatividade. Sempre com aplicação no cotidiano.</p>
      </div>
    </div>

    <div class="topic-grid">

      <!-- ÁTOMO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">01</span>
          <h3>Estrutura Atômica</h3>
        </div>
        <p>O átomo é formado por prótons, elétrons e nêutrons. Saber contar cada um é cobrado diretamente.</p>
        <div class="formula-box">
          <span>Número Atômico (Z):</span> = número de prótons<br>
          Em átomo neutro: Z = número de elétrons<br><br>
          <span>Número de Massa (A):</span> = prótons + nêutrons<br>
          Nêutrons = A − Z<br><br>
          <span>Representação:</span>  ᴬ_Z X<br>
          Ex: ⁵⁶₂₆Fe → Z=26, A=56, nêutrons=56−26=30
        </div>
        <div class="exam-box">Prova 2024 (Q.21) — Ferro ⁵⁶₂₆Fe: prótons=26, elétrons=26, nêutrons=56−26=30. Resposta: A.</div>
        <div class="exam-box">Prova 2026 (Q.35) — ⁵⁶₂₆Fe: número de massa = 56. Resposta: A.</div>
        <div class="tip-box">Íons têm elétrons diferentes dos prótons. Íon positivo (cátion) perdeu elétrons; íon negativo (ânion) ganhou elétrons.</div>
      </div>

      <!-- SUBSTÂNCIAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">02</span>
          <h3>Classificação de Substâncias</h3>
        </div>
        <p>Distinguir substâncias simples, compostas e misturas é base da química.</p>
        <div class="concept-box">
          <strong>Substância simples:</strong> formada por um único elemento químico. Ex: O₂ (oxigênio), H₂ (hidrogênio), N₂, Fe (ferro puro).
        </div>
        <div class="concept-box">
          <strong>Substância composta:</strong> formada por dois ou mais elementos químicos diferentes, em proporção definida. Ex: H₂O (água: H e O), NaCl (sal), CaCl₂ (cloreto de cálcio), C₆H₁₂O₆ (glicose).
        </div>
        <div class="concept-box">
          <strong>Mistura:</strong> dois ou mais componentes sem proporção fixa. Ex: água + óleo, ar atmosférico.
        </div>
        <div class="exam-box">Prova 2026 (Q.16): O₂ = substância simples (1 elemento: oxigênio). C₆H₁₂O₆ = substância composta (3 elementos: C, H, O). Resposta: B.</div>
        <div class="exam-box">Prova 2018 (Q.06): KCl (cloreto de potássio) = substância composta (K + Cl). Resposta: A.</div>
      </div>

      <!-- pH E ÁCIDO-BASE -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">03</span>
          <h3>pH: Ácidos, Bases e Indicadores</h3>
        </div>
        <p>Escala de pH de 0 a 14, onde 7 é neutro.</p>
        <div class="formula-box">
          <span>pH &lt; 7:</span> solução ÁCIDA (mais H⁺)<br>
          <span>pH = 7:</span> solução NEUTRA<br>
          <span>pH &gt; 7:</span> solução BÁSICA (mais OH⁻)<br><br>
          Quanto menor o pH, mais ácida (mais H⁺).
        </div>
        <div class="concept-box">
          <strong>Indicadores ácido-base:</strong>
          Mudam de cor conforme o pH. O indicador citado na prova 2026: vermelho (pH ácido), verde (neutro), azul (básico).
        </div>
        <div class="exam-box">Prova 2026 (Q.30): suco gástrico pH=2 → ácido → indicador fica VERMELHO. Resposta: D.</div>
        <ul class="content-list">
          <li>Suco gástrico: pH ≈ 1,5–3,5 (muito ácido)</li>
          <li>Sangue humano: pH ≈ 7,4 (levemente básico)</li>
          <li>Água pura: pH = 7 (neutro)</li>
          <li>Leite: pH ≈ 6,5 (levemente ácido)</li>
          <li>Sabão: pH ≈ 9–11 (básico)</li>
        </ul>
      </div>

      <!-- REAÇÕES QUÍMICAS E ESTEQUIOMETRIA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">04</span>
          <h3>Reações Químicas e Estequiometria</h3>
        </div>
        <p>Proporções em reações químicas — regra de três com massas molares.</p>
        <div class="formula-box">
          <span>Fotossíntese:</span><br>
          6CO₂ + 6H₂O → C₆H₁₂O₆ + 6O₂<br>
          44g    18g      180g      32g<br><br>
          <span>Proporção:</span> 66g CO₂ → ?g glicose<br>
          44g CO₂ → 180g glicose<br>
          66g CO₂ → x = (66 × 180) / 44 = <span>270g</span>
        </div>
        <div class="exam-box">Prova 2019 (Q.03): 66g CO₂ absorvidos; como 44g → 30g de glicose na proporção usada: x = 66×30/44 = 45g. Resposta: E.</div>
        <div class="tip-box">Na estequiometria, sempre monte uma regra de três respeitando as proporções da equação balanceada. As massas devem ser proporcionais.</div>
      </div>

      <!-- RADIOATIVIDADE -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">05</span>
          <h3>Radioatividade</h3>
        </div>
        <p>Tipos de radiação e suas aplicações médicas.</p>
        <div class="concept-box">
          <strong>Partícula Alfa (α) — prova 2024 (Q.44):</strong>
          Representada como ⁴₂α (ou ⁴₂He). Z=2, A=4.
          Contém 2 PRÓTONS e 2 NÊUTRONS. (NÃO contém elétrons!)
        </div>
        <div class="concept-box">
          <strong>Decaimento alfa:</strong>
          ¹³¹₅₃I → ⁴₂α + ¹²⁷₅₁Sb
          Verifica-se: 53=2+51 (Z); 131=4+127 (A). Conservação de massa e carga.
        </div>
        <table class="data-table">
          <tr><th>Radiação</th><th>Composição</th><th>Penetração</th></tr>
          <tr><td>Alfa (α)</td><td>2p⁺ + 2n° (núcleo de He)</td><td>Baixa (papel detém)</td></tr>
          <tr><td>Beta (β)</td><td>Elétron (e⁻)</td><td>Média (alumínio detém)</td></tr>
          <tr><td>Gama (γ)</td><td>Onda eletromagnética</td><td>Alta (chumbo detém)</td></tr>
        </table>
      </div>

      <!-- COMPOSTOS ORGÂNICOS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">06</span>
          <h3>Química Orgânica Básica</h3>
        </div>
        <p>Fórmulas moleculares, grupos funcionais e identificação de compostos.</p>
        <div class="concept-box">
          <strong>Fórmula molecular a partir da estrutural — prova 2026 (Q.36):</strong>
          Feromônio do percevejo escuro: conta-se os átomos na fórmula estrutural.
          CH₃–CH₂–CH(OH)–CH(CH₃)–CO–CH₂–CH₃ → C₈H₁₆O₂.
        </div>
        <div class="concept-box">
          <strong>Como contar átomos na fórmula estrutural:</strong>
          1. Conte cada "C" (carbono) incluindo os das ramificações.
          2. Conte cada "H" (hidrogênio) — lembre que cada carbono precisa de 4 ligações.
          3. Conte O, N, S, etc.
        </div>
        <div class="concept-box">
          <strong>Álcool × Ácido carboxílico:</strong>
          Álcool: –OH (hidroxila). Ácido: –COOH (carboxila). Éster: –COO–.
        </div>
      </div>

      <!-- QUESTÕES RESOLVIDAS QUÍMICA -->
      <div class="topic-card full-width">
        <div class="quiz-section">
          <h4>🎯 Questões Resolvidas — Química</h4>

          <div class="question-item">
            <div class="q-text"><strong>Q1 (Vestibulinho 2019 Q.08).</strong> O cloreto de cálcio, subproduto de uma reação química, tem íons Ca²⁺ e Cl¹⁻. Qual a fórmula correta?</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">A</span> CaCl₂</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> Ca₂Cl₂</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">C</span> Ca₂Cl</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> Ca₂Cl₃</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> CaCl</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa A. Para neutralidade elétrica: Ca²⁺ precisa de 2 cargas negativas → 2 Cl¹⁻. Fórmula: CaCl₂. Regra: carga do cátion = índice do ânion; carga do ânion = índice do cátion.</div>
          </div>

          <div class="question-item">
            <div class="q-text"><strong>Q2 (Vestibulinho 2026 Q.16).</strong> O oxigênio (O₂) e a glicose (C₆H₁₂O₆) são classificados, respectivamente, como:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> substância composta e substância simples</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">B</span> substância simples e substância composta</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">C</span> substância composta e substância composta</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> substância composta e mistura</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> substância simples e mistura</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa B. O₂ é substância SIMPLES: formada por apenas um elemento (oxigênio). C₆H₁₂O₆ é substância COMPOSTA: formada por três elementos diferentes (carbono, hidrogênio, oxigênio) em proporção definida.</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     FÍSICA
═══════════════════════════════════════ -->
<section class="subject-section fis" id="fisica">
  <div class="section-inner">
    <div class="section-header">
      <div class="section-icon">⚡</div>
      <div class="section-title-block">
        <div class="section-label">Matéria 05</div>
        <h2>Física</h2>
        <p>Mecânica, óptica, termologia, ondas e eletromagnetismo. Sempre com fórmulas aplicadas a situações do dia a dia.</p>
      </div>
    </div>

    <div class="topic-grid">

      <!-- PRESSÃO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">01</span>
          <h3>Pressão</h3>
        </div>
        <p>A pressão é força por área — um dos tópicos mais cobrados da física no Vestibulinho.</p>
        <div class="formula-box">
          <span>P = F / A</span><br>
          P = pressão (Pascal = N/m² ou atm)<br>
          F = força (Newtons)<br>
          A = área (m²)<br><br>
          <span>Relação:</span> F constante → P e A são inversamente proporcionais.
          Se A ↓ então P ↑ (faca afiada = menos área = mais pressão)
        </div>
        <div class="exam-box">Prova 2024 (Q.14): faca afiada → diminuição da área → aumento da pressão → I=inversamente, II=diminuição, III=maior. Resposta: C.</div>
        <div class="concept-box">
          <strong>Pressão atmosférica e profundidade — prova 2019 (Q.34):</strong>
          Ao nível do mar: 1 atm. A cada 10m submerso: +1 atm.
          Fossa das Marianas: 11.000m → 11.000/10 = 1.100 atm + 1 atm (atmosférica) = 1.101 atm. Resposta: D.
        </div>
        <div class="concept-box">
          <strong>Camelos e pressão sobre areia — prova 2026 (Q.40):</strong>
          Cascos largos = maior área = menor pressão → não afundam na areia. Princípio: P = F/A.
        </div>
      </div>

      <!-- ÓPTICA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">02</span>
          <h3>Óptica: Lentes e Defeitos de Visão</h3>
        </div>
        <p>Lentes convergentes e divergentes, miopia e hipermetropia.</p>
        <div class="concept-box">
          <strong>Miopia — prova 2024 (Q.34):</strong>
          Imagem forma-se ANTES da retina. Dificuldade em ver de longe.
          Correção: lente CÔNCAVA (divergente), que afasta os raios, empurrando a imagem para trás até a retina.
        </div>
        <div class="concept-box">
          <strong>Hipermetropia:</strong>
          Imagem forma-se ATRÁS da retina. Dificuldade em ver de perto.
          Correção: lente CONVEXA (convergente), que aproxima os raios.
        </div>
        <table class="data-table">
          <tr><th>Defeito</th><th>Imagem forma em</th><th>Dificuldade</th><th>Lente corretora</th></tr>
          <tr><td>Miopia</td><td>Antes da retina</td><td>Visão de longe</td><td>Côncava (divergente)</td></tr>
          <tr><td>Hipermetropia</td><td>Após a retina</td><td>Visão de perto</td><td>Convexa (convergente)</td></tr>
          <tr><td>Astigmatismo</td><td>Pontos difusos</td><td>Visão distorcida</td><td>Cilíndrica</td></tr>
          <tr><td>Presbiopia</td><td>Perda elasticidade</td><td>Idosos: perto</td><td>Convexa (bifocal)</td></tr>
        </table>
        <div class="exam-box">Prova 2024 (Q.36): lentes para corrigir miopia = divergentes (bicôncavas, plano-côncavas e convexo-côncavas). Resposta: E.</div>
      </div>

      <!-- CALOR E TEMPERATURA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">03</span>
          <h3>Calor: Transmissão e Escalas</h3>
        </div>
        <p>Três formas de propagação do calor e conversão entre escalas.</p>
        <div class="concept-box">
          <strong>Formas de propagação — prova 2018 (Q.38):</strong>
          CONVECÇÃO: calor levado pelo movimento de fluidos (gases/líquidos) — fumaça subindo.
          CONDUÇÃO: calor passa de partícula a partícula (sólidos) — panela aquecendo cabo.
          IRRADIAÇÃO: calor transmitido por ondas eletromagnéticas (sem meio) — sol aquecendo objetos.
        </div>
        <div class="formula-box">
          <span>Conversão Celsius ↔ Fahrenheit:</span><br>
          θC/5 = (θF − 32)/9<br><br>
          Ex: 50°C → θF = (50×9/5) + 32 = 90 + 32 = 122°F<br>
          Ex: 60°C → θF = (60×9/5) + 32 = 108 + 32 = 140°F
        </div>
        <div class="exam-box">Prova 2018 (Q.36): 50°C = 122°F e 60°C = 140°F. Resposta: D.</div>
      </div>

      <!-- ONDAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">04</span>
          <h3>Ondas: Som e Eletromagnéticas</h3>
        </div>
        <p>Fórmula fundamental das ondas e espectro eletromagnético.</p>
        <div class="formula-box">
          <span>v = λ · f</span><br>
          v = velocidade de propagação (m/s)<br>
          λ = comprimento de onda (m)<br>
          f = frequência (Hz)<br><br>
          No ar: velocidade do som ≈ 340 m/s<br>
          Luz e ondas EM: c ≈ 3×10⁸ m/s
        </div>
        <div class="concept-box">
          <strong>Morcegos — prova 2019 (Q.03):</strong>
          Ouvem de 1.000 Hz a 120.000 Hz. Maior comprimento de onda → menor frequência (1.000 Hz).
          λ = v/f = 340/1000 = 0,34 m. Resposta: B.
        </div>
        <div class="concept-box">
          <strong>Espectro eletromagnético (menor → maior λ, maior → menor energia):</strong>
          Raios Gama → Raios X → UV → Luz visível → Infravermelho → Micro-ondas → Rádio
        </div>
        <div class="exam-box">Prova 2019 (Q.41): Chernobyl emitiu ondas de menor comprimento = maior energia = raios gama. Para esterilizar mosquitos machos: raios gama. Resposta: E.</div>
      </div>

      <!-- ENERGIA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">05</span>
          <h3>Energia: Potência e Fontes Renováveis</h3>
        </div>
        <p>Potência, energia e tipos de fontes energéticas.</p>
        <div class="formula-box">
          <span>Potência:</span> P = E / t<br>
          P = potência (Watts, W)<br>
          E = energia (Joules, J)<br>
          t = tempo (segundos, s)<br><br>
          <span>1 kWh</span> = 1000 W × 3600 s = 3,6 × 10⁶ J
        </div>
        <div class="concept-box">
          <strong>Prova 2018 (Q.32) — LED vs. incandescente:</strong>
          LED 10W em 8h = 80 Wh. Incandescente 75W em t:
          75 × t = 80 → t ≈ 1,07h ≈ 1 hora (aproximado). Resposta: A.
        </div>
        <div class="concept-box">
          <strong>Fontes renováveis — prova 2018 (Q.30):</strong>
          RENOVÁVEIS: etanol (cana), energia eólica, hidrelétrica, solar, biomassa.
          NÃO renováveis: petróleo, carvão mineral, gás natural, energia nuclear.
          Resposta: B (etanol + eólica).
        </div>
      </div>

      <!-- FORÇAS E MÁQUINAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">06</span>
          <h3>Máquinas Simples: Alavancas e Polias</h3>
        </div>
        <p>Máquinas que facilitam o trabalho aplicando princípios físicos.</p>
        <div class="concept-box">
          <strong>Alavanca — prova 2024 (Q.30):</strong>
          Barra rígida apoiada em ponto fixo (fulcro). Músculos e ossos funcionam como alavancas (articulação = fulcro).
          Exercício com halteres para bíceps é um exemplo de alavanca de 3ª classe.
        </div>
        <div class="concept-box">
          <strong>Polias — prova 2018 (Q.29):</strong>
          Polia maior (roda d'água) ligada por correia à polia menor (dínamo).
          Correia não desliza → ambas têm MESMA velocidade LINEAR na correia.
          Portanto: polia maior gira mais DEVAGAR que a menor (demora mais para dar uma volta).
          Ambas giram no MESMO sentido (correia conecta exteriormente). Resposta: D.
        </div>
        <div class="tip-box">Numa polia com correia: velocidade linear igual → a maior (raio maior) tem menor velocidade angular → leva mais tempo para dar uma volta.</div>
      </div>

      <!-- QUESTÕES RESOLVIDAS FÍSICA -->
      <div class="topic-card full-width">
        <div class="quiz-section">
          <h4>🎯 Questões Resolvidas — Física</h4>

          <div class="question-item">
            <div class="q-text"><strong>Q1 (Vestibulinho 2024 Q.20).</strong> Em dia quente, o mecanismo de sudorese envolve a _______ da água do suor. A água _______ calor do corpo e _______ a temperatura corpórea.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> condensação — absorve — aumenta</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> condensação — libera — diminui</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">C</span> evaporação — absorve — aumenta</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">D</span> evaporação — absorve — diminui</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> evaporação — libera — aumenta</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa D. A água do suor sofre EVAPORAÇÃO (muda de líquido para vapor). A evaporação é endotérmica: absorve calor do corpo para acontecer. Portanto, o corpo perde calor e sua temperatura DIMINUI. Isso é o mecanismo de termorregulação por sudorese.</div>
          </div>

          <div class="question-item">
            <div class="q-text"><strong>Q2 (Vestibulinho 2018 Q.25).</strong> Dois protótipos filtram água. O segundo tem área maior. Aplicando a MESMA força no segundo, a pressão na água é:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> menor que p, demorando menos tempo</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> menor que p, mesmo tempo</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">C</span> menor que p, demorando mais tempo</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> maior que p, demorando mais tempo</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> maior que p, demorando menos tempo</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa C. P=F/A. Mesma força, área maior → pressão MENOR que p. Com pressão menor, a água passa mais devagar pelo filtro → demora MAIS tempo. Apesar de ter mais orifícios, a pressão menor compensa, resultando em mais tempo total de filtragem.</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     HISTÓRIA
═══════════════════════════════════════ -->
<section class="subject-section his" id="historia">
  <div class="section-inner">
    <div class="section-header">
      <div class="section-icon">🏛️</div>
      <div class="section-title-block">
        <div class="section-label">Matéria 06</div>
        <h2>História</h2>
        <p>Brasil e mundo — da Antiguidade ao século XXI. As provas pedem contextualização de eventos com causas e consequências.</p>
      </div>
    </div>

    <div class="topic-grid">

      <!-- RENASCIMENTO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">01</span>
          <h3>Renascimento</h3>
        </div>
        <p>Movimento cultural, artístico e científico que surgiu na Europa entre os séculos XIV e XVI.</p>
        <div class="concept-box">
          <strong>Características principais:</strong>
          Humanismo (o ser humano no centro); Antropocentrismo (em oposição ao teocentrismo medieval); valorização da razão e da ciência; retomada da herança greco-romana; investigação experimental.
        </div>
        <div class="concept-box">
          <strong>Prova 2024 (Q.02) — Leonardo da Vinci:</strong>
          Desenhos anatômicos → investigação experimental (dissecação de cadáveres) → desenvolvimento do conhecimento da anatomia humana e da medicina. Resposta: C.
        </div>
        <ul class="content-list">
          <li>Leonardo da Vinci: arte + ciência (anatomia, engenharia)</li>
          <li>Michelangelo: escultura e pintura (Davi, Sistina)</li>
          <li>Nicolau Copérnico: heliocentrismo</li>
          <li>Galileu Galilei: telescópio, física experimental</li>
          <li>Origem: Itália (Florença, Veneza)</li>
        </ul>
      </div>

      <!-- IMPERIALISMO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">02</span>
          <h3>Imperialismo e Neocolonialismo</h3>
        </div>
        <p>Expansão europeia sobre a Ásia e África nos séculos XIX e XX.</p>
        <div class="concept-box">
          <strong>Características — prova 2024 (Q.32):</strong>
          Dominação econômica, política e cultural de nações europeias industrializadas sobre Ásia e África. Justificada por teorias raciais como o darwinismo social e o racismo científico (século XIX). Resposta: C.
        </div>
        <div class="concept-box">
          <strong>Prova 2026 (Q.46) — Zoológicos:</strong>
          Surgimento dos zoológicos ligado ao Imperialismo dos séculos XVIII–XIX: impérios levavam animais exóticos das colônias para exibição na Europa — simbolizando dominação territorial e controle da natureza. Esse processo = neocolonialismo / política de expansão territorial. Resposta: C.
        </div>
      </div>

      <!-- SEGUNDA GUERRA MUNDIAL -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">03</span>
          <h3>Segunda Guerra Mundial</h3>
        </div>
        <p>Conflito global (1939–1945) com impactos devastadores na humanidade.</p>
        <div class="concept-box">
          <strong>Bomba de Hiroshima — prova 2018 (Q.15):</strong>
          6 de agosto de 1945 — EUA bombeiam Hiroshima, Japão. Foi um dos ÚLTIMOS eventos da Segunda Guerra Mundial (Europa já havia se rendido — Alemanha/Hitler). Japão se rendeu dias depois. Resposta: D.
        </div>
        <div class="concept-box">
          <strong>Efeitos da radiação — prova 2024 (Q.45):</strong>
          Bombardeios atômicos de 1945 = Segunda Guerra Mundial. Crianças expostas desenvolveram leucemia e múltiplos tipos de câncer. Resposta: D.
        </div>
        <ul class="content-list">
          <li>Início: 1939 (invasão da Polônia pela Alemanha)</li>
          <li>Aliados: EUA, URSS, Reino Unido, França, etc.</li>
          <li>Eixo: Alemanha, Itália, Japão</li>
          <li>Fim na Europa: maio de 1945 (rendição alemã)</li>
          <li>Fim no Pacífico: agosto/setembro de 1945 (bombas atômicas)</li>
        </ul>
      </div>

      <!-- GUERRA FRIA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">04</span>
          <h3>Guerra Fria e Corrida Espacial</h3>
        </div>
        <p>Disputa ideológica entre EUA (capitalismo) e URSS (socialismo) após a Segunda Guerra.</p>
        <div class="concept-box">
          <strong>Prova 2026 (Q.07) — Corrida espacial:</strong>
          URSS lançou a cadela Laika no Sputnik 2 em 1957. Entre 1948 e 1961, URSS e EUA enviaram 65 animais ao espaço. Yuri Gagarin foi o primeiro humano no espaço (1961). Esse período = GUERRA FRIA. Resposta: E.
        </div>
        <ul class="content-list">
          <li>1947–1991: período da Guerra Fria</li>
          <li>1957: Sputnik 1 (URSS) — primeiro satélite artificial</li>
          <li>1961: Yuri Gagarin (URSS) — primeiro humano no espaço</li>
          <li>1969: Neil Armstrong (EUA) — primeiro humano na Lua</li>
          <li>1989: Queda do Muro de Berlim</li>
          <li>1991: Dissolução da URSS — fim da Guerra Fria</li>
        </ul>
      </div>

      <!-- DITADURA MILITAR BRASILEIRA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">05</span>
          <h3>Ditadura Militar Brasileira</h3>
        </div>
        <p>Período de 1964 a 1985 no Brasil, marcado por repressão e crescimento econômico.</p>
        <div class="concept-box">
          <strong>Governo Médici (1969–1974) — prova 2018 (Q.24):</strong>
          "Milagre econômico": crescimento acelerado, industrialização, obras de infraestrutura (Transamazônica, Itaipu). Mas também: endurecimento da repressão (AI-5), censura, torturas, desaparecimentos. Cubatão = industrialização acelerada → mais poluída do mundo na década de 1980. Resposta: C.
        </div>
        <div class="concept-box">
          <strong>Criação da Petrobras — prova 2018 (Q.20):</strong>
          1953, governo Getúlio Vargas: política nacional-desenvolvimentista (industrialização, estatização, criação de empresas estatais em setores estratégicos). Resposta: E.
        </div>
      </div>

      <!-- COLONIZAÇÃO E MERCANTILISMO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">06</span>
          <h3>Colonização das Américas e Mercantilismo</h3>
        </div>
        <p>A colonização ibérica e as políticas econômicas que a impulsionaram.</p>
        <div class="concept-box">
          <strong>Mercantilismo — prova 2018 (Q.44):</strong>
          Política econômica praticada pelas nações europeias a partir do séc. XVI. Caracterizada por: acumulação de metais (ouro/prata), medidas protecionistas, controle rígido das colônias (Pacto Colonial). Justifica a busca por ouro em Minas Gerais e prata em Potosí. Resposta: E.
        </div>
        <div class="concept-box">
          <strong>Floresta do Congo — prova 2019 (Q.04):</strong>
          Região da África subsaariana com grande biodiversidade. Foi origem de GRANDE PARTE dos africanos escravizados trazidos para a América do Sul durante o período colonial. Resposta: E.
        </div>
      </div>

      <!-- IDADE MÉDIA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">07</span>
          <h3>Idade Média</h3>
        </div>
        <p>Período histórico europeu (séc. V ao XV) marcado pelo teocentrismo e feudalismo.</p>
        <div class="concept-box">
          <strong>Visão medieval de mundo — prova 2019 (Q.49):</strong>
          O referencial medieval era o sagrado/religioso (teocentrismo). Medo da natureza, das epidemias e das colheitas ruins levou à busca de explicações no sobrenatural. A sensação de insegurança diante do inesperado fez com que essas sociedades buscassem a solução no sobrenatural. Resposta: D.
        </div>
        <div class="concept-box">
          <strong>Inovações agrícolas medievais (séc. X–XII) — prova 2018 (Q.05):</strong>
          Rotação trienal de culturas + arado de ferro + ferradura + novas formas de atrelagem de animais. Esses avanços aumentaram a produtividade agrícola. Resposta: C.
        </div>
        <div class="concept-box">
          <strong>Mapas medievais — prova 2026 (Q.41):</strong>
          Mapas com monstros marinhos = visão baseada em medo e superstição. Substituída gradualmente pelo olhar científico com as expedições marítimas e o desenvolvimento da biologia marinha. Resposta: B.
        </div>
      </div>

      <!-- QUESTÕES RESOLVIDAS HISTÓRIA -->
      <div class="topic-card full-width">
        <div class="quiz-section">
          <h4>🎯 Questões Resolvidas — História</h4>

          <div class="question-item">
            <div class="q-text"><strong>Q1 (Vestibulinho 2024 Q.32).</strong> O Imperialismo é definido como conquista e exploração econômica/social de nações industrializadas europeias sobre África e Ásia. Esse movimento tem como principal característica:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> a reivindicação de melhores condições de vida afetadas pela crise econômica de 2008.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> a polarização do mundo em dois blocos ideológicos na Guerra Fria.</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">C</span> a utilização ideológica de teorias raciais como o racismo científico e o darwinismo social do séc. XIX.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> a formação das monarquias nacionais como consequência da Guerra dos Cem Anos.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> a oposição da França à política ambiental de países em desenvolvimento no séc. XXI.</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa C. O Imperialismo (séc. XIX) usou as teorias de racismo científico e darwinismo social para justificar a dominação colonial. Essas teorias pseudocientíficas afirmavam que europeus eram "superiores" e tinham o dever de "civilizar" outros povos — legitimando ideologicamente a exploração colonial.</div>
          </div>

          <div class="question-item">
            <div class="q-text"><strong>Q2 (Vestibulinho 2019 Q.35).</strong> O Jardim Botânico do Rio de Janeiro foi criado em 1808. Sobre o contexto de criação, é correto mencionar:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> o reinado de D. Pedro II, responsável por iniciativas científicas na capital.</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">B</span> a transferência da Corte de Portugal para o Brasil, quando o Rio tornou-se capital do império português.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">C</span> a Independência do Brasil, quando o Rio se tornou capital da República.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> a fundação do Rio de Janeiro, planejada para ser nova capital.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> a proclamação da República e a transferência da capital para Brasília.</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa B. Em 1808, com a invasão napoleônica, a família real portuguesa transferiu-se para o Brasil. O Rio de Janeiro tornou-se sede do Império português. D. João VI fundou o Jardim Botânico para aclimatar espécies úteis vindas das colônias. D. Pedro II governou de 1841–1889 — décadas depois.</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     GEOGRAFIA
═══════════════════════════════════════ -->
<section class="subject-section geo" id="geografia">
  <div class="section-inner">
    <div class="section-header">
      <div class="section-icon">🌍</div>
      <div class="section-title-block">
        <div class="section-label">Matéria 07</div>
        <h2>Geografia</h2>
        <p>Brasil e mundo — espaço geográfico, biomas, urbanização, clima, relevo e questões ambientais.</p>
      </div>
    </div>

    <div class="topic-grid">

      <!-- ESPAÇO GEOGRÁFICO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">01</span>
          <h3>Espaço Geográfico</h3>
        </div>
        <p>Conceito fundamental de Milton Santos, muito cobrado nas provas.</p>
        <div class="concept-box">
          <strong>Milton Santos — prova 2024 (Q.31):</strong>
          Espaço geográfico = "conjunto indissociável do qual participam, de um lado, certo arranjo de objetos geográficos, objetos naturais e objetos sociais; e, de outro, a vida que os preenche e os anima, ou seja, a sociedade em movimento."
          → É o RESULTADO da relação entre o ser humano e o meio no qual ele habita e do qual também faz parte. Resposta: C.
        </div>
        <div class="tip-box">O espaço geográfico NÃO é puramente natural (sem sociedade), NÃO é puramente social (sem natureza). É a RELAÇÃO entre ambos.</div>
      </div>

      <!-- BIOMAS BRASILEIROS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">02</span>
          <h3>Biomas e Domínios Morfoclimáticos</h3>
        </div>
        <p>Características e localização dos principais biomas brasileiros.</p>
        <table class="data-table">
          <tr><th>Bioma</th><th>Clima</th><th>Localização</th><th>Característica</th></tr>
          <tr><td>Amazônia</td><td>Equatorial úmido</td><td>Norte</td><td>Maior biodiversidade</td></tr>
          <tr><td>Cerrado</td><td>Tropical</td><td>Centro-Oeste</td><td>Savana brasileira</td></tr>
          <tr><td>Mata Atlântica</td><td>Tropical/Subtropical</td><td>Costa leste</td><td>Hotspot — muito desmatada</td></tr>
          <tr><td>Caatinga</td><td>Semiárido</td><td>Nordeste</td><td>Exclusiva do Brasil</td></tr>
          <tr><td>Pampa</td><td>Subtropical</td><td>Rio Grande do Sul</td><td>Campos gaúchos</td></tr>
          <tr><td>Pantanal</td><td>Tropical úmido</td><td>Mato Grosso do Sul</td><td>Maior planície alagável</td></tr>
        </table>
        <div class="exam-box">Prova 2022/2026: Mata Atlântica no Nordeste (Sergipe) → cerrado em Goiás = deslocamento para o noroeste. Prova 2019: bioma da Reserva Mamirauá (Amazônia) = vegetação heterogênea com árvores altas em ambiente úmido. Resposta: D.</div>
      </div>

      <!-- CORRENTES MARÍTIMAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">03</span>
          <h3>Correntes Marítimas</h3>
        </div>
        <p>Movimentos de grandes massas de água que influenciam o clima costeiro.</p>
        <div class="concept-box">
          <strong>Corrente do Peru (Humboldt) — prova 2026 (Q.26):</strong>
          Corrente FRIA que corre ao longo do litoral do Pacífico, na costa oeste da América do Sul (Chile, Peru, Equador). Causa ressurgência (upwelling) → traz nutrientes das profundezas → peixes em abundância → aves migratórias (guano). Também inibe chuvas → deserto costeiro (Atacama).
        </div>
        <table class="data-table">
          <tr><th>Corrente</th><th>Temperatura</th><th>Localização</th><th>Efeito</th></tr>
          <tr><td>Corrente do Brasil</td><td>Quente</td><td>Costa atlântica brasileira</td><td>Chuvoso, tropical</td></tr>
          <tr><td>Corrente do Peru</td><td>Fria</td><td>Costa Pacífico Sul-americana</td><td>Ressurgência, deserto</td></tr>
          <tr><td>Corrente de Benguela</td><td>Fria</td><td>Costa oeste africana</td><td>Deserto Namibe</td></tr>
          <tr><td>Corrente do Golfo</td><td>Quente</td><td>Atlântico Norte</td><td>Clima ameno Europa</td></tr>
        </table>
      </div>

      <!-- DERIVA CONTINENTAL -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">04</span>
          <h3>Teoria da Deriva Continental</h3>
        </div>
        <p>Wegener propôs que os continentes já estiveram unidos e se separaram ao longo do tempo geológico.</p>
        <div class="concept-box">
          <strong>Prova 2026 (Q.17) — Argumento paleontológico:</strong>
          Existência de FÓSSEIS IDÊNTICOS encontrados em continentes hoje afastados (ex: Brasil e África). Se os continentes sempre foram separados, como animais terrestres poderiam ter distribuição idêntica em dois lados do Atlântico? Isso prova que estavam unidos. Resposta: C.
        </div>
        <ul class="content-list">
          <li><span class="highlight">Pangeia:</span> supercontinente único, ~225 milhões de anos atrás</li>
          <li><span class="highlight">Pantalassa:</span> oceano único que rodeava a Pangeia</li>
          <li><span class="highlight">Evidências:</span> fósseis, similaridade de rochas, encaixe dos continentes, magnetismo</li>
          <li><span class="highlight">Mecanismo atual:</span> teoria das placas tectônicas (Wegener não soube explicar o mecanismo)</li>
        </ul>
      </div>

      <!-- TERREMOTOS E PLACAS TECTÔNICAS -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">05</span>
          <h3>Terremotos e Placas Tectônicas</h3>
        </div>
        <p>Sismos naturais e induzidos pela atividade humana.</p>
        <div class="concept-box">
          <strong>Prova 2024 (Q.37):</strong>
          Terremotos naturais ocorrem principalmente ao longo de FALHAS GEOLÓGICAS, especialmente onde diferentes placas tectônicas se tocam (bordas de placas). Terremotos INDUZIDOS pela atividade humana podem ocorrer LONGE das extremidades das placas. São causados por mineração, reservatórios, injeção de fluidos no subsolo. Resposta: A.
        </div>
        <div class="concept-box">
          <strong>Forças endógenas:</strong>
          Forças internas da Terra (vulcanismo, tectonismo, terremotos).
          Forças exógenas: erosão, sedimentação (externas).
        </div>
      </div>

      <!-- URBANIZAÇÃO E GENTRIFICAÇÃO -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">06</span>
          <h3>Urbanização: Problemas e Processos</h3>
        </div>
        <p>Problemas urbanos contemporâneos.</p>
        <div class="concept-box">
          <strong>Gentrificação — prova 2024 (Q.46):</strong>
          Processo de valorização de áreas urbanas antigas/populares → chegada de população de maior renda → deslocamento da população de menor renda. Ocorre em áreas URBANAS. Originalmente descrito em bairros operários de Londres. Resposta: B.
        </div>
        <div class="concept-box">
          <strong>"Homem-caranguejo" de Josué de Castro — prova 2024 (Q.47):</strong>
          Conceito do sociólogo/geógrafo Josué de Castro sobre a situação de pobreza extrema dos habitantes dos mangues do rio Capibaribe (Recife, PE). Fatores sociais e econômicos empurram o homem para condição de miséria semelhante à do caranguejo nos mangues. Resposta: D.
        </div>
      </div>

      <!-- CICLO DA ÁGUA E CLIMA -->
      <div class="topic-card">
        <div class="topic-card-header">
          <span class="topic-num">07</span>
          <h3>Ciclo da Água e Clima</h3>
        </div>
        <p>Processos físicos do ciclo hidrológico e fenômenos climáticos.</p>
        <div class="concept-box">
          <strong>Prova 2026 (Q.32) — Migração de gnus:</strong>
          A migração ocorre em função do ciclo da água (busca por água e pastagens).
          O ciclo hidrológico é movido pela ENERGIA SOLAR: evaporação (sol aquece a água) e condensação (vapor resfria e forma chuva). Resposta: E.
        </div>
        <div class="concept-box">
          <strong>Equinócio — prova 2026 (Q.42):</strong>
          Equinócio: momento em que o eixo da Terra fica perpendicular à linha Sol–Terra. Dia e noite têm ~12h cada. NÃO é responsável por ondas de calor — não concentra radiação especialmente sobre o Brasil. A fake news era incorreta. Resposta: C.
        </div>
        <div class="concept-box">
          <strong>Estações do ano — prova 2019 (Q.14):</strong>
          Quando a imagem mostra Dia Polar no Norte e Noite Polar no Sul → solstício de verão no hemisférico Norte = solstício de inverno no hemisfério Sul. Brasil (Mata Atlântica) = INVERNO; Hemisfério Norte = VERÃO. Resposta: C.
        </div>
      </div>

      <!-- QUESTÕES RESOLVIDAS GEOGRAFIA -->
      <div class="topic-card full-width">
        <div class="quiz-section">
          <h4>🎯 Questões Resolvidas — Geografia</h4>

          <div class="question-item">
            <div class="q-text"><strong>Q1 (Vestibulinho 2024 Q.37).</strong> Com base no texto sobre terremotos, é correto afirmar que os terremotos:</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">A</span> são causados tanto por forças endógenas, quanto pelas atividades humanas.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> ocasionados por fenômenos naturais não ocorrem mais no planeta Terra.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">C</span> provocados pelos seres humanos não alcançam magnitudes elevadas.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> estimulados por agentes bióticos não ocorrem há mais de 150 anos.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> ocorrem unicamente em áreas de separação de placas tectônicas.</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa A. O texto afirma claramente que terremotos podem ser causados tanto por forças naturais (endógenas — placas tectônicas, falhas geológicas) quanto por atividades humanas (mineração, reservatórios, injeção de fluidos). Os terremotos induzidos chegam a magnitudes elevadas e ocorrem longe das bordas de placas.</div>
          </div>

          <div class="question-item">
            <div class="q-text"><strong>Q2 (Vestibulinho 2024 Q.41).</strong> Para garantir desenvolvimento sustentável e inclusivo, de acordo com o texto, é correto afirmar que:</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">A</span> a destruição da Amazônia é fundamental para o Brasil entrar no grupo dos países mais ricos.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">B</span> o desenvolvimento econômico não se mistura com preservação ambiental, pois são processos antagônicos.</div>
            <div class="option" onclick="reveal(this,'correct')"><span class="opt-letter">C</span> é preciso que ocorram políticas econômicas sólidas, aliadas à eliminação da pobreza, para se alcançar o desenvolvimento sustentável e inclusivo.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">D</span> a emergência climática ocorre fora dos limites da Amazônia, não afetando este bioma.</div>
            <div class="option" onclick="reveal(this,'wrong')"><span class="opt-letter">E</span> é necessário conscientizar o poder público para facilitar a instalação de indústrias no coração da Amazônia.</div>
            <button class="show-answer-btn" onclick="toggleAnswer(this)">Ver Resolução</button>
            <div class="answer-reveal">Alternativa C. O texto afirma que para alcançar desenvolvimento sustentável e inclusivo é preciso "políticas sociais e econômicas consistentes" com foco em "erradicar a pobreza, reduzir a desigualdade social e criar oportunidades para todos". A destruição da Amazônia, ao contrário, levaria ao isolamento internacional.</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>Apostila Preparatória <strong>Vestibulinho ETEC</strong> · Conteúdo baseado nas provas de 2018, 2019, 2024, 2025 e 2026</p>
  <p style="margin-top:8px; font-size: 12px;">Estude com consistência · Revise os temas mais cobrados · Pratique com questões reais</p>
  <a href="#top" class="back-top">↑ Voltar ao início</a>
</footer>

<script>
function reveal(el, type) {
  // Remove previous states in same question
  const siblings = el.parentElement.querySelectorAll('.option');
  siblings.forEach(s => { s.classList.remove('correct','wrong'); });
  el.classList.add(type);
}

function toggleAnswer(btn) {
  const reveal = btn.nextElementSibling;
  if (reveal.classList.contains('show')) {
    reveal.classList.remove('show');
    btn.textContent = 'Ver Resolução';
  } else {
    reveal.classList.add('show');
    btn.textContent = 'Ocultar Resolução';
  }
}

// Active nav highlighting on scroll
const sections = document.querySelectorAll('.subject-section');
const navTabs = document.querySelectorAll('.nav-tab');

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const id = entry.target.id;
      navTabs.forEach(tab => {
        tab.classList.toggle('active', tab.getAttribute('href') === '#' + id);
      });
    }
  });
}, { threshold: 0.2 });

sections.forEach(s => observer.observe(s));
</script>
</body>
</html>
