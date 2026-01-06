<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>KRISH-PATEL — Demo</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header class="nav container" role="banner">
    <a class="brand" href="#">
      <img src="https://via.placeholder.com/44" alt="logo" class="avatar" />
      <span>KRISH-PATEL</span>
    </a>

    <nav class="nav-links" id="primary-nav" aria-label="Primary navigation">
      <a href="#features">Features</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
      <a class="btn" href="#contact">Get in touch</a>
    </nav>

    <button class="btn ghost menu-btn" id="menuBtn" aria-expanded="false" aria-controls="primary-nav" aria-label="Toggle menu">☰</button>
  </header>

  <main id="main" class="container">
    <section class="hero">
      <div class="hero-inner">
        <div class="copy">
          <h1>Build beautiful UIs faster</h1>
          <p>Lightweight, responsive components and utilities to kickstart your site. Includes dark-mode support and accessible defaults.</p>

          <p>
            <a class="btn" href="#projects">See examples</a>
            <a class="btn btn-outline" href="#features">Learn more</a>
          </p>

          <div class="mt-2 row" aria-hidden="true">
            <div class="card tiny">
              <strong>Performance</strong>
              <div class="muted">Small CSS footprint</div>
            </div>
            <div class="card tiny">
              <strong>Accessible</strong>
              <div class="muted">Focus-visible, semantic HTML</div>
            </div>
          </div>
        </div>

        <div class="media">
          <div class="card skeleton" style="height:220px;display:flex;align-items:center;justify-content:center;">
            <div style="text-align:center;">
              <img src="https://via.placeholder.com/240x120" alt="demo" style="max-width:100%;border-radius:8px">
              <div style="margin-top:8px;color:var(--muted)">Preview screenshot</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="projects" class="mt-2">
      <h2>Projects</h2>
      <p>Responsive examples using the base styles and components.</p>

      <div class="grid mt-2">
        <article class="card">
          <h3>Project Alpha</h3>
          <p>Modular card layout with hover lift and drop shadow.</p>
          <p><a class="btn" href="#">View</a></p>
        </article>

        <article class="card">
          <h3>Project Beta</h3>
          <p>Forms and inputs designed for clarity and accessibility.</p>
          <p><a class="btn" href="#">View</a></p>
        </article>

        <article class="card">
          <h3>Project Gamma</h3>
          <p>Dark-mode aware styles and color variables to customize.</p>
          <p><a class="btn" href="#">View</a></p>
        </article>
      </div>
    </section>

    <section id="contact" class="mt-2">
      <h2>Contact</h2>
      <p>Send a quick message — this form uses minimal markup and our input styles.</p>

      <form class="card mt-1" style="max-width:720px" action="#" method="post" aria-label="Contact form">
        <div class="form-row">
          <label style="flex:1">
            <div class="label-title">Name</div>
            <input class="input" name="name" type="text" placeholder="Your name" required>
          </label>
          <label style="flex:1">
            <div class="label-title">Email</div>
            <input class="input" name="email" type="email" placeholder="you@example.com" required>
          </label>
        </div>

        <label style="display:block;margin-top:12px">
          <div class="label-title">Message</div>
          <textarea class="input" name="message" rows="5" placeholder="Tell me about your project..." required></textarea>
        </label>

        <div style="margin-top:12px">
          <button type="submit" class="btn">Send message</button>
          <button type="reset" class="btn ghost" style="margin-left:8px">Reset</button>
        </div>
      </form>
    </section>

    <footer class="footer mt-2">
      <small>© <time datetime="2026">2026</time> KRISH-PATEL • Built with simple CSS</small>
    </footer>
  </main>

  <script>
    // mobile menu toggle
    (function(){
      const btn = document.getElementById('menuBtn');
      const nav = document.getElementById('primary-nav');
      if(!btn || !nav) return;
      btn.addEventListener('click', () => {
        const open = btn.getAttribute('aria-expanded') === 'true';
        btn.setAttribute('aria-expanded', String(!open));
        nav.style.display = open ? '' : 'flex';
        if(!open){
          nav.style.flexDirection = 'column';
          nav.style.position = 'absolute';
          nav.style.right = '1rem';
          nav.style.top = '64px';
          nav.style.background = 'var(--card)';
          nav.style.padding = '0.6rem';
          nav.style.borderRadius = '8px';
          nav.style.boxShadow = 'var(--shadow-md)';
        } else {
          nav.style.position = '';
          nav.style.right = '';
          nav.style.top = '';
        }
      });

      // initialize for small screens
      function init(){
        if(window.innerWidth <= 720){
          nav.style.display = 'none';
          btn.style.display = 'inline-flex';
        } else {
          nav.style.display = '';
          btn.style.display = 'none';
          btn.setAttribute('aria-expanded','false');
        }
      }
      init();
      window.addEventListener('resize', init);
    })();
  </script>
</body>
</html>
