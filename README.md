<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Layanan Digital Kreatif</title>
  <style>
    /* 1. RESET CSS & SETUP VARIABEL WARNA */
    :root {
      --primary-color: #3b82f6;
      --primary-dark: #1d4ed8;
      --secondary-color: #0f172a;
      --text-muted: #64748b;
      --bg-light: #f8fafc;
      --bg-card: #ffffff;
      --border-color: #e2e8f0;
      --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
      --shadow-hover: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.04);
      --transition-smooth: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
      background-color: var(--bg-light);
      color: var(--secondary-color);
      line-height: 1.6;
    }

    /* 2. HEADER & NAVBAR (FLEXBOX) */
    header {
      background-color: var(--bg-card);
      border-bottom: 1px solid var(--border-color);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .navbar {
      max-width: 1100px;
      margin: 0 auto;
      padding: 1rem 1.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .brand-logo {
      font-size: 1.35rem;
      font-weight: 700;
      color: var(--primary-color);
      text-decoration: none;
      letter-spacing: -0.5px;
    }

    .nav-links {
      display: flex;
      list-style: none;
      gap: 1.5rem;
    }

    .nav-links a {
      text-decoration: none;
      color: var(--secondary-color);
      font-weight: 500;
      font-size: 0.95rem;
      transition: color 0.2s ease;
    }

    .nav-links a:hover {
      color: var(--primary-color);
    }

    /* 3. HERO SECTION (TEKS RATA TENGAH) */
    .hero-section {
      text-align: center;
      padding: 5rem 1.5rem 3.5rem;
      max-width: 800px;
      margin: 0 auto;
    }

    .hero-section h1 {
      font-size: 2.75rem;
      font-weight: 800;
      color: var(--secondary-color);
      line-height: 1.2;
      margin-bottom: 1rem;
    }

    .hero-section p {
      font-size: 1.15rem;
      color: var(--text-muted);
      margin-bottom: 2rem;
    }

    .btn-cta {
      display: inline-block;
      background-color: var(--primary-color);
      color: #ffffff;
      padding: 0.85rem 1.75rem;
      border-radius: 8px;
      text-decoration: none;
      font-weight: 600;
      transition: var(--transition-smooth);
    }

    .btn-cta:hover {
      background-color: var(--primary-dark);
      transform: translateY(-2px);
    }

    /* 4. SERVICES SECTION & CARDS */
    .services-section {
      max-width: 1100px;
      margin: 0 auto;
      padding: 3rem 1.5rem 5rem;
    }

    .section-title {
      text-align: center;
      font-size: 2rem;
      margin-bottom: 2.5rem;
    }

    .card-grid {
      display: grid;
      grid-template-columns: 1fr; /* Default mobile: 1 kolom menumpuk */
      gap: 2rem;
    }

    .card {
      background-color: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      padding: 2rem;
      box-shadow: var(--shadow-sm);
      /* Transisi efek hover */
      transition: var(--transition-smooth);
      display: flex;
      flex-direction: column;
      gap: 0.75rem;
    }

    /* 5. HOVER EFFECT HALUS PADA CARD */
    .card:hover {
      transform: translateY(-8px);
      box-shadow: var(--shadow-hover);
      border-color: rgba(59, 130, 246, 0.4);
    }

    .card-badge {
      display: inline-block;
      width: fit-content;
      font-size: 0.75rem;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: var(--primary-color);
      background: rgba(59, 130, 246, 0.1);
      padding: 0.25rem 0.65rem;
      border-radius: 9999px;
    }

    .card h3 {
      font-size: 1.35rem;
      color: var(--secondary-color);
    }

    .card p {
      color: var(--text-muted);
      font-size: 0.95rem;
      line-height: 1.5;
    }

    /* Tampilan Tablet & Desktop (Layar >= 768px) */
    @media (min-width: 768px) {
      .card-grid {
        grid-template-columns: repeat(3, 1fr); /* 3 Card sejajar */
      }

      .hero-section {
        padding: 6rem 1.5rem 4rem;
      }
    }
  </style>
</head>
<body>

  <!-- HEADER DENGAN TAG SEMANTIK & FLEXBOX NAVBAR -->
  <header>
    <nav class="navbar" aria-label="Navigasi Utama">
      <a href="#" class="brand-logo">DevStudio.</a>
      <ul class="nav-links">
        <li><a href="#beranda">Beranda</a></li>
        <li><a href="#layanan">Layanan</a></li>
        <li><a href="#kontak">Kontak</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <!-- HERO SECTION (TEKS RATA TENGAH) -->
    <section id="beranda" class="hero-section">
      <h1>Solusi Desain & Pengembangan Web Modern</h1>
      <p>Membantu bisnis membangun identitas digital yang profesional, cepat, dan responsif di setiap perangkat.</p>
      <a href="#layanan" class="btn-cta">Mulai Sekarang</a>
    </section>

    <!-- SECTION CARD LAYANAN -->
    <section id="layanan" class="services-section">
      <h2 class="section-title">Layanan Unggulan Kami</h2>

      <div class="card-grid">
        <!-- Card 1 -->
        <article class="card">
          <span class="card-badge">Desain</span>
          <h3>UI/UX Design</h3>
          <p>Menciptakan antarmuka aplikasi yang intuitif, estetis, dan memberikan pengalaman pengguna terbaik.</p>
        </article>

        <!-- Card 2 -->
        <article class="card">
          <span class="card-badge">Coding</span>
          <h3>Web Development</h3>
          <p>Membangun situs web cepat, aman, dan dirancang dengan standar kode modern yang terstruktur.</p>
        </article>

        <!-- Card 3 -->
        <article class="card">
          <span class="card-badge">Performa</span>
          <h3>SEO & Optimasi</h3>
          <p>Mengoptimalkan performa kecepatan situs dan peringkat pencarian agar mudah ditemukan di Google.</p>
        </article>
      </div>
    </section>
  </main>

</body>
</html>
