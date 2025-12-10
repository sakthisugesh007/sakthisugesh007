<!--
index.html — Ready-to-deploy single-file GitHub Pages landing page
How to use:
1. Rename this file to `index.html` and push to the `gh-pages` branch or the repository root (for user/organization pages: `username.github.io`).
2. Edit the placeholders (YOUR NAME, BIO, project cards, links).
3. Commit & push — GitHub Pages will serve this file.

Features:
- Responsive layout (mobile-first)
- Hero section with name, role, and CTAs
- Projects grid with external links
- About, Skills, Contact sections
- Simple light/dark mode toggle (no external deps)
- Clean, modern styling with CSS only
--> 

<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <meta name="description" content="Personal GitHub Pages landing page" />
  <title>YOUR NAME • Portfolio</title>

  <!-- Favicon -->
  <link rel="icon" href="data:;base64,iVBORw0KGgo=" />

  <style>
    :root{
      --bg:#0f1724; --card:#0b1220; --muted:#9aa4b2; --accent:#7c5cff; --glass:rgba(255,255,255,0.04);
      --radius:12px; --maxw:1000px; --container-padding:20px;
      color-scheme: dark;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; font-family:Inter, ui-sans-serif, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(124,92,255,0.12), transparent 10%),
                  radial-gradient(800px 400px at 90% 90%, rgba(0,200,255,0.04), transparent 12%),
                  var(--bg);
      color:#dbe7ff; -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale;
      padding:40px 16px; display:flex; justify-content:center;
    }

    .wrap{width:100%; max-width:var(--maxw)}
    header{display:flex;align-items:center;justify-content:space-between;margin-bottom:28px}

    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:52px;height:52px;border-radius:10px;background:linear-gradient(135deg,var(--accent),#00c9ff);display:flex;align-items:center;justify-content:center;font-weight:700}
    .brand h1{margin:0;font-size:16px}
    .brand p{margin:0;font-size:12px;color:var(--muted)}

    nav{display:flex;gap:12px;align-items:center}
    .btn{background:var(--glass);border:1px solid rgba(255,255,255,0.03);padding:8px 12px;border-radius:10px;font-size:14px;color:inherit;text-decoration:none}
    .ghost{background:transparent}

    main{display:grid;grid-template-columns:1fr;gap:20px}

    .hero{display:flex;gap:20px;align-items:center;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);padding:24px;border-radius:var(--radius);backdrop-filter:blur(6px)}
    .hero .left{flex:1}
    .kicker{font-size:13px;color:var(--muted);margin-bottom:8px}
    .title{font-size:28px;margin:0 0 10px}
    .lead{margin:0;color:var(--muted);line-height:1.5}
    .ctas{margin-top:16px;display:flex;gap:12px}

    .avatar{width:120px;height:120px;border-radius:16px;background:linear-gradient(135deg,#1f2937,#111827);display:flex;align-items:center;justify-content:center;font-size:28px}

    .grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
    .card{background:var(--card);padding:16px;border-radius:12px;border:1px solid rgba(255,255,255,0.02)}
    .card h3{margin:0 0 8px}
    .card p{margin:0;color:var(--muted);font-size:14px}

    footer{margin-top:18px;color:var(--muted);font-size:13px}

    /* Responsive */
    @media (max-width:900px){
      .grid{grid-template-columns:repeat(2,1fr)}
      .avatar{width:96px;height:96px}
      .title{font-size:22px}
    }
    @media (max-width:640px){
      header{flex-direction:column;align-items:flex-start;gap:12px}
      .grid{grid-template-columns:1fr}
      .hero{flex-direction:column;align-items:flex-start}
      .avatar{width:80px;height:80px}
    }

    /* Small utility styles */
    .muted{color:var(--muted)}
    .skills{display:flex;flex-wrap:wrap;gap:8px;margin-top:8px}
    .pill{padding:6px 10px;background:rgba(255,255,255,0.03);border-radius:999px;font-size:13px}

    /* Light mode (simple toggle) */
    :root.light{--bg:#f7fbff;--card:#ffffff;--muted:#51606f;--accent:#5b21b6;color-scheme:light;color:#0b1220}

    .small{font-size:13px}
    a.link{color:inherit;text-decoration:underline}

    /* subtle focus outline */
    a:focus{outline:2px solid rgba(124,92,255,0.18);outline-offset:3px}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="logo">YS</div>
        <div>
          <h1>YOUR NAME</h1>
          <p class="muted">Full‑stack developer • Open-source enthusiast</p>
        </div>
      </div>

      <nav>
        <a class="btn ghost" href="#projects">Projects</a>
        <a class="btn" href="#contact">Contact</a>
        <button id="themeToggle" class="btn ghost" aria-label="Toggle light/dark">Toggle</button>
      </nav>
    </header>

    <main>
      <section class="hero">
        <div class="left">
          <div class="kicker">Hi — I'm</div>
          <h2 class="title">YOUR NAME — building useful things on the web.</h2>
          <p class="lead">I'm a software engineer focused on building scalable web apps and delightful developer tools. I enjoy clean code, well-tested systems, and fast feedback loops. Currently: building a blood-donation platform (link in projects).</p>

          <div class="ctas">
            <a class="btn" href="#projects">See projects</a>
            <a class="btn ghost" href="https://github.com/YOUR_USERNAME" target="_blank" rel="noopener">GitHub profile</a>
          </div>

          <div style="margin-top:14px">
            <div class="small muted">Top skills</div>
            <div class="skills">
              <div class="pill">React</div>
              <div class="pill">Node.js</div>
              <div class="pill">Express</div>
              <div class="pill">MongoDB</div>
              <div class="pill">Docker</div>
            </div>
          </div>
        </div>

        <div class="avatar" aria-hidden="true">YS</div>
      </section>

      <section id="projects" style="display:grid;grid-template-columns:1fr;gap:12px">
        <h3 style="margin:8px 0 6px">Selected projects</h3>
        <div class="grid">
          <article class="card">
            <h3>Blood Donation Platform</h3>
            <p class="muted">Full-stack app (React, Node, Express, MongoDB) — user/admin dashboards, authentication, contact form, geolocation features.</p>
            <p style="margin-top:10px"><a class="link" href="https://github.com/YOUR_USERNAME/blood-donation">github.com/YOUR_USERNAME/blood-donation</a></p>
          </article>

          <article class="card">
            <h3>Mini Quiz Creator</h3>
            <p class="muted">Next.js app for creating, sharing, and taking quizzes — SSR, performance-focused.</p>
            <p style="margin-top:10px"><a class="link" href="#">Repository link</a></p>
          </article>

          <article class="card">
            <h3>AI Tourist Tracker</h3>
            <p class="muted">React + Node.js project with geofencing and AI trip suggestions.</p>
            <p style="margin-top:10px"><a class="link" href="#">Repository link</a></p>
          </article>
        </div>
      </section>

      <section style="display:grid;grid-template-columns:1fr 320px;gap:16px;margin-top:6px;align-items:start">
        <div class="card">
          <h3>About</h3>
          <p class="muted">I'm YOUR NAME — currently working on web apps and improving developer UX. I like testing, clean architecture, and short feedback loops. I mentor peers and enjoy writing short technical notes.</p>

          <h4 style="margin-top:12px">Work</h4>
          <p class="muted small">Open to collaboration, freelance, and hiring for mid/senior roles. Email: <a class="link" href="mailto:you@example.com">you@example.com</a></p>
        </div>

        <aside class="card">
          <h3>Contact</h3>
          <p class="muted small">Want to work together or ask about a project?</p>
          <p style="margin-top:10px"><a class="btn" href="mailto:you@example.com">Email me</a></p>

          <h4 style="margin-top:14px">Social</h4>
          <p class="muted small"><a class="link" href="https://twitter.com/YOUR_HANDLE">Twitter</a> • <a class="link" href="https://linkedin.com/in/YOUR_PROFILE">LinkedIn</a> • <a class="link" href="https://github.com/YOUR_USERNAME">GitHub</a></p>
        </aside>
      </section>

      <footer>
        <div class="small muted">Made with ❤️ • Customize this page in <code>index.html</code></div>
      </footer>
    </main>
  </div>

  <script>
    // simple light/dark toggle — stores preference in localStorage
    const btn = document.getElementById('themeToggle');
    const root = document.documentElement;
    function setMode(mode){
      if(mode === 'light') root.classList.add('light'); else root.classList.remove('light');
      localStorage.setItem('theme', mode);
    }
    btn.addEventListener('click', ()=>{
      const isLight = root.classList.contains('light');
      setMode(isLight ? 'dark' : 'light');
    });
    // init from preference or system
    const saved = localStorage.getItem('theme');
    if(saved) setMode(saved); else {
      const prefersLight = window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches;
      setMode(prefersLight ? 'light' : 'dark');
    }
  </script>
</body>
</html>
