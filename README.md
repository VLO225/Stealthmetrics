<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>VLO225 Archives - Charts</title>
  <style>
    :root {
      --bg-color: #f4f1ea;
      --card-bg: #ffffff;
      --text-primary: #2c2926;
      --text-secondary: #595550;
      --accent: #8c3b2b;
      --border: #dcd6cc;
    }
    body {
      font-family: Georgia, "Times New Roman", serif;
      background: var(--bg-color);
      color: var(--text-primary);
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 960px;
      margin: 0 auto;
    }
    header { text-align:center; margin-bottom:30px; }
    h1 { margin: 0; font-size: 2rem; }
    .gallery { display: grid; gap: 24px; grid-template-columns: 1fr; }
    .card {
      background: var(--card-bg);
      border: 1px solid var(--border);
      padding: 18px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.05);
    }
    .card h2 { margin: 0 0 8px 0; font-size: 1.2rem; }
    .thumb {
      display: block;
      max-width: 100%;
      height: auto;
      cursor: zoom-in;
      box-shadow: 0 2px 6px rgba(0,0,0,0.08);
      transition: transform .15s;
    }
    .thumb:hover { transform: scale(1.01); }
    /* Lightbox */
    #lightbox {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(12,12,12,0.9);
      align-items: center;
      justify-content: center;
      z-index: 9999;
      cursor: zoom-out;
    }
    #lightbox.open { display: flex; }
    #lightbox img {
      max-width: 95%;
      max-height: 95%;
      box-shadow: 0 0 30px rgba(0,0,0,0.6);
    }
    .caption { color: var(--text-secondary); font-size: .95rem; margin-top:8px;}
    footer { text-align:center; margin-top:30px; color:var(--text-secondary); font-size:.9rem; }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>VLO225 ARCHIVES</h1>
      <div class="caption">Defense Analysis • Program Tracking • OSINT</div>
    </header>

    <section class="gallery">
      <article class="card">
        <h2>F-35 Program Timeline & Delivery Schedule</h2>
        <p class="caption">Comprehensive breakdown of Software Blocks, Hardware Generations, and Production Lots.</p>
        <img class="thumb" src="f35.png" alt="F-35 Timeline Chart" data-full="f35.png">
      </article>

      <article class="card">
        <h2>Aircraft Cost Per Flight Hour (2024 vs 2025)</h2>
        <p class="caption">DoD Component User Rates analysis.</p>
        <img class="thumb" src="rcpfh.png" alt="RCPFH Cost Analysis" data-full="rcpfh.png">
      </article>

      <article class="card">
        <h2>U.S. Navy LCS Deployments (2022-2025)</h2>
        <p class="caption">Sustained deployment tracking for Independence and Freedom class variants.</p>
        <img class="thumb" src="lcs.jpeg" alt="LCS Deployment Timeline" data-full="lcs.jpeg">
      </article>
    </section>

    <footer>&copy; 2025 VLO225. All rights reserved.</footer>
  </div>

  <div id="lightbox" aria-hidden="true" role="dialog">
    <img id="lightbox-img" src="" alt="Expanded chart view">
  </div>

  <script>
    // Safe, non-inline JS — works when opening index.html locally or via GitHub Pages
    (function () {
      const lightbox = document.getElementById('lightbox');
      const lightboxImg = document.getElementById('lightbox-img');

      function openLightbox(src, alt) {
        lightboxImg.src = src;
        lightboxImg.alt = alt || 'Full-size image';
        lightbox.classList.add('open');
        lightbox.setAttribute('aria-hidden', 'false');
        // trap focus if needed (simple)
        document.addEventListener('keydown', onKeyDown);
      }

      function closeLightbox() {
        lightbox.classList.remove('open');
        lightboxImg.src = '';
        lightbox.setAttribute('aria-hidden', 'true');
        document.removeEventListener('keydown', onKeyDown);
      }

      function onKeyDown(e) {
        if (e.key === 'Escape') closeLightbox();
      }

      // Click thumbnails
      document.querySelectorAll('.thumb').forEach(img => {
        img.addEventListener('click', function (ev) {
          const src = img.dataset.full || img.src;
          const alt = img.alt || '';
          openLightbox(src, alt);
        });
      });

      // Close when clicking overlay (but not when clicking image)
      lightbox.addEventListener('click', function (ev) {
        if (ev.target === lightbox) closeLightbox();
      });

      // Also close when clicking image (optional): if you prefer clicking the image to do nothing, remove this handler
      lightboxImg.addEventListener('click', function (ev) {
        // Prevent the click from bubbling to the overlay which would close it
        ev.stopPropagation();
      });
    })();
  </script>
</body>
</html>
