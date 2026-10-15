# Panduan Belajar & Implementasi: Web Landing Page Modern

Panduan ini dirancang untuk membimbing Anda membuat landing page modern dari awal menggunakan HTML5 semantik dan CSS murni (*vanilla CSS*).

---

## 📋 Daftar Isi
1. [Langkah 1: Setup Kerangka HTML5 & Tag Semantik](#langkah-1-setup-kerangka-html5--tag-semantik)
2. [Langkah 2: Reset CSS & Konfigurasi Variabel Warna](#langkah-2-reset-css--konfigurasi-variabel-warna)
3. [Langkah 3: Membuat Navbar Flexbox](#langkah-3-membuat-navbar-flexbox)
4. [Langkah 4: Membangun Hero Section](#langkah-4-membangun-hero-section)
5. [Langkah 5: Membuat Grid Card Layanan Responsif](#langkah-5-membuat-grid-card-layanan-responsif)
6. [Langkah 6: Menambahkan Animasi & Hover Efek Halus](#langkah-6-menambahkan-animasi--hover-efek-halus)
7. [Pengujian & Verifikasi](#pengujian--verifikasi)

---

## Langkah 1: Setup Kerangka HTML5 & Tag Semantik

Gunakan tag semantik untuk meningkatkan aksesibilitas dan SEO:
- `<header>`: Pembungkus navigasi utama.
- `<nav>`: Wadah menu navigasi.
- `<main>`: Konten utama halaman.
- `<section>`: Membagi konten per topik (Hero, Services).
- `<article>`: Wadah konten independen (Card).

```html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Layanan Digital</title>
</head>
<body>
  <header>
    <nav class="navbar">...</nav>
  </header>
  <main>
    <section class="hero-section">...</section>
    <section class="services-section">
      <div class="card-grid">
        <article class="card">...</article>
      </div>
    </section>
  </main>
</body>
</html>
```

---

## Langkah 2: Reset CSS & Konfigurasi Variabel Warna

Tulis deklarasi variabel di selector `:root` agar mudah dikustomisasi dari satu tempat, lalu reset margin dan box-sizing.

```css
:root {
  --primary-color: #3b82f6;
  --primary-dark: #1d4ed8;
  --text-dark: #0f172a;
  --text-muted: #64748b;
  --bg-light: #f8fafc;
  --bg-card: #ffffff;
  --border-color: #e2e8f0;
  --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
  --shadow-hover: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
  --transition-smooth: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

/* CSS Reset Sederhana */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: system-ui, sans-serif;
  background-color: var(--bg-light);
  color: var(--text-dark);
}
```

---

## Langkah 3: Membuat Navbar Flexbox

Gunakan **Flexbox** dengan properti `justify-content: space-between` agar logo otomatis berada di sisi kiri dan daftar tautan berada di sisi kanan.

```css
.navbar {
  max-width: 1100px;
  margin: 0 auto;
  padding: 1rem 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 1.5rem;
}
```

---

## Langkah 4: Membangun Hero Section

Buat hero section dengan teks rata tengah (`text-align: center`) dan batasi lebar kontainer (`max-width: 800px`) agar teks nyaman dibaca di layar lebar.

```css
.hero-section {
  text-align: center;
  padding: 5rem 1.5rem 3.5rem;
  max-width: 800px;
  margin: 0 auto;
}

.hero-section h1 {
  font-size: 2.75rem;
  margin-bottom: 1rem;
}
```

---

## Langkah 5: Membuat Grid Card Layanan Responsif

Terapkan prinsip **Mobile-First**:
1. Di layar ponsel (default): card otomatis berbaris ke bawah (`grid-template-columns: 1fr`).
2. Di layar tablet/desktop ($\ge 768\text{px}$): card dibagi menjadi 3 kolom sejajar (`grid-template-columns: repeat(3, 1fr)`).

```css
/* Tampilan Mobile */
.card-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

/* Tampilan Tablet / Laptop / Desktop */
@media (min-width: 768px) {
  .card-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

---

## Langkah 6: Menambahkan Animasi & Hover Efek Halus

Agar interaksi terasa premium dan lembut:
1. Pasang `transition: var(--transition-smooth)` pada state normal `.card`.
2. Gunakan `transform: translateY(-8px)` dan bayangan lebih tebal pada selector `.card:hover`.

```css
.card {
  background-color: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  padding: 2rem;
  box-shadow: var(--shadow-sm);
  transition: var(--transition-smooth);
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: var(--shadow-hover);
  border-color: rgba(59, 130, 246, 0.4);
}
```

---

## 🔍 Pengujian & Verifikasi

1. **Uji Responsivitas**:
   - Tekan `Ctrl + Shift + M` (atau `Cmd + Option + M` di Mac) di browser untuk membuka mode simulasi mobile.
   - Pastikan card tersusun 1 kolom vertikal saat lebar layar di bawah $768\text{px}$.
2. **Uji Efek Hover**:
   - Arahkan kursor ke tiap card; amati apakah kartu terangkat ke atas setinggi $8\text{px}$ secara mulus tanpa efek patah-patah.
