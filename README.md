<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Muhammad Anees | GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d1117;
    --card: #161b22;
    --border: #30363d;
    --text: #c9d1d9;
    --muted: #8b949e;
    --accent: #58a6ff;
    --accent2: #a371f7;
    --accent3: #3fb950;
    --accent4: #f78166;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inter', sans-serif;
    min-height: 100vh;
    padding: 30px 16px;
    overflow-x: hidden;
  }
  body::before, body::after {
    content: "";
    position: fixed;
    width: 520px; height: 520px;
    border-radius: 50%;
    filter: blur(120px);
    opacity: .18;
    z-index: -1;
    animation: drift 18s ease-in-out infinite alternate;
  }
  body::before { background: var(--accent2); top: -160px; left: -140px; }
  body::after  { background: var(--accent); bottom: -180px; right: -140px; animation-delay: -9s; }
  @keyframes drift {
    from { transform: translate(0,0) scale(1); }
    to   { transform: translate(90px,60px) scale(1.15); }
  }

  .wrap { max-width: 860px; margin: 0 auto; display: grid; gap: 18px; }

  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 22px 24px;
    opacity: 0;
    transform: translateY(24px);
    animation: rise .7s cubic-bezier(.2,.8,.2,1) forwards;
    transition: border-color .3s, box-shadow .3s;
  }
  .card:hover {
    border-color: var(--accent);
    box-shadow: 0 0 0 1px var(--accent), 0 10px 40px -10px rgba(88,166,255,.35);
  }
  .card:nth-child(1) { animation-delay: .1s; }
  .card:nth-child(2) { animation-delay: .25s; }
  .card:nth-child(3) { animation-delay: .4s; }
  .card:nth-child(4) { animation-delay: .55s; }
  @keyframes rise { to { opacity: 1; transform: translateY(0); } }

  h2 {
    font-size: 1.05rem;
    font-weight: 800;
    letter-spacing: .3px;
    margin-bottom: 16px;
    display: flex; align-items: center; gap: 8px;
  }

  .hero { display: flex; align-items: center; gap: 18px; flex-wrap: wrap; }
  .avatar {
    width: 74px; height: 74px; border-radius: 50%;
    background: conic-gradient(var(--accent), var(--accent2), var(--accent3), var(--accent));
    padding: 3px;
    animation: spin 6s linear infinite;
  }
  .avatar-inner {
    width: 100%; height: 100%; border-radius: 50%;
    background: var(--card);
    display: grid; place-items: center;
    font-family: 'Fira Code', monospace; font-weight: 600; font-size: 1.3rem;
    color: var(--accent);
    animation: spin 6s linear infinite reverse;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .name {
    font-size: 1.9rem; font-weight: 800;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3), var(--accent));
    background-size: 300% auto;
    -webkit-background-clip: text; background-clip: text; color: transparent;
    animation: shine 5s linear infinite;
  }
  @keyframes shine { to { background-position: 300% center; } }
  .wave { display: inline-block; animation: wave 2.2s infinite; transform-origin: 70% 70%; -webkit-text-fill-color: initial; }
  @keyframes wave {
    0%, 60%, 100% { transform: rotate(0); }
    10%, 30% { transform: rotate(14deg); }
    20% { transform: rotate(-8deg); }
    40% { transform: rotate(10deg); }
    50% { transform: rotate(-4deg); }
  }

  .role {
    font-family: 'Fira Code', monospace;
    color: var(--accent3);
    font-size: .95rem;
    margin-top: 6px;
    min-height: 1.4em;
  }
  .role::after {
    content: "▋"; margin-left: 3px;
    animation: blink 1s steps(1) infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }

  .bio { color: var(--muted); font-size: .92rem; line-height: 1.6; margin-top: 12px; }

  .tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 16px; }
  .tag {
    font-size: .78rem; padding: 6px 12px; border-radius: 999px;
    border: 1px solid var(--border); background: #0d1117;
    transition: all .25s;
  }
  .tag:hover { border-color: var(--accent2); color: var(--accent2); }

  /* Tech stack: icon grid grouped by category */
  .group-title {
    font-size: .72rem; text-transform: uppercase; letter-spacing: 1.2px;
    color: var(--muted); margin: 18px 0 10px;
    font-family: 'Fira Code', monospace;
  }
  .group-title:first-of-type { margin-top: 0; }
  .icons { display: grid; grid-template-columns: repeat(auto-fill, minmax(118px, 1fr)); gap: 10px; }
  .skill {
    display: flex; align-items: center; gap: 10px;
    padding: 9px 11px;
    background: #0d1117;
    border: 1px solid var(--border);
    border-radius: 10px;
    font-size: .8rem; font-weight: 600;
    transition: transform .25s, border-color .25s, box-shadow .25s;
    animation: float 4s ease-in-out infinite;
    animation-delay: var(--d);
  }
  .skill:hover {
    transform: translateY(-3px);
    border-color: var(--c);
    box-shadow: 0 8px 20px -10px var(--c);
  }
  .skill .ico {
    width: 26px; height: 26px; flex: 0 0 26px;
    border-radius: 7px;
    background: var(--c);
    display: grid; place-items: center;
  }
  .skill .ico img { width: 16px; height: 16px; filter: brightness(0) invert(1); }
  .skill .ico span { color: #fff; font-size: .72rem; font-weight: 800; font-family: 'Fira Code', monospace; }
  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-3px); }
  }

  .stats { display: grid; grid-template-columns: 1fr 180px; gap: 18px; align-items: center; }
  .stat-list { display: grid; gap: 12px; }
  .stat {
    display: flex; justify-content: space-between; align-items: center;
    padding: 10px 14px; background: #0d1117; border: 1px solid var(--border);
    border-radius: 10px; font-size: .9rem;
    transition: transform .25s, border-color .25s;
  }
  .stat:hover { transform: translateX(6px); border-color: var(--accent3); }
  .stat b {
    font-family: 'Fira Code', monospace;
    color: var(--accent3); font-size: 1.05rem;
  }
  .ring { position: relative; width: 170px; height: 170px; margin: auto; }
  .ring svg { transform: rotate(-90deg); width: 100%; height: 100%; }
  .ring circle.track { stroke: var(--border); }
  .ring circle.fill {
    stroke: url(#g); stroke-linecap: round;
    stroke-dasharray: 440; stroke-dashoffset: 440;
    animation: fill 2.2s .6s cubic-bezier(.4,0,.2,1) forwards;
  }
  @keyframes fill { to { stroke-dashoffset: 110; } }
  .ring .grade {
    position: absolute; inset: 0; display: grid; place-items: center;
    font-size: 3rem; font-weight: 800;
    color: var(--accent3);
    text-shadow: 0 0 24px rgba(63,185,80,.5);
    animation: pop .6s 1.6s both;
  }
  @keyframes pop { from { transform: scale(.4); opacity: 0; } to { transform: scale(1); opacity: 1; } }

  .empty {
    text-align: center; color: var(--muted); font-size: .9rem;
    padding: 26px 0; border: 1px dashed var(--border); border-radius: 10px;
  }
  .empty::before { content: "⌁"; display: block; font-size: 1.6rem; color: var(--accent2); animation: pulse 2s infinite; }
  @keyframes pulse { 50% { opacity: .3; transform: scale(.9); } }

  footer {
    text-align: center; font-size: .78rem; color: var(--muted);
    opacity: 0; animation: rise .8s 1s forwards;
  }
  footer span { color: var(--accent4); animation: heart 1.4s infinite; display: inline-block; }
  @keyframes heart { 0%,100% { transform: scale(1); } 50% { transform: scale(1.25); } }

  @media (max-width: 640px) {
    .stats { grid-template-columns: 1fr; }
    .name { font-size: 1.5rem; }
  }
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation: none !important; opacity: 1 !important; transform: none !important; }
  }
</style>
</head>
<body>
<div class="wrap">

  <section class="card">
    <h2>👋 About Me</h2>
    <div class="hero">
      <div class="avatar"><div class="avatar-inner">MA</div></div>
      <div>
        <div class="name">Hi, I'm Muhammad Anees <span class="wave">👋</span></div>
        <div class="role" id="role"></div>
      </div>
    </div>
    <p class="bio">
      💻 IT Professional &amp; Full-Stack Developer with 6+ years of experience.<br>
      🚀 Building modern web applications and digital solutions.
    </p>
    <div class="tags">
      <span class="tag">🤖 AI Automation &amp; Agentic AI</span>
      <span class="tag">📈 Digital Marketing &amp; SEO</span>
      <span class="tag">☁️ Google Cloud · Cloudflare · Google Workspace</span>
      <span class="tag">🎨 UI/UX &amp; Graphic Design</span>
    </div>
  </section>

  <section class="card">
    <h2>💻 Tech Stack</h2>
    <div id="stack"></div>
  </section>

  <section class="card">
    <h2>📊 GitHub Stats</h2>
    <div class="stats">
      <div class="stat-list">
        <div class="stat">Total Stars Earned <b data-count="0">0</b></div>
        <div class="stat">Total Commits (last year) <b data-count="5">0</b></div>
        <div class="stat">Total PRs <b data-count="0">0</b></div>
        <div class="stat">Total Issues <b data-count="0">0</b></div>
        <div class="stat">Contributed to (last year) <b data-count="0">0</b></div>
      </div>
      <div class="ring">
        <svg viewBox="0 0 160 160">
          <defs>
            <linearGradient id="g" x1="0" y1="0" x2="1" y2="1">
              <stop offset="0%" stop-color="#3fb950"/>
              <stop offset="100%" stop-color="#58a6ff"/>
            </linearGradient>
          </defs>
          <circle class="track" cx="80" cy="80" r="70" fill="none" stroke-width="10"/>
          <circle class="fill" cx="80" cy="80" r="70" fill="none" stroke-width="10"/>
        </svg>
        <div class="grade">C</div>
      </div>
    </div>
  </section>

  <section class="card">
    <h2>🧩 Most Used Languages</h2>
    <div class="empty">No languages data yet.</div>
  </section>

  <footer>Made with <span>♥</span> · Profile views counter placeholder</footer>
</div>

<script>
  // Role typing effect
  const roles = [
    "Full-Stack Developer",
    "AI Automation Specialist",
    "Laravel & Python Engineer",
    "UI/UX Enthusiast"
  ];
  const roleEl = document.getElementById('role');
  let r = 0, c = 0, deleting = false;
  function type() {
    const word = roles[r];
    roleEl.textContent = deleting ? word.slice(0, c--) : word.slice(0, c++);
    let delay = deleting ? 45 : 90;
    if (!deleting && c > word.length) { deleting = true; delay = 1400; }
    else if (deleting && c < 0) { deleting = false; r = (r + 1) % roles.length; c = 0; delay = 300; }
    setTimeout(type, delay);
  }
  type();

  // Icon CDN (Simple Icons, brand SVGs). "fallback" is shown if an icon is missing.
  const ICON = slug => `https://cdn.jsdelivr.net/npm/simple-icons@11/icons/${slug}.svg`;

  const groups = [
    {
      title: "Languages",
      items: [
        ["C++",         "cplusplus",    "#00599C"],
        ["Java",        "openjdk",      "#E76F00"],
        ["C#",          "csharp",       "#68217A"],
        ["Python",      "python",       "#3776AB"],
        ["PHP",         "php",          "#777BB4"],
        ["JavaScript",  "javascript",   "#B39400"],
        ["SQL",         null,           "#336791", "SQL"]
      ]
    },
    {
      title: "Web & Frameworks",
      items: [
        ["HTML5",       "html5",        "#E34F26"],
        ["CSS3",        "css3",         "#1572B6"],
        ["Laravel",     "laravel",      "#FF2D20"],
        ["Flask",       "flask",        "#3a3a3a"],
        ["WordPress",   "wordpress",    "#21759B"],
        ["MySQL",       "mysql",        "#00758F"]
      ]
    },
    {
      title: "Design & Creative",
      items: [
        ["Figma",       "figma",        "#A259FF"],
        ["Adobe XD",    "adobexd",      "#B0107A"],
        ["Photoshop",   "adobephotoshop","#001E36"],
        ["Lightroom",   "adobelightroom","#1B3A57"],
        ["Illustrator", "adobeillustrator","#4A2100"],
        ["InDesign",    "adobeindesign","#49021F"],
        ["Premiere Pro","adobepremierepro","#2A0A3A"],
        ["After Effects","adobeaftereffects","#1A0530"],
        ["Canva",       "canva",        "#00897B"]
      ]
    },
    {
      title: "Cloud & Hosting",
      items: [
        ["Google Cloud","googlecloud",  "#1A73E8"],
        ["Cloudflare",  "cloudflare",   "#C25B12"],
        ["Google Workspace","googleworkspace","#1E8E3E"],
        ["Vercel",      "vercel",       "#000000"],
        ["Netlify",     "netlify",      "#00787A"],
        ["Scaleway",    null,           "#4F0599", "SCW"]
      ]
    }
  ];

  const stack = document.getElementById('stack');
  let idx = 0;
  groups.forEach(g => {
    const t = document.createElement('div');
    t.className = 'group-title';
    t.textContent = g.title;
    stack.appendChild(t);

    const grid = document.createElement('div');
    grid.className = 'icons';
    g.items.forEach(([name, slug, color, fallback]) => {
      const el = document.createElement('div');
      el.className = 'skill';
      el.style.setProperty('--c', color);
      el.style.setProperty('--d', (idx++ * 0.12) + 's');

      const ico = document.createElement('div');
      ico.className = 'ico';

      if (slug) {
        const img = document.createElement('img');
        img.src = ICON(slug);
        img.alt = name;
        img.onerror = () => {
          img.remove();
          const s = document.createElement('span');
          s.textContent = name.slice(0, 2).toUpperCase();
          ico.appendChild(s);
        };
        ico.appendChild(img);
      } else {
        const s = document.createElement('span');
        s.textContent = fallback || name.slice(0, 2).toUpperCase();
        ico.appendChild(s);
      }

      const label = document.createElement('div');
      label.textContent = name;

      el.append(ico, label);
      grid.appendChild(el);
    });
    stack.appendChild(grid);
  });

  // Count-up stats
  document.querySelectorAll('[data-count]').forEach(el => {
    const target = +el.dataset.count;
    let n = 0;
    const step = () => {
      n = Math.min(target, n + Math.max(1, Math.ceil(target / 30)));
      el.textContent = n;
      if (n < target) requestAnimationFrame(step);
    };
    setTimeout(() => requestAnimationFrame(step), 700);
  });
</script>
</body>
</html>
