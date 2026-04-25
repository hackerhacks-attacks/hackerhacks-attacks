<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Professional security research portfolio focused on secure systems, detection engineering, security tooling, and technical research artifacts." />
  <title>Security Research Portfolio</title>

  <style>
    :root {
      --bg: #070a0d;
      --bg-elevated: #0b1115;
      --panel: rgba(15, 22, 27, 0.86);
      --panel-strong: rgba(18, 27, 33, 0.96);
      --border: rgba(190, 215, 218, 0.16);
      --border-strong: rgba(190, 215, 218, 0.30);
      --text: #f3f7f8;
      --muted: #9aa8ac;
      --dim: #6e7b80;
      --accent: #9ddfe4;
      --accent-strong: #c9fbff;
      --accent-soft: rgba(157, 223, 228, 0.11);
      --success: #9ee6b6;
      --warning: #d7bd7a;
      --shadow: rgba(0, 0, 0, 0.48);
      --max-width: 1160px;
      --radius-lg: 32px;
      --radius-md: 22px;
      --radius-sm: 14px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      min-height: 100vh;
      color: var(--text);
      background:
        radial-gradient(circle at 16% 10%, rgba(157, 223, 228, 0.10), transparent 30%),
        radial-gradient(circle at 88% 12%, rgba(158, 230, 182, 0.06), transparent 24%),
        linear-gradient(180deg, #070a0d 0%, #091216 44%, #06080a 100%);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      line-height: 1.5;
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      background-image:
        linear-gradient(rgba(190, 215, 218, 0.026) 1px, transparent 1px),
        linear-gradient(90deg, rgba(190, 215, 218, 0.026) 1px, transparent 1px);
      background-size: 76px 76px;
      mask-image: linear-gradient(to bottom, transparent, black 12%, black 78%, transparent);
      z-index: 0;
    }

    body::after {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      background: radial-gradient(circle at center, transparent 0%, rgba(0, 0, 0, 0.46) 100%);
      z-index: 1;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .page {
      width: min(var(--max-width), calc(100% - 42px));
      margin: 0 auto;
      padding: 28px 0 76px;
      position: relative;
      z-index: 2;
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 22px;
      padding: 12px 0 28px;
      color: var(--muted);
      font-size: 14px;
    }

    .brand {
      display: inline-flex;
      align-items: center;
      gap: 12px;
      color: var(--text);
      font-weight: 750;
      letter-spacing: -0.03em;
    }

    .brand-mark {
      width: 36px;
      height: 36px;
      border-radius: 13px;
      display: grid;
      place-items: center;
      border: 1px solid var(--border-strong);
      color: var(--accent);
      background: var(--accent-soft);
      box-shadow: 0 0 34px rgba(157, 223, 228, 0.06);
      font-weight: 800;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 28px;
    }

    .nav-links a {
      transition: color 180ms ease;
    }

    .nav-links a:hover {
      color: var(--accent-strong);
    }

    .nav-pill {
      border: 1px solid var(--border);
      color: var(--accent-strong);
      background: rgba(157, 223, 228, 0.045);
      border-radius: 999px;
      padding: 8px 13px;
      font-size: 12px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    .hero {
      min-height: 660px;
      display: grid;
      grid-template-columns: 1.05fr 0.95fr;
      gap: 36px;
      align-items: center;
      position: relative;
      overflow: hidden;
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      background:
        linear-gradient(120deg, rgba(7, 10, 13, 0.98), rgba(13, 25, 31, 0.92)),
        radial-gradient(circle at 76% 44%, rgba(157, 223, 228, 0.11), transparent 32%);
      box-shadow: 0 38px 108px var(--shadow);
      padding: clamp(34px, 6vw, 74px);
    }

    .hero::before {
      content: "";
      position: absolute;
      right: -260px;
      top: 130px;
      width: 940px;
      height: 380px;
      background: repeating-radial-gradient(ellipse at center, rgba(157, 223, 228, 0.075) 0 1px, transparent 2px 18px);
      opacity: 0.38;
      transform: rotate(-9deg);
      pointer-events: none;
    }

    .hero-copy,
    .overview-card {
      position: relative;
      z-index: 1;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 26px;
      color: var(--muted);
      font-size: 12px;
      letter-spacing: 0.14em;
      text-transform: uppercase;
    }

    .eyebrow::before {
      content: "";
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: var(--success);
      box-shadow: 0 0 16px rgba(158, 230, 182, 0.48);
    }

    h1 {
      max-width: 820px;
      margin-bottom: 24px;
      font-size: clamp(48px, 7.2vw, 102px);
      line-height: 0.95;
      letter-spacing: -0.075em;
      font-weight: 850;
    }

    h1 span {
      color: var(--accent-strong);
    }

    .subtitle {
      max-width: 720px;
      color: #f0f6f7;
      font-size: clamp(20px, 2.1vw, 28px);
      line-height: 1.28;
      letter-spacing: -0.035em;
    }

    .summary {
      max-width: 660px;
      margin-top: 20px;
      color: var(--muted);
      font-size: 15px;
      line-height: 1.82;
    }

    .actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 34px;
    }

    .button {
      min-height: 48px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border: 1px solid var(--border-strong);
      border-radius: 999px;
      background: rgba(157, 223, 228, 0.07);
      color: var(--accent-strong);
      padding: 0 20px;
      font-size: 14px;
      font-weight: 720;
      transition: transform 180ms ease, border-color 180ms ease, background 180ms ease;
    }

    .button:hover {
      transform: translateY(-1px);
      border-color: rgba(201, 251, 255, 0.55);
      background: rgba(157, 223, 228, 0.10);
    }

    .button.primary {
      border-color: transparent;
      background: linear-gradient(135deg, var(--accent), #e9ffff);
      color: #061012;
      box-shadow: 0 18px 42px rgba(157, 223, 228, 0.13);
    }

    .overview-card {
      overflow: hidden;
      border: 1px solid var(--border);
      border-radius: 28px;
      background: rgba(9, 16, 19, 0.78);
      backdrop-filter: blur(18px);
      box-shadow: 0 28px 78px rgba(0, 0, 0, 0.34), inset 0 0 42px rgba(157, 223, 228, 0.025);
    }

    .overview-top {
      height: 56px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid var(--border);
      padding: 0 20px;
      color: var(--muted);
      font-size: 12px;
      letter-spacing: 0.11em;
      text-transform: uppercase;
    }

    .dots {
      display: flex;
      gap: 7px;
    }

    .dot {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: var(--dim);
    }

    .dot:nth-child(2) {
      background: var(--accent);
    }

    .dot:nth-child(3) {
      background: var(--success);
    }

    .overview-body {
      padding: 20px;
    }

    .metrics {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
    }

    .metric,
    .panel {
      border: 1px solid rgba(190, 215, 218, 0.13);
      border-radius: 18px;
      background: rgba(255, 255, 255, 0.024);
      padding: 18px;
    }

    .metric span,
    .panel-title {
      color: var(--muted);
      font-size: 11px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .metric strong {
      display: block;
      margin-top: 12px;
      color: var(--text);
      font-size: 29px;
      letter-spacing: -0.06em;
    }

    .metric small {
      display: block;
      margin-top: 8px;
      color: var(--accent-strong);
      font-size: 12px;
    }

    .panel {
      margin-top: 12px;
    }

    .review-list {
      margin-top: 15px;
      display: grid;
      gap: 10px;
    }

    .review-item {
      display: flex;
      justify-content: space-between;
      gap: 16px;
      border-top: 1px solid rgba(190, 215, 218, 0.08);
      padding-top: 10px;
      color: var(--muted);
      font-size: 13px;
    }

    .review-item b {
      color: #eef7f7;
      font-weight: 620;
    }

    .review-item em {
      color: var(--accent-strong);
      font-style: normal;
    }

    .section-head {
      display: flex;
      align-items: end;
      justify-content: space-between;
      gap: 24px;
      margin: 52px 0 18px;
    }

    .section-head h2 {
      font-size: clamp(32px, 4vw, 54px);
      line-height: 1;
      letter-spacing: -0.065em;
    }

    .section-head p {
      max-width: 530px;
      color: var(--muted);
      font-size: 14px;
      line-height: 1.66;
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
    }

    .card {
      min-height: 252px;
      border: 1px solid var(--border);
      border-radius: 28px;
      background: var(--panel);
      box-shadow: 0 24px 66px rgba(0, 0, 0, 0.25);
      padding: 28px;
    }

    .num {
      width: 44px;
      height: 44px;
      display: grid;
      place-items: center;
      margin-bottom: 24px;
      border: 1px solid var(--border-strong);
      border-radius: 15px;
      color: var(--accent-strong);
      background: rgba(157, 223, 228, 0.07);
      font-size: 13px;
      font-weight: 800;
    }

    .card h3,
    .work h3 {
      margin-bottom: 12px;
      font-size: 22px;
      letter-spacing: -0.045em;
    }

    .card p,
    .work p {
      color: var(--muted);
      font-size: 14px;
      line-height: 1.76;
    }

    .work-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 18px;
    }

    .work {
      border: 1px solid var(--border);
      border-radius: 24px;
      background: rgba(12, 20, 23, 0.78);
      padding: 24px;
    }

    .tag {
      display: inline-flex;
      margin-bottom: 15px;
      border: 1px solid rgba(190, 215, 218, 0.14);
      border-radius: 999px;
      background: rgba(157, 223, 228, 0.045);
      color: var(--accent-strong);
      padding: 6px 10px;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.10em;
    }

    .methodology {
      margin-top: 22px;
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      align-items: center;
      gap: 38px;
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      background:
        linear-gradient(110deg, rgba(157, 223, 228, 0.08), transparent 46%),
        rgba(9, 16, 19, 0.88);
      box-shadow: 0 28px 82px rgba(0, 0, 0, 0.30);
      padding: clamp(34px, 6vw, 72px);
    }

    .methodology h2 {
      font-size: clamp(40px, 5.8vw, 76px);
      line-height: 0.96;
      letter-spacing: -0.08em;
    }

    .principle-list {
      display: grid;
      gap: 12px;
    }

    .principle {
      border: 1px solid rgba(190, 215, 218, 0.13);
      border-radius: 18px;
      background: rgba(255, 255, 255, 0.026);
      color: #eff7f7;
      padding: 18px 20px;
      font-size: 16px;
    }

    .contact {
      margin-top: 22px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      border: 1px solid var(--border);
      border-radius: 28px;
      background: var(--panel-strong);
      padding: 28px;
    }

    .contact h2 {
      margin-bottom: 8px;
      font-size: 28px;
      letter-spacing: -0.05em;
    }

    .contact p {
      color: var(--muted);
      font-size: 14px;
      line-height: 1.7;
    }

    footer {
      display: flex;
      justify-content: space-between;
      gap: 18px;
      padding: 26px 4px 0;
      color: var(--dim);
      font-size: 13px;
    }

    @media (max-width: 1020px) {
      .hero {
        grid-template-columns: 1fr;
        min-height: auto;
      }

      .cards,
      .work-grid {
        grid-template-columns: 1fr;
      }

      .methodology {
        grid-template-columns: 1fr;
      }

      .nav-links {
        display: none;
      }

      .section-head {
        display: block;
      }

      .section-head p {
        margin-top: 10px;
      }

      .contact {
        flex-direction: column;
        align-items: flex-start;
      }
    }

    @media (max-width: 560px) {
      .page {
        width: min(var(--max-width), calc(100% - 20px));
      }

      .hero {
        border-radius: 24px;
        padding: 24px;
      }

      .metrics {
        grid-template-columns: 1fr;
      }

      .nav-pill {
        display: none;
      }

      footer {
        flex-direction: column;
      }
    }
  </style>
</head>

<body>
  <main class="page">
    <nav class="nav" aria-label="Primary navigation">
      <a class="brand" href="#top" aria-label="Go to top">
        <span class="brand-mark">∴</span>
        <span>Security Research Portfolio</span>
      </a>

      <div class="nav-links">
        <a href="#focus">Focus</a>
        <a href="#work">Work</a>
        <a href="#methodology">Methodology</a>
        <a href="#contact">Contact</a>
      </div>

      <div class="nav-pill">privacy-conscious public profile</div>
    </nav>

    <section class="hero" id="top">
      <div class="hero-copy">
        <div class="eyebrow">independent security research</div>
        <h1>Security engineering, research, and <span>resilient systems.</span></h1>
        <p class="subtitle">A professional portfolio for secure systems work, security research, detection logic, and technical artifacts.</p>
        <p class="summary">This site is intentionally identity-light and evidence-focused. It is designed for employers and collaborators who want to review technical judgment, project quality, methodology, and documented work without unnecessary personal exposure.</p>

        <div class="actions">
          <a class="button primary" href="#work">View Selected Work</a>
          <a class="button" href="#methodology">Review Methodology</a>
        </div>
      </div>

      <aside class="overview-card" aria-label="Portfolio overview">
        <div class="overview-top">
          <div class="dots" aria-hidden="true">
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
          </div>
          <span>professional overview</span>
        </div>

        <div class="overview-body">
          <div class="metrics">
            <div class="metric">
              <span>Core domains</span>
              <strong>04</strong>
              <small>security-centered</small>
            </div>
            <div class="metric">
              <span>Public identity</span>
              <strong>Minimal</strong>
              <small>work-first profile</small>
            </div>
            <div class="metric">
              <span>Portfolio evidence</span>
              <strong>Labs</strong>
              <small>documented output</small>
            </div>
            <div class="metric">
              <span>Research scope</span>
              <strong>Authorized</strong>
              <small>ethical boundaries</small>
            </div>
          </div>

          <div class="panel">
            <div class="panel-title">review signal</div>
            <div class="review-list">
              <div class="review-item"><b>Technical projects</b><em>verifiable</em></div>
              <div class="review-item"><b>Security methodology</b><em>documented</em></div>
              <div class="review-item"><b>Personal exposure</b><em>minimized</em></div>
              <div class="review-item"><b>Professional use</b><em>employer-ready</em></div>
            </div>
          </div>
        </div>
      </aside>
    </section>

    <div class="section-head" id="focus">
      <h2>Focus areas</h2>
      <p>Clear security domains without theatrical language. Suitable for job applications, interviews, networking, and technical review.</p>
    </div>

    <section class="cards" aria-label="Focus areas">
      <article class="card">
        <div class="num">01</div>
        <h3>Secure Systems Engineering</h3>
        <p>Architecture review, trust boundaries, hardening logic, execution paths, and secure-by-design reasoning.</p>
      </article>

      <article class="card">
        <div class="num">02</div>
        <h3>Security Research</h3>
        <p>Controlled attack-surface analysis, vulnerability classes, lab methodology, exploit-chain reasoning, and defensive implications.</p>
      </article>

      <article class="card">
        <div class="num">03</div>
        <h3>Detection Engineering</h3>
        <p>Telemetry interpretation, behavior mapping, detection logic, incident evidence, and signal reduction.</p>
      </article>
    </section>

    <div class="section-head" id="work">
      <h2>Selected work</h2>
      <p>Replace these placeholders with real repositories, writeups, tools, labs, benchmarks, or case studies as they are published.</p>
    </div>

    <section class="work-grid" aria-label="Selected work">
      <article class="work">
        <span class="tag">systems research</span>
        <h3>Runtime / Compiler Security Notes</h3>
        <p>Research notes on execution models, trust boundaries, native tooling, artifact validation, and secure systems architecture.</p>
      </article>

      <article class="work">
        <span class="tag">security labs</span>
        <h3>Authorized Lab Writeups</h3>
        <p>Methodology-driven writeups from owned or authorized lab environments, with emphasis on root cause and defensive lessons.</p>
      </article>

      <article class="work">
        <span class="tag">tooling</span>
        <h3>Security Automation Utilities</h3>
        <p>Small practical tools: parsers, log analyzers, validation helpers, lab automation scripts, and research workflow utilities.</p>
      </article>

      <article class="work">
        <span class="tag">detection</span>
        <h3>Detection Logic Experiments</h3>
        <p>Rule concepts, telemetry fields, behavior chains, alert-quality notes, and adversary-pattern mapping for defensive context.</p>
      </article>
    </section>

    <section class="methodology" id="methodology">
      <h2>Private by design.<br />Professional by output.</h2>
      <div class="principle-list">
        <div class="principle">Work only in owned, authorized, or controlled lab environments.</div>
        <div class="principle">Prefer evidence, reproducibility, and documentation over unsupported claims.</div>
        <div class="principle">Explain technical risk clearly without exaggeration or theatrics.</div>
        <div class="principle">Keep public identity minimal while making technical work reviewable.</div>
      </div>
    </section>

    <section class="contact" id="contact">
      <div>
        <h2>Professional review</h2>
        <p>For employers or collaborators: link a professional email, GitHub repositories, LinkedIn, or selected project documents here.</p>
      </div>
      <a class="button primary" href="mailto:your-email@example.com">Contact</a>
    </section>

    <footer>
      <span>Independent Security Research Portfolio</span>
      <span>Secure Systems • Security Research • Detection Engineering</span>
    </footer>
  </main>
</body>
</html>
