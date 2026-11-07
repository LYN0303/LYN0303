<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#080d0e" />
  <meta name="description" content="Portfolio de Data Engineer — pipelines, plateformes de données et analytics engineering." />
  <title>TON NOM — Data Engineer</title>
  <style>
    :root {
      --bg: #080d0e;
      --panel: #0d1516;
      --panel-2: #101b1c;
      --line: #244344;
      --text: #e4f0ed;
      --muted: #91a7a1;
      --green: #39e6bd;
      --gold: #e6bd58;
      --blue: #8fc9ff;
      --mono: "SFMono-Regular", Consolas, "Liberation Mono", monospace;
      --sans: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0; color: var(--text); background:
        radial-gradient(circle at 82% 8%, rgba(27, 111, 94, .16), transparent 27rem),
        linear-gradient(180deg, #080d0e, #090f10 65%, #070b0c);
      font-family: var(--sans); line-height: 1.6;
      overflow-x: hidden;
    }
    /* Ambient animated lights */
    .ambient {
      position: fixed; inset: 0; z-index: -1; overflow: hidden;
      pointer-events: none; isolation: isolate;
    }
    .light {
      position: absolute; width: 360px; height: 360px; border-radius: 50%;
      filter: blur(75px); opacity: .20; mix-blend-mode: screen;
      animation: drift 18s ease-in-out infinite alternate;
    }
    .light.one { background: #00e6b2; top: -150px; left: -130px; }
    .light.two { background: #087e91; right: -170px; top: 28%; animation-duration: 23s; animation-delay: -7s; }
    .light.three { background: #b58a32; width: 260px; height: 260px; left: 24%; bottom: -170px; opacity: .13; animation-duration: 21s; animation-delay: -11s; }
    .light.four { background: #16b8a0; width: 190px; height: 190px; right: 18%; top: 68%; opacity: .14; animation-duration: 16s; animation-delay: -4s; }
    @keyframes drift {
      0% { transform: translate3d(0, 0, 0) scale(.88); }
      50% { transform: translate3d(90px, 65px, 0) scale(1.13); }
      100% { transform: translate3d(-45px, 125px, 0) scale(.96); }
    }
    .frame { position: relative; }
    .frame::before {
      content: ""; position: absolute; inset: 0; pointer-events: none;
      background: linear-gradient(115deg, transparent 15%, rgba(57,230,189,.045) 48%, transparent 68%);
      background-size: 220% 100%; animation: lightSweep 12s linear infinite;
    }
    @keyframes lightSweep {
      0% { background-position: 180% 0; }
      100% { background-position: -40% 0; }
    }
    .orb i { animation: pulse 2.8s ease-in-out infinite; }
    @keyframes pulse {
      0%, 100% { opacity: .7; transform: scale(.8); box-shadow: 0 0 12px 3px rgba(57,230,189,.35); }
      50% { opacity: 1; transform: scale(1.35); box-shadow: 0 0 25px 9px rgba(57,230,189,.65); }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { animation-duration: .01ms !important; animation-iteration-count: 1 !important; scroll-behavior: auto !important; }
    }
    a { color: inherit; text-decoration: none; }
    a:hover { color: var(--green); }
    .shell { width: min(1040px, calc(100% - 32px)); margin: 34px auto 60px; }
    .topline { height: 2px; background: linear-gradient(90deg, var(--green), #6d8f78, var(--gold)); }
    .frame { border: 1px solid #344647; border-top: 0; padding: clamp(20px, 4vw, 42px); background: rgba(8, 14, 15, .88); box-shadow: 0 22px 80px rgba(0,0,0,.28); }
    .eyebrow { color: var(--green); font: 700 12px var(--mono); letter-spacing: .2em; text-transform: uppercase; }
    .hero { display: grid; grid-template-columns: 1fr 190px; gap: 28px; align-items: center; padding: 8px 0 34px; }
    h1 { margin: 8px 0 4px; font-size: clamp(30px, 6vw, 52px); line-height: 1.05; letter-spacing: -.055em; }
    .role { color: var(--gold); font: 12px var(--mono); letter-spacing: .08em; text-transform: uppercase; }
    .intro { max-width: 650px; color: #b5c7c1; font-size: 14px; margin: 18px 0; }
    .meta { display: flex; flex-wrap: wrap; gap: 8px 16px; color: var(--muted); font: 11px var(--mono); }
    .meta span::before { content: "› "; color: var(--green); }
    .orb { width: 160px; height: 160px; justify-self: center; position: relative; border: 1px solid rgba(57,230,189,.32); border-radius: 50%; background: repeating-radial-gradient(circle, transparent 0 17px, rgba(57,230,189,.11) 18px 19px), linear-gradient(90deg, transparent 49.5%, rgba(57,230,189,.2) 50%, transparent 50.5%), linear-gradient(0deg, transparent 49.5%, rgba(57,230,189,.2) 50%, transparent 50.5%); box-shadow: 0 0 35px rgba(57,230,189,.08), inset 0 0 35px rgba(57,230,189,.06); }
    .orb::before, .orb::after { content: ""; position: absolute; inset: 22px 0; border: 1px solid rgba(57,230,189,.2); border-radius: 50%; transform: rotate(55deg); }
    .orb::after { transform: rotate(-55deg); }
    .orb i { position: absolute; width: 7px; height: 7px; border-radius: 50%; background: var(--green); top: 48%; left: 48%; box-shadow: 0 0 18px 5px rgba(57,230,189,.55); }
    section { margin-top: 30px; }
    .section-head { display: flex; justify-content: space-between; gap: 12px; align-items: baseline; border-bottom: 1px solid var(--line); padding-bottom: 9px; margin-bottom: 12px; }
    h2 { margin: 0; color: var(--green); font: 700 12px var(--mono); letter-spacing: .17em; text-transform: uppercase; }
    .count { color: #718781; font: 10px var(--mono); }
    .stack { display: grid; gap: 8px; }
    .item { display: grid; grid-template-columns: 1fr auto; gap: 14px; align-items: center; border: 1px solid #1d3737; border-left: 2px solid var(--green); background: linear-gradient(90deg, rgba(16,35,34,.72), rgba(11,18,19,.72)); padding: 11px 13px; }
    .item strong { display: block; font: 600 12px var(--mono); color: #dcebe6; }
    .item p { margin: 3px 0 0; color: var(--muted); font-size: 11px; }
    .tag { color: var(--gold); font: 10px var(--mono); white-space: nowrap; }
    .grid { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 10px; }
    .card { min-height: 120px; padding: 15px; border: 1px solid #284443; background: linear-gradient(145deg, #101c1d, #0b1213); }
    .card h3 { margin: 0 0 8px; color: #e7f4ef; font: 700 12px var(--mono); }
    .card p { margin: 0 0 12px; color: var(--muted); font-size: 12px; }
    .chips { display: flex; flex-wrap: wrap; gap: 6px; }
    .chip { border: 1px solid #2b514c; color: var(--green); padding: 3px 7px; font: 9px var(--mono); }
    .gold-card { border-left: 2px solid var(--gold); }
    .gold-card .chip { border-color: #66552e; color: var(--gold); }
    .links { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 18px; }
    .links a { border: 1px solid #34504d; padding: 7px 10px; color: #c9d9d3; font: 10px var(--mono); }
    .links a:hover { border-color: var(--green); }
    footer { display: flex; justify-content: space-between; gap: 10px; color: #718781; font: 10px var(--mono); padding-top: 24px; margin-top: 34px; border-top: 1px solid var(--line); }
    .hint { color: #738b84; font: 10px var(--mono); margin-top: 18px; }
    @media (max-width: 650px) {
      .hero { grid-template-columns: 1fr; }
      .orb { width: 112px; height: 112px; justify-self: start; grid-row: 1; }
      .grid { grid-template-columns: 1fr; }
      .item { grid-template-columns: 1fr; gap: 5px; }
      .tag { white-space: normal; }
      footer { flex-direction: column; }
    }
  </style>
</head>
<body>
  <div class="ambient" aria-hidden="true">
    <span class="light one"></span>
    <span class="light two"></span>
    <span class="light three"></span>
    <span class="light four"></span>
  </div>
  <main class="shell">
    <div class="topline"></div>
    <div class="frame">
      <header class="hero">
        <div>
          <div class="eyebrow">Data Engineering · Data Platform · Analytics</div>
          <h1>Lynda MERNICHE</h1>
          <div class="role"> <h3 style="font-size: 20px;">Data Engineer</h3></div>
          
          <div class="meta">
            <span>Basée à Paris, France</span>
            <span>Disponible pour échanger</span>
            <span>FR / EN</span>
          </div>
          <nav class="links" aria-label="Liens">
            <a href="https://merniche.alwaysdata.net/portfolio/index.html">Portfolio ↗</a>
            <a href="https://www.linkedin.com/in/lynda-merniche/">LINKEDIN ↗</a>
            <a href="mailto:lyndamerniche@gmail.com">EMAIL ↗</a>
            <a href="#projects">About↓</a>
          </nav>
        </div>
        <div class="orb" aria-hidden="true"><i></i></div>
      </header>

      <section id="expertise">
        <div class="section-head"><h2>Domaines d'expertise</h2><span class="count">01 / EXPERTISE</span></div>
        <div class="stack">
          <article class="item"><div><strong>Data Engineering</strong><p>Conception de pipelines batch et streaming, ingestion, transformation et orchestration.</p></div><span class="tag">CORE</span></article>
          <article class="item"><div><strong>Data Warehousing & Modeling</strong><p>Modélisation dimensionnelle, tables analytiques, qualité et gouvernance des données.</p></div><span class="tag">ANALYTICS</span></article>
          <article class="item"><div><strong>Cloud Architectures</strong><p>stockage cloud, optimisation </p></div><span class="tag">PLATFORM</span></article>
          <article class="item"><div><strong>Data Quality & Gouvernance</strong><p>Tests, contrôles, monitoring, traçabilité et fiabilité des flux de données.</p></div><span class="tag">RELIABILITY</span></article>
        </div>
      </section>

      <section id="stack">
        <div class="section-head"><h2>Stack technique</h2><span class="count">02 / TOOLBOX</span></div>
        <div class="grid">
          <article class="card"><h3>LANGUAGES</h3><p>Langages utilisés pour construire et transformer les données.</p><div class="chips"><span class="chip">Python</span><span class="chip">SQL</span><span class="chip">PySpark</span><span class="chip">Bash</span></div></article>
          <article class="card"><h3>PROCESSING</h3><p>Traitement et transformation des données.</p><div class="chips"><span class="chip">Apache Spark</span><span class="chip">Pandas</span></div></article>
          <article class="card"><h3>ORCHESTRATION</h3><p>Planification et automatisation des workflows.</p><div class="chips"><span class="chip">Airflow</span><span class="chip">Docker</span></div></article>
          <article class="card"><h3>STORAGE & CLOUD</h3><p>Stockage, entrepôts et infrastructure.</p><div class="chips"><span class="chip">Azure</span><span class="chip">PostgreSQL</span><span class="chip">Snowflake</span></div></article>
          <article class="card"><h3>STREAMING</h3><p>Flux de données et architectures événementielles.</p><div class="chips"><span class="chip">Spark Streaming</span></div></article>
          <article class="card"><h3>DEV & DELIVERY</h3><p>Versioning, tests et déploiement.</p><div class="chips"><span class="chip">Git</span><span class="chip">GitHub Actions</span><span class="chip">CI/CD</span></div></article>
        </div>
      </section>

      <section id="approach">
        <div class="section-head"><h2>Ma méthode</h2><span class="count">03 / PRINCIPLES</span></div>
        <div class="stack">
          <article class="item"><div><strong>01 — Understand</strong><p>Comprendre les besoins métier, les sources et les contraintes de données.</p></div><span class="tag">DISCOVERY</span></article>
          <article class="item"><div><strong>02 — Design</strong><p>Choisir une architecture simple, robuste, documentée et adaptée au besoin.</p></div><span class="tag">ARCHITECTURE</span></article>
          <article class="item"><div><strong>03 — Build & Validate</strong><p>Développer, tester, monitorer et améliorer en continu.</p></div><span class="tag">DELIVERY</span></article>
        </div>
      </section>

     
      <footer><span>© <span id="year"></span> Lynda MERNICHE · DATA ENGINEER</span></footer>
    </div>
  </main>
  <script>document.getElementById("year").textContent = new Date().getFullYear();</script>
</body>
</html>
