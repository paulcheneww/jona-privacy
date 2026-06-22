<!DOCTYPE html>
<html lang="de" data-theme="light">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Datenschutzerklärung</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=Inter:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    /* ── Light Mode (Standard) ── */
    :root, [data-theme="light"] {
      --bg:        #f5f5f7;
      --surface:   #ffffff;
      --border:    #e0e0e8;
      --accent:    #5b4fe9;
      --accent-dim:#ede9ff;
      --text:      #3a3a4a;
      --muted:     #888899;
      --strong:    #0f0f1a;
      --glow1:     transparent;
      --glow2:     transparent;
      --chip-bg:   #f0eeff;
      --chip-hover-bg: #ede9ff;
      --chip-hover-color: #3a2fd4;
    }

    /* ── Dark Mode ── */
    [data-theme="dark"] {
      --bg:        #0b0c10;
      --surface:   #13141a;
      --border:    #1f2130;
      --accent:    #7c6af7;
      --accent-dim:#3d3578;
      --text:      #d4d6e0;
      --muted:     #5a5d72;
      --strong:    #f0f1f5;
      --glow1:     #1a1550;
      --glow2:     #0d1a35;
      --chip-bg:   #13141a;
      --chip-hover-bg: #3d3578;
      --chip-hover-color: #f0f1f5;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Inter', sans-serif;
      font-weight: 300;
      line-height: 1.75;
      min-height: 100vh;
      transition: background 0.3s, color 0.3s;
    }

    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        radial-gradient(ellipse 60% 40% at 70% 10%, var(--glow1) 0%, transparent 60%),
        radial-gradient(ellipse 40% 30% at 10% 80%, var(--glow2) 0%, transparent 55%);
      pointer-events: none;
      z-index: 0;
      transition: background-image 0.3s;
    }

    /* ── Toggle Button ── */
    .theme-toggle {
      position: fixed;
      top: 20px;
      right: 20px;
      z-index: 100;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 100px;
      padding: 8px 16px;
      font-family: 'Inter', sans-serif;
      font-size: 13px;
      font-weight: 500;
      color: var(--text);
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 7px;
      transition: background 0.2s, border-color 0.2s, color 0.2s;
      box-shadow: 0 2px 8px rgba(0,0,0,0.08);
    }

    .theme-toggle:hover {
      border-color: var(--accent);
      color: var(--accent);
    }

    .theme-toggle .icon { font-size: 15px; line-height: 1; }

    /* ── Layout ── */
    .wrap {
      position: relative;
      z-index: 1;
      max-width: 780px;
      margin: 0 auto;
      padding: 80px 24px 120px;
    }

    header {
      border-bottom: 1px solid var(--border);
      padding-bottom: 48px;
      margin-bottom: 64px;
    }

    .eyebrow {
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 16px;
    }

    h1 {
      font-family: 'Syne', sans-serif;
      font-size: clamp(2rem, 5vw, 3.2rem);
      font-weight: 800;
      color: var(--strong);
      line-height: 1.1;
      margin-bottom: 20px;
      transition: color 0.3s;
    }

    .meta { font-size: 13px; color: var(--muted); }

    section { margin-bottom: 56px; }

    h2 {
      font-family: 'Syne', sans-serif;
      font-size: 1.15rem;
      font-weight: 700;
      color: var(--strong);
      margin-bottom: 16px;
      display: flex;
      align-items: center;
      gap: 12px;
      transition: color 0.3s;
    }

    h2::before {
      content: '';
      display: inline-block;
      width: 3px;
      height: 1.1em;
      background: var(--accent);
      border-radius: 2px;
      flex-shrink: 0;
    }

    p { margin-bottom: 12px; }
    p:last-child { margin-bottom: 0; }

    ul { list-style: none; padding-left: 0; margin-top: 8px; }

    ul li { padding: 6px 0 6px 20px; position: relative; }

    ul li::before {
      content: '–';
      position: absolute;
      left: 0;
      color: var(--accent);
    }

    strong.hl { color: var(--strong); }

    .callout {
      background: var(--surface);
      border: 1px solid var(--border);
      border-left: 3px solid var(--accent);
      border-radius: 6px;
      padding: 20px 24px;
      margin-top: 12px;
      font-size: 14px;
      transition: background 0.3s, border-color 0.3s;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 16px;
      font-size: 14px;
    }

    th {
      text-align: left;
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      color: var(--strong);
      padding: 10px 14px;
      border-bottom: 1px solid var(--border);
      transition: color 0.3s;
    }

    td {
      padding: 10px 14px;
      border-bottom: 1px solid var(--border);
      color: var(--text);
      vertical-align: top;
    }

    tr:last-child td { border-bottom: none; }

    a { color: var(--accent); text-decoration: none; }
    a:hover { text-decoration: underline; }

    .contact-chip {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: var(--chip-bg);
      border: 1px solid var(--border);
      border-radius: 100px;
      padding: 10px 20px;
      font-size: 14px;
      color: var(--accent);
      margin-top: 12px;
      transition: border-color 0.2s, background 0.2s, color 0.2s;
    }

    .contact-chip:hover {
      border-color: var(--accent);
      background: var(--chip-hover-bg);
      color: var(--chip-hover-color);
      text-decoration: none;
    }

    footer {
      border-top: 1px solid var(--border);
      padding-top: 32px;
      margin-top: 80px;
      font-size: 12px;
      color: var(--muted);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 8px;
    }

    @media (max-width: 500px) {
      footer { flex-direction: column; }
      table, thead, tbody, th, td, tr { display: block; }
      th { display: none; }
      td { border: none; padding: 6px 0; }
      td::before {
        content: attr(data-label) ": ";
        font-weight: 500;
        color: var(--strong);
      }
    }
  </style>
</head>
<body>

<!-- Theme Toggle -->
<button class="theme-toggle" onclick="toggleTheme()" aria-label="Theme wechseln">
  <span class="icon" id="theme-icon">🌙</span>
  <span id="theme-label">Dark Mode</span>
</button>

<div class="wrap">

  <header>
    <p class="eyebrow">Rechtliches</p>
    <h1>Datenschutzerklärung</h1>
    <p class="meta">Zuletzt aktualisiert: Juni 2025 &nbsp;·&nbsp; Deutsch &nbsp;·&nbsp; DSGVO-konform</p>
  </header>

  <section>
    <h2>Verantwortliche Stelle</h2>
    <p>
      Verantwortlich für die Verarbeitung personenbezogener Daten im Zusammenhang
      mit diesem Discord-Bot ist der Betreiber des Bots. Bei Fragen zur
      Datenverarbeitung kannst du uns über Discord kontaktieren (siehe Abschnitt&nbsp;8).
    </p>
  </section>

  <section>
    <h2>Welche Daten werden verarbeitet?</h2>
    <p>Der Bot verarbeitet nur die Daten, die Discord beim Aufruf von Befehlen oder Ereignissen automatisch übermittelt:</p>
    <table>
      <thead>
        <tr>
          <th>Datenkategorie</th>
          <th>Beispiel</th>
          <th>Zweck</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td data-label="Datenkategorie">Server-ID</td>
          <td data-label="Beispiel">123456789012345678</td>
          <td data-label="Zweck">Servergebundene Funktionen</td>
        </tr>
        <tr>
          <td data-label="Datenkategorie">Kanal-ID</td>
          <td data-label="Beispiel">987654321098765432</td>
          <td data-label="Zweck">Antwort im richtigen Kanal</td>
        </tr>
        <tr>
          <td data-label="Datenkategorie">Nutzer-ID</td>
          <td data-label="Beispiel">111222333444555666</td>
          <td data-label="Zweck">Befehlszuordnung, Berechtigungen</td>
        </tr>
        <tr>
          <td data-label="Datenkategorie">Befehlsinhalt</td>
          <td data-label="Beispiel">/test</td>
          <td data-label="Zweck">Ausführung der Funktion</td>
        </tr>
      </tbody>
    </table>
    <div class="callout" style="margin-top:16px;">
      Es werden keine Nachrichten mitgelesen, keine Profile gespeichert und keine Daten an Dritte weitergegeben.
    </div>
  </section>

  <section>
    <h2>Rechtsgrundlage</h2>
    <p>
      Die Verarbeitung erfolgt auf Grundlage von Art.&nbsp;6 Abs.&nbsp;1 lit.&nbsp;b DSGVO
      (Vertragserfüllung), da die Datenverarbeitung technisch notwendig ist,
      um die vom Nutzer angeforderten Funktionen des Bots bereitzustellen.
    </p>
  </section>

  <section>
    <h2>Speicherdauer</h2>
    <p>
      Daten werden nur so lange gespeichert, wie es für den Betrieb des Bots erforderlich ist.
      Technische Logs (sofern vorhanden) werden spätestens nach <strong class="hl">30 Tagen</strong> automatisch gelöscht.
      Es findet keine dauerhafte Speicherung personenbezogener Daten statt.
    </p>
  </section>

  <section>
    <h2>Weitergabe an Dritte</h2>
    <p>Eine Weitergabe deiner Daten an Dritte findet nicht statt. Ausnahmen gelten nur, wenn wir gesetzlich dazu verpflichtet sind.</p>
    <p>
      Beachte, dass Discord Inc. als Plattformbetreiber eigene Daten erhebt.
      Deren Datenschutzrichtlinie findest du unter
      <a href="https://discord.com/privacy" target="_blank" rel="noopener">discord.com/privacy</a>.
    </p>
  </section>

  <section>
    <h2>Deine Rechte</h2>
    <p>Nach der DSGVO stehen dir folgende Rechte zu:</p>
    <ul>
      <li><strong class="hl">Auskunft</strong> – du kannst jederzeit erfragen, welche Daten gespeichert sind (Art. 15 DSGVO),</li>
      <li><strong class="hl">Berichtigung</strong> – unrichtige Daten können korrigiert werden (Art. 16 DSGVO),</li>
      <li><strong class="hl">Löschung</strong> – du kannst die Löschung deiner Daten verlangen (Art. 17 DSGVO),</li>
      <li><strong class="hl">Einschränkung</strong> – du kannst die Verarbeitung einschränken lassen (Art. 18 DSGVO),</li>
      <li><strong class="hl">Widerspruch</strong> – du kannst der Verarbeitung widersprechen (Art. 21 DSGVO),</li>
      <li><strong class="hl">Beschwerde</strong> – du hast das Recht, dich bei einer Aufsichtsbehörde zu beschweren (Art. 77 DSGVO).</li>
    </ul>
  </section>

  <section>
    <h2>Cookies &amp; Tracking</h2>
    <p>
      Der Bot selbst setzt keine Cookies und führt kein Tracking durch.
      Diese Webseite verwendet ebenfalls keine Cookies, keine Analyse-Tools
      und keine eingebetteten Inhalte von Drittanbietern.
    </p>
  </section>

  <section>
    <h2>Kontakt</h2>
    <p>Für Anfragen zur Datenverarbeitung oder zur Ausübung deiner Rechte erreichst du uns über unseren Discord-Server:</p>
    <a class="contact-chip" href="https://discord.gg/W9cCUFRw5e" target="_blank" rel="noopener">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
        <path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057c.002.022.015.043.034.055a19.93 19.93 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028 14.09 14.09 0 0 0 1.226-1.994.076.076 0 0 0-.041-.106 13.14 13.14 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03z"/>
      </svg>
      Discord-Server beitreten
    </a>
  </section>

  <footer>
    <span>© 2025 — Alle Rechte vorbehalten</span>
    <span>Betrieben unabhängig von Discord Inc.</span>
  </footer>

</div>

<script>
  function toggleTheme() {
    const html = document.documentElement;
    const isDark = html.getAttribute('data-theme') === 'dark';
    html.setAttribute('data-theme', isDark ? 'light' : 'dark');
    document.getElementById('theme-icon').textContent  = isDark ? '🌙' : '☀️';
    document.getElementById('theme-label').textContent = isDark ? 'Dark Mode' : 'Light Mode';
    localStorage.setItem('theme', isDark ? 'light' : 'dark');
  }

  // Gespeicherte Präferenz wiederherstellen
  (function() {
    const saved = localStorage.getItem('theme');
    if (saved === 'dark') {
      document.documentElement.setAttribute('data-theme', 'dark');
      document.getElementById('theme-icon').textContent  = '☀️';
      document.getElementById('theme-label').textContent = 'Light Mode';
    }
  })();
</script>
</body>
</html>
