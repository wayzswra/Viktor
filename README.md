[geburtstag_viktor.html](https://github.com/user-attachments/files/25869348/geburtstag_viktor.html)
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Alles Gute, Viktor! 🎂</title>
  <link href="https://fonts.googleapis.com/css2?family=Bangers&family=Comic+Neue:ital,wght@0,400;0,700;1,700&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --yellow: #FFE83D;
      --orange: #FF6B35;
      --pink: #FF3D9A;
      --blue: #3DFFE8;
      --dark: #0f0f1a;
      --purple: #9B5FFF;
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { background: var(--dark); font-family: 'Comic Neue', cursive; min-height: 100vh; overflow-x: hidden; }

    .confetti-wrap { position: fixed; inset: 0; pointer-events: none; z-index: 0; overflow: hidden; }
    .c { position: absolute; top: -20px; width: 10px; height: 14px; border-radius: 2px; opacity: 0; animation: fall linear infinite; }
    @keyframes fall {
      0%   { transform: translateY(0) rotate(0deg); opacity: 1; }
      100% { transform: translateY(110vh) rotate(900deg); opacity: 0.2; }
    }

    .page { position: relative; z-index: 1; display: flex; flex-direction: column; align-items: center; padding: 40px 20px 60px; min-height: 100vh; gap: 32px; }

    .banner { text-align: center; animation: popIn .6s cubic-bezier(.175,.885,.32,1.6) both; }
    @keyframes popIn { from { transform: scale(0) rotate(-6deg); opacity: 0; } to { transform: scale(1) rotate(0deg); opacity: 1; } }
    .banner h1 {
      font-family: 'Bangers', cursive; font-size: clamp(52px, 12vw, 110px);
      letter-spacing: 4px; line-height: 1;
      background: linear-gradient(135deg, var(--yellow), var(--orange), var(--pink));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      filter: drop-shadow(0 0 18px rgba(255,107,53,.6));
    }
    .banner .name-display {
      font-family: 'Bangers', cursive; font-size: clamp(40px, 10vw, 90px);
      letter-spacing: 6px; color: var(--blue);
      animation: glow 1.8s ease-in-out infinite alternate;
    }
    @keyframes glow {
      from { filter: drop-shadow(0 0 10px var(--blue)); }
      to   { filter: drop-shadow(0 0 35px var(--blue)) drop-shadow(0 0 60px var(--purple)); }
    }

    .badge-50 {
      display: inline-flex; align-items: center; justify-content: center;
      width: 120px; height: 120px; border-radius: 50%;
      background: conic-gradient(var(--yellow), var(--orange), var(--pink), var(--purple), var(--blue), var(--yellow));
      box-shadow: 0 0 40px rgba(255,232,61,.5), 0 0 80px rgba(255,61,154,.3);
      animation: hueSpin 4s linear infinite;
    }
    @keyframes hueSpin { from { filter: hue-rotate(0deg); } to { filter: hue-rotate(360deg); } }
    .badge-50 .inner { width: 100px; height: 100px; border-radius: 50%; background: var(--dark); display: flex; flex-direction: column; align-items: center; justify-content: center; }
    .badge-50 .num { font-family: 'Bangers', cursive; font-size: 52px; line-height: 1; background: linear-gradient(135deg, var(--yellow), var(--orange)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    .badge-50 .lbl { font-family: 'Bangers', cursive; font-size: 13px; letter-spacing: 2px; color: rgba(255,255,255,.6); }

    .row-center { display: flex; align-items: center; justify-content: center; gap: 24px; flex-wrap: wrap; }

    .cake-wrap { font-size: 110px; line-height: 1; animation: wobble 1.4s ease-in-out infinite; cursor: pointer; user-select: none; }
    @keyframes wobble { 0%,100% { transform: rotate(-4deg) scale(1); } 50% { transform: rotate(4deg) scale(1.07); } }

    .special-msg {
      background: rgba(255,255,255,0.05); border: 2px dashed var(--yellow);
      border-radius: 20px; padding: 24px 32px; max-width: 580px; width: 100%;
      text-align: center; backdrop-filter: blur(6px);
    }
    .special-msg p { font-size: 18px; font-weight: 700; color: #fff; line-height: 1.7; }
    .special-msg p span { color: var(--yellow); }
    .special-msg .punchline { margin-top: 14px; padding-top: 14px; border-top: 1px solid rgba(255,255,255,.15); color: rgba(255,255,255,.9); font-style: italic; }
    .special-msg .punchline strong { color: var(--pink); font-style: normal; }

    .joke-card {
      background: rgba(255,255,255,0.05); border: 2px solid var(--purple);
      border-radius: 20px; padding: 28px 36px; max-width: 600px; width: 100%;
      text-align: center; backdrop-filter: blur(6px); position: relative; overflow: hidden;
    }
    .joke-card::before { content: ''; position: absolute; inset: 0; background: linear-gradient(135deg, rgba(155,95,255,.08), rgba(61,255,232,.05)); pointer-events: none; }
    .joke-label { font-family: 'Bangers', cursive; font-size: 22px; letter-spacing: 3px; color: var(--blue); margin-bottom: 16px; }
    .joke-setup { font-size: 17px; font-weight: 700; color: rgba(255,255,255,.85); line-height: 1.5; margin-bottom: 6px; }
    .joke-punch { font-size: 19px; font-weight: 700; color: var(--yellow); line-height: 1.5; min-height: 56px; transition: opacity .3s; }
    .joke-punch.hidden { opacity: 0; }
    .progress-bar { display: flex; gap: 6px; justify-content: center; margin-top: 14px; }
    .dot { width: 8px; height: 8px; border-radius: 50%; background: rgba(255,255,255,.2); transition: background .3s; }
    .dot.active { background: var(--purple); box-shadow: 0 0 8px var(--purple); }
    .btn-joke {
      margin-top: 18px; background: linear-gradient(135deg, var(--purple), var(--pink));
      border: none; border-radius: 50px; padding: 12px 32px;
      font-family: 'Bangers', cursive; font-size: 20px; letter-spacing: 2px; color: #fff;
      cursor: pointer; box-shadow: 0 4px 20px rgba(155,95,255,.5); transition: transform .15s, box-shadow .15s;
    }
    .btn-joke:hover { transform: scale(1.07) rotate(-1deg); box-shadow: 0 6px 30px rgba(155,95,255,.8); }
    .btn-joke:active { transform: scale(.95); }

    .facts-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 16px; max-width: 720px; width: 100%; }
    .fact-card { background: rgba(255,255,255,0.04); border: 1.5px solid rgba(255,255,255,0.12); border-radius: 16px; padding: 20px 18px; text-align: center; transition: transform .2s, border-color .2s; }
    .fact-card:hover { transform: translateY(-5px) rotate(1deg); border-color: var(--blue); }
    .fact-card .icon { font-size: 40px; margin-bottom: 8px; }
    .fact-card .fact-title { font-family: 'Bangers', cursive; font-size: 18px; letter-spacing: 2px; color: var(--yellow); margin-bottom: 6px; }
    .fact-card p { font-size: 14px; color: rgba(255,255,255,.7); line-height: 1.5; }

    .footer-msg { font-family: 'Bangers', cursive; font-size: clamp(18px, 5vw, 32px); letter-spacing: 3px; text-align: center; color: var(--pink); filter: drop-shadow(0 0 10px var(--pink)); animation: pulse 2s ease-in-out infinite; }
    @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: .5; } }

    .spark { position: fixed; width: 8px; height: 8px; border-radius: 50%; pointer-events: none; z-index: 999; animation: spark .7s ease-out forwards; }
    @keyframes spark { 0% { transform: translate(0,0) scale(1); opacity: 1; } 100% { transform: var(--tx) scale(0); opacity: 0; } }
  </style>
</head>
<body>

<div class="confetti-wrap" id="confetti"></div>

<div class="page">

  <div class="banner">
    <div class="name-display">🎉 VIKTOR 🎉</div>
    <h1>ALLES GUTE!</h1>
  </div>

  <div class="row-center">
    <div class="badge-50"><div class="inner"><span class="num">50</span><span class="lbl">JAHRE</span></div></div>
    <div class="cake-wrap" id="cake">🎂</div>
    <div class="badge-50"><div class="inner"><span class="num">50</span><span class="lbl">JAHRE</span></div></div>
  </div>

  <div class="special-msg">
    <p>🎊 Herzlichen Glückwunsch zum <span>50. Geburtstag!</span><br>
    Du bist jetzt offiziell <span>älter als Google</span> 🌐</p>
    <p class="punchline">
      Mit 50 kannst du immer noch ohne Brille lesen!<br>
      <strong>Nur wenn der Text mit Sprühfarbe an eine Hauswand geschrieben ist! 🎨😂</strong>
    </p>
  </div>

  <div class="joke-card">
    <div class="joke-label">🖧 SYSADMIN-WITZ-SERVER v50.0</div>
    <div class="joke-setup" id="jokeSetup">Warum hat der Systemintegrator keine Freunde?</div>
    <div class="joke-punch" id="jokePunch">Weil er immer sagt: „Das liegt nicht an mir – das ist ein Netzwerkproblem!" 🔌</div>
    <div class="progress-bar" id="progressBar"></div>
    <button class="btn-joke" id="jokeBtn">NÄCHSTER WITZ &gt;&gt;</button>
  </div>

  <div class="facts-grid">
    <div class="fact-card">
      <div class="icon">🖧</div>
      <div class="fact-title">Uptime: 50 J.</div>
      <p>Viktor läuft seit 50 Jahren ohne ungeplanten Ausfall. Kein Rechenzentrum der Welt schafft das!</p>
    </div>
    <div class="fact-card">
      <div class="icon">🔧</div>
      <div class="fact-title">Troubleshooter</div>
      <p>Bevor Viktor den Raum betritt, lösen sich Probleme schon von selbst. Aus Respekt.</p>
    </div>
    <div class="fact-card">
      <div class="icon">📡</div>
      <div class="fact-title">Volle Signalstärke</div>
      <p>Mit 50 Jahren noch 5 Balken. Andere verlieren das Signal – Viktor verstärkt es noch.</p>
    </div>
    <div class="fact-card">
      <div class="icon">🔒</div>
      <div class="fact-title">Firewall-Legende</div>
      <p>Viktors Firewall lässt nur durch, was er will. Und Geburtstagskuchen kommt immer durch. 🍰</p>
    </div>
  </div>

  <div class="footer-msg">🥳 VON DEINEM GANZEN TEAM – DANKE FÜR ALLES! 🥳</div>

</div>

<script>
  /* CONFETTI */
  const wrap = document.getElementById('confetti');
  const cols = ['#FFE83D','#FF6B35','#FF3D9A','#3DFFE8','#9B5FFF','#fff'];
  for (let i = 0; i < 80; i++) {
    const c = document.createElement('div');
    c.className = 'c';
    c.style.left = Math.random() * 100 + 'vw';
    c.style.width  = (8 + Math.random() * 8) + 'px';
    c.style.height = (10 + Math.random() * 10) + 'px';
    c.style.background = cols[Math.floor(Math.random() * cols.length)];
    c.style.animationDuration = (4 + Math.random() * 8) + 's';
    c.style.animationDelay = (Math.random() * 8) + 's';
    c.style.borderRadius = Math.random() > .5 ? '50%' : '2px';
    wrap.appendChild(c);
  }

  /* SYSADMIN WITZE */
  const jokes = [
    {
      setup: "Warum hat der Systemintegrator keine Freunde?",
      punch: "Weil er immer sagt: „Das liegt nicht an mir – das ist ein Netzwerkproblem!" 🔌"
    },
    {
      setup: "Viktor feiert heute seinen 50. Geburtstag.",
      punch: "Er hat die Feier natürlich redundant geplant – mit Backup-Kuchen im Keller. 🎂"
    },
    {
      setup: "Wie begrüßt Viktor seine Gäste?",
      punch: "„Willkommen – habt ihr euch schon im Active Directory angemeldet?" 👤"
    },
    {
      setup: "Was sagt Viktor, wenn der Kuchen nicht schmeckt?",
      punch: "„Ich hab die Anforderungen umgesetzt. Das ist ein Anwenderfehler." 🍰"
    },
    {
      setup: "Warum ist Viktors Geburtstag so zuverlässig?",
      punch: "Er läuft auf einem georedundanten Kalender mit automatischem Failover. 📅"
    },
    {
      setup: "Was wünscht sich ein Systemintegrator zum Geburtstag?",
      punch: "Endlich mal ein Ticket, das wirklich reproduzierbar ist! 🎫"
    },
    {
      setup: "Viktor mit 50 ist wie ein gut gepflegtes Rechenzentrum:",
      punch: "Kühl, strukturiert, und wehe dem, der die Verkabelung anfasst! 🌡️"
    },
    {
      setup: "Wie viele Systemintegratoren braucht man, um eine Glühbirne zu wechseln?",
      punch: "Keiner – das ist doch ein Endgerät. Dafür ist der User-Support zuständig! 💡"
    },
  ];

  let idx = 0;
  const setup = document.getElementById('jokeSetup');
  const punch = document.getElementById('jokePunch');
  const bar   = document.getElementById('progressBar');

  jokes.forEach((_, i) => {
    const d = document.createElement('div');
    d.className = 'dot' + (i === 0 ? ' active' : '');
    bar.appendChild(d);
  });

  document.getElementById('jokeBtn').addEventListener('click', () => {
    punch.classList.add('hidden');
    setTimeout(() => {
      idx = (idx + 1) % jokes.length;
      setup.textContent = jokes[idx].setup;
      punch.textContent = jokes[idx].punch;
      punch.classList.remove('hidden');
      document.querySelectorAll('.dot').forEach((d, i) => d.classList.toggle('active', i === idx));
    }, 300);
  });

  /* CAKE CLICK */
  const emojis = ['🎂','🎉','🥳','🎊','✨','🍰','🎈','🖧','📡','🔧','🔌'];
  let ci = 0;
  document.getElementById('cake').addEventListener('click', e => {
    ci = (ci + 1) % emojis.length;
    e.target.textContent = emojis[ci];
    sparks(e.clientX, e.clientY);
  });

  function sparks(x, y) {
    const sc = ['#FFE83D','#FF3D9A','#3DFFE8','#FF6B35','#9B5FFF'];
    for (let i = 0; i < 16; i++) {
      const s = document.createElement('div');
      s.className = 'spark';
      const a = (Math.PI * 2 / 16) * i;
      const d = 60 + Math.random() * 90;
      s.style.cssText = `left:${x}px;top:${y}px;background:${sc[i%sc.length]};--tx:translate(${Math.cos(a)*d}px,${Math.sin(a)*d}px);animation-duration:${.5+Math.random()*.4}s;`;
      document.body.appendChild(s);
      setTimeout(() => s.remove(), 900);
    }
  }
  document.addEventListener('click', e => {
    if (!['cake','jokeBtn'].includes(e.target.id)) sparks(e.clientX, e.clientY);
  });
</script>
</body>
</html>
