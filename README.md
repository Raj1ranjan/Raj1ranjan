<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>STUDIO / RANJAN</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-primary: #0B0C0E;
      --bg-surface: #121418;
      --bg-hover: #171A20;
      --border: #23272F;
      --text-main: #F3F4F6;
      --text-muted: #8E95A2;
      --accent-amber: #F59E0B;
      --bayer-r: #EF4444;
      --bayer-g: #10B981;
      --bayer-b: #3B82F6;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background-color: var(--bg-primary);
      color: var(--text-main);
      font-family: 'Inter', -apple-system, sans-serif;
      line-height: 1.65;
      -webkit-font-smoothing: antialiased;
      background-image: radial-gradient(#1D2028 1px, transparent 1px);
      background-size: 24px 24px;
    }

    .container {
      max-width: 820px;
      margin: 0 auto;
      padding: 4rem 1.5rem;
    }

    /* Header & Bayer Motif */
    header {
      border-bottom: 1px solid var(--border);
      padding-bottom: 2.5rem;
      margin-bottom: 3rem;
    }

    .brand-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 1.5rem;
    }

    .brand-title {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.9rem;
      letter-spacing: 0.14em;
      font-weight: 500;
      color: var(--text-main);
    }

    .bayer-dots {
      display: grid;
      grid-template-columns: repeat(2, 6px);
      gap: 3px;
    }
    .bayer-dots span { width: 6px; height: 6px; border-radius: 1px; }
    .dot-r { background: var(--bayer-r); }
    .dot-g { background: var(--bayer-g); }
    .dot-b { background: var(--bayer-b); }

    h1 {
      font-size: 2.25rem;
      font-weight: 600;
      letter-spacing: -0.03em;
      margin-bottom: 1rem;
      color: #FFFFFF;
    }

    .bio {
      color: var(--text-muted);
      font-size: 1.05rem;
      max-width: 65ch;
      margin-bottom: 0.75rem;
    }

    /* Section Headings */
    .section-label {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.78rem;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--text-muted);
      margin-bottom: 1.25rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }
    .section-label::after {
      content: "";
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    section { margin-bottom: 3.5rem; }

    /* Cards & Selected Work */
    .card {
      background: var(--bg-surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 1.5rem;
      margin-bottom: 1rem;
      transition: border-color 0.2s ease, background 0.2s ease;
    }
    .card:hover {
      border-color: #363C48;
      background: var(--bg-hover);
    }

    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 0.35rem;
    }

    .card-title {
      font-size: 1.15rem;
      font-weight: 600;
      color: #FFFFFF;
    }
    .card-index {
      font-family: 'JetBrains Mono', monospace;
      color: var(--accent-amber);
      font-size: 0.9rem;
      margin-right: 0.4rem;
    }

    .tech-line {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.8rem;
      color: var(--text-muted);
      margin-bottom: 0.9rem;
    }

    .card p {
      color: #D1D5DB;
      font-size: 0.95rem;
      margin-bottom: 0.85rem;
    }

    ul.clean-list {
      list-style: none;
      margin-bottom: 1rem;
    }
    ul.clean-list li {
      position: relative;
      padding-left: 1.15rem;
      font-size: 0.92rem;
      color: var(--text-muted);
      margin-bottom: 0.35rem;
    }
    ul.clean-list li::before {
      content: "›";
      position: absolute;
      left: 0;
      color: var(--accent-amber);
      font-family: 'JetBrains Mono', monospace;
    }

    .status-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.45rem;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.75rem;
      color: var(--accent-amber);
      background: rgba(245, 158, 11, 0.1);
      border: 1px solid rgba(245, 158, 11, 0.25);
      padding: 0.25rem 0.6rem;
      border-radius: 4px;
    }
    .status-dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: var(--accent-amber);
    }

    .repo-link {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.82rem;
      color: var(--text-main);
      text-decoration: none;
      border-bottom: 1px solid var(--border);
      padding-bottom: 2px;
      transition: border-color 0.2s, color 0.2s;
    }
    .repo-link:hover {
      color: var(--accent-amber);
      border-color: var(--accent-amber);
    }

    /* Telemetry Box for Experimental Results */
    .telemetry-box {
      background: rgba(16, 185, 129, 0.06);
      border: 1px solid rgba(16, 185, 129, 0.25);
      border-radius: 6px;
      padding: 1rem 1.15rem;
      margin-top: 1rem;
    }
    .telemetry-metrics {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
      margin-bottom: 0.5rem;
    }
    .metric-val {
      font-family: 'JetBrains Mono', monospace;
      font-size: 1.25rem;
      font-weight: 500;
      color: var(--bayer-g);
      display: block;
    }
    .metric-label {
      font-size: 0.8rem;
      color: #D1D5DB;
    }
    .telemetry-note {
      font-size: 0.78rem;
      color: var(--text-muted);
      font-style: italic;
    }

    /* Tech Grid */
    .tech-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 1rem;
    }
    .tech-cell {
      background: var(--bg-surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 1.1rem 1.25rem;
    }
    .tech-cell h3 {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.78rem;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 0.4rem;
    }
    .tech-cell p {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.88rem;
      color: var(--text-main);
    }

    /* Footer */
    footer {
      border-top: 1px solid var(--border);
      padding-top: 2rem;
      text-align: center;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.8rem;
      color: var(--text-muted);
    }
    footer strong {
      display: block;
      color: var(--text-main);
      letter-spacing: 0.14em;
      font-weight: 500;
      margin-bottom: 0.25rem;
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand-bar">
        <span class="brand-title">STUDIO / RANJAN</span>
        <!-- 2x2 RGGB Bayer Filter Matrix -->
        <div class="bayer-dots" title="RGGB Sensor Matrix">
          <span class="dot-r"></span><span class="dot-g"></span>
          <span class="dot-g"></span><span class="dot-b"></span>
        </div>
      </div>
      <h1>Engineering through curiosity.</h1>
      <p class="bio">I'm a Computer Science student interested in understanding how technology works — and exploring what I can build with it.</p>
      <p class="bio">My work and experiments sit around software engineering, computational photography, artificial intelligence, and Linux.</p>
    </header>

    <section>
      <div class="section-label">Selected Work</div>

      <article class="card">
        <div class="card-header">
          <h2 class="card-title"><span class="card-index">01 —</span>Nokia Camera Lab</h2>
          <span class="status-badge"><span class="status-dot"></span>Active development · Local project</span>
        </div>
        <div class="tech-line">Android · Kotlin · Camera2 · RAW Photography</div>
        <p>An experimental camera application for the Nokia 6, exploring a Pixel-inspired mobile photography experience.</p>
        <ul class="clean-list">
          <li>Built a working Camera2-based viewfinder.</li>
          <li>Implemented JPEG capture and DNG + JPEG saving.</li>
          <li>Explored manual camera controls and RAW capture.</li>
          <li>Developed the foundation for a more computational approach to mobile photography.</li>
        </ul>
      </article>

      <article class="card">
        <div class="card-header">
          <h2 class="card-title"><span class="card-index">02 —</span>Kumo</h2>
          <a href="#" class="repo-link">View repository ↗</a>
        </div>
        <div class="tech-line">Local AI · Personal Assistant</div>
        <p>An exploration of personal AI assistants, with an interest in local execution, useful memory, and greater user control.</p>
      </article>

      <article class="card">
        <div class="card-header">
          <h2 class="card-title"><span class="card-index">03 —</span>LocalMind AI</h2>
          <a href="#" class="repo-link">View repository ↗</a>
        </div>
        <div class="tech-line">Python · Local AI</div>
        <p>Exploring privacy-conscious AI tools and practical local workflows.</p>
      </article>
    </section>

    <section>
      <div class="section-label">Engineering Work &amp; Experiments</div>

      <article class="card">
        <div class="card-header">
          <h2 class="card-title">RAW Burst Processing</h2>
        </div>
        <div class="tech-line">Python · RawPy · OpenCV · 16-bit Linear RAW</div>
        <p>Developed a Python-based experimental pipeline using RawPy and OpenCV to process multiple DNG photographs.</p>
        <ul class="clean-list">
          <li>Processed 16-bit linear RAW image data.</li>
          <li>Implemented image alignment using ECC-based registration.</li>
          <li>Experimented with multi-frame fusion for noise reduction.</li>
          <li>Evaluated image quality using noise measurements and signal-to-noise comparisons.</li>
        </ul>
      </article>

      <article class="card">
        <div class="card-header">
          <h2 class="card-title">Bayer Image Processing</h2>
        </div>
        <div class="tech-line">Colour-Plane Separation · Motion-Aware Fusion</div>
        <p>Built an experimental Bayer-processing pipeline with separate colour-plane processing and motion-aware fusion.</p>
        <ul class="clean-list">
          <li>Worked with individual Bayer colour planes.</li>
          <li>Tested alignment and fusion on static and moving scenes.</li>
          <li>Developed noise-aware sample rejection.</li>
          <li>Evaluated fusion quality against individual input frames.</li>
        </ul>

        <div class="telemetry-box">
          <div class="telemetry-metrics">
            <div>
              <span class="metric-val">~1.75× SNR</span>
              <span class="metric-label">Improvement in tested fusion scenario</span>
            </div>
            <div>
              <span class="metric-val">~93.5%</span>
              <span class="metric-label">Rejection of injected moving-object samples</span>
            </div>
          </div>
          <div class="telemetry-note">These are results from controlled experiments, not universal performance claims.</div>
        </div>
      </article>
    </section>

    <section>
      <div class="section-label">Technology</div>
      <div class="tech-grid">
        <div class="tech-cell">
          <h3>Languages</h3>
          <p>Python · Kotlin · Java</p>
        </div>
        <div class="tech-cell">
          <h3>Platforms</h3>
          <p>Linux · Fedora · Android</p>
        </div>
        <div class="tech-cell">
          <h3>Tools &amp; Libraries</h3>
          <p>Git · GitHub · VS Code · Gradle · OpenCV · RawPy</p>
        </div>
      </div>
    </section>

    <section>
      <div class="section-label">Currently Exploring</div>
      <div class="card">
        <ul class="clean-list" style="margin-bottom: 0;">
          <li>Improving RAW burst fusion and motion handling.</li>
          <li>Refining the Nokia Camera Lab application.</li>
          <li>Investigating computational photography algorithms.</li>
          <li>Developing Kumo as a local AI assistant.</li>
          <li>Learning more about systems and software engineering.</li>
        </ul>
      </div>
    </section>

    <footer>
      <strong>STUDIO / RANJAN</strong>
      <span>Experiment. Understand. Build.</span>
    </footer>
  </div>
</body>
</html>
