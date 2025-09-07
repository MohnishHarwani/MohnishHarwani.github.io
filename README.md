# Create a single-file academic site (index.html) with a clean left sidebar like the screenshot.
html = r"""<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Your Name — Academic Portfolio</title>
  <meta name="description" content="Academic portfolio for graduate applications: research, projects, publications, and CV." />
  <style>
    :root{
      --bg:#0f1214;
      --text:#e6e6e6;
      --muted:#9aa0a6;
      --accent:#4cc9f0;
      --card:#171a1c;
      --border:#262b2f;
      --link:#8ab4f8;
    }
    @media (prefers-color-scheme: light){
      :root{
        --bg:#ffffff;
        --text:#111418;
        --muted:#5f6b76;
        --accent:#0ea5e9;
        --card:#f7f8fa;
        --border:#e5e7eb;
        --link:#0a66c2;
      }
    }
    *{box-sizing:border-box}
    html,body{margin:0;padding:0;background:var(--bg);color:var(--text);font:16px/1.6 -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Inter,Ubuntu,"Helvetica Neue",Arial,"Apple Color Emoji","Segoe UI Emoji";}
    a{color:var(--link);text-decoration:none}
    a:hover{text-decoration:underline}
    .container{max-width:1200px;margin:0 auto;padding:0 24px 64px}
    .topbar{position:sticky;top:0;background:rgba(15,18,20,.8);backdrop-filter:saturate(180%) blur(10px);border-bottom:1px solid var(--border);z-index:10}
    @media (prefers-color-scheme: light){ .topbar{background:rgba(255,255,255,.8);} }
    .topbar-inner{display:flex;align-items:center;justify-content:space-between;gap:24px;min-height:56px}
    .brand{font-weight:700}
    .nav a{margin-left:18px;font-weight:500}
    .layout{display:grid;grid-template-columns:320px 1fr;gap:32px;margin-top:24px}
    @media (max-width:900px){ .layout{grid-template-columns:1fr} .nav{display:none} }
    .sidebar{position:sticky;top:80px;align-self:start;background:var(--card);border:1px solid var(--border);border-radius:16px;padding:24px}
    .avatar{display:block;width:180px;height:180px;border-radius:50%;object-fit:cover;margin:8px auto 16px;border:1px solid var(--border);background:#222}
    .name{font-size:1.15rem;font-weight:700;text-align:center;margin:0 0 6px}
    .bio{font-size:.95rem;color:var(--muted);text-align:center;margin:0 0 12px}
    .list{list-style:none;padding:0;margin:8px 0 0}
    .list li{display:flex;align-items:center;gap:10px;padding:8px 0;border-bottom:1px dashed var(--border)}
    .list li:last-child{border-bottom:0}
    .pill{display:inline-block;padding:8px 12px;border:1px solid var(--border);border-radius:999px;background:transparent;font-weight:600}
    .pill:hover{background:var(--border)}
    .content{min-width:0}
    h1,h2{line-height:1.25}
    h1{font-size:2rem;margin:6px 0 8px}
    h2{margin:28px 0 8px}
    .card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:24px;margin-bottom:16px}
    .kicker{color:var(--muted);text-transform:uppercase;letter-spacing:.08em;font-size:.8rem}
    .lead{font-size:1.05rem;color:var(--muted)}
    .tags{display:flex;flex-wrap:wrap;gap:8px;margin-top:8px}
    .tag{font-size:.8rem;border:1px solid var(--border);padding:4px 8px;border-radius:999px;color:var(--muted)}
    footer{margin-top:32px;color:var(--muted);font-size:.9rem}
    code{background:rgba(127,127,127,.1);padding:.15em .35em;border-radius:6px}
  </style>
</head>
<body>
  <div class="topbar">
    <div class="container topbar-inner">
      <div class="brand">Your Name / Site Title</div>
      <nav class="nav">
        <a href="#publications">Publications</a>
        <a href="#projects">Projects</a>
        <a href="#research">Research</a>
        <a href="#contact">Contact</a>
        <a href="assets/CV.pdf">CV</a>
      </nav>
    </div>
  </div>

  <div class="container layout">
    <!-- Sidebar -->
    <aside class="sidebar">
      <img class="avatar" src="assets/headshot.jpg" alt="Your Name">
      <h3 class="name">Your Sidebar Name</h3>
      <p class="bio">Short biography for the left-hand sidebar. One or two lines about interests and goals.</p>
      <ul class="list">
        <li>🌍 Earth</li>
        <li>🏛️ Red Brick University</li>
        <li>✉️ <a href="mailto:you@university.edu">you@university.edu</a></li>
        <li>🧑‍🎓 <a href="https://scholar.google.com/">Google Scholar</a></li>
        <li>🐙 <a href="https://github.com/your-username">GitHub</a></li>
        <li>💼 <a href="https://linkedin.com/in/your-handle">LinkedIn</a></li>
      </ul>
      <p style="text-align:center;margin-top:14px">
        <a class="pill" href="assets/CV.pdf">Download CV</a>
      </p>
    </aside>

    <!-- Main content -->
    <section class="content">
      <div class="card">
        <div class="kicker">Welcome</div>
        <h1>Academic Pages is a ready-to-fork template vibe</h1>
        <p class="lead">
          This single <code>index.html</code> intentionally mimics the clean, two-panel layout you showed: a left profile
          sidebar and right content panel with large headings and comfortable spacing—no Jekyll required.
        </p>
        <p>
          Replace all placeholders with your details. Put your photo at <code>assets/headshot.jpg</code> and your CV at
          <code>assets/CV.pdf</code>. You can keep a simple <code>README.md</code> for the repo view; GitHub Pages will serve
          this HTML as your website’s homepage.
        </p>
      </div>

      <div class="card" id="research">
        <h2>Research</h2>
        <p><strong>Interests.</strong> Algorithms (approximation, graph, randomized); Machine Learning (optimization, generalization).</p>
        <div class="tags">
          <span class="tag">Algorithms</span><span class="tag">ML Theory</span><span class="tag">Optimization</span>
        </div>
        <h3 style="margin-top:12px">Research Assistant — &lt;Lab, Advisor&gt; (Dates)</h3>
        <ul>
          <li>Worked on …; applied …; evaluated on …</li>
          <li>Outcome: poster / talk / preprint (<a href="#">PDF</a>)</li>
        </ul>
        <h3>Independent Study — &lt;Course/Advisor&gt; (Dates)</h3>
        <ul>
          <li>Investigated …; developed …; key result …</li>
        </ul>
      </div>

      <div class="card" id="projects">
        <h2>Projects</h2>
        <ul>
          <li><strong><a href="#">Project Name</a></strong> — one-sentence impact. Techniques/stack.</li>
          <li><strong><a href="#">Project Name</a></strong> — what you built and why it matters.</li>
        </ul>
      </div>

      <div class="card" id="publications">
        <h2>Publications & Talks</h2>
        <ul>
          <li>“<em>Title of Paper</em>,” Venue, Year. <a href="#">PDF</a> · <a href="#">Slides</a></li>
          <li>“<em>Another Work</em>,” Venue, Year.</li>
        </ul>
      </div>

      <div class="card" id="contact">
        <h2>Contact</h2>
        <p>Email: <a href="mailto:you@university.edu">you@university.edu</a></p>
        <p>GitHub: <a href="https://github.com/your-username">your-username</a></p>
        <p>LinkedIn: <a href="https://linkedin.com/in/your-handle">linkedin.com/in/your-handle</a></p>
      </div>

      <footer>© Your Name. Built as a single-file site for GitHub Pages.</footer>
    </section>
  </div>
</body>
</html>
"""
with open("/mnt/data/index.html", "w", encoding="utf-8") as f:
    f.write(html)
"/mnt/data/index.html"
