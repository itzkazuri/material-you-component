# 🎨 Material You CSS

[English](README.md) | **Bahasa Indonesia**

> Implementasi CSS mandiri yang ringan untuk [Material Design 3 (Material You)](https://m3.material.io/) — tinggal import, langsung pakai.

[![License: MIT](https://img.shields.io/badge/License-MIT-purple.svg)](LICENSE)
[![CSS Only](https://img.shields.io/badge/CSS-Only-1e88e5.svg)]()
[![Material Design 3](https://img.shields.io/badge/Material-Design%203-6750A4.svg)](https://m3.material.io/)
[![GitHub](https://img.shields.io/badge/GitHub-hiratazx%2Fmaterial--you--css-181717?logo=github)](https://github.com/hiratazx/material-you-css)

> **⚠️ Disclaimer:** Proyek ini adalah **implementasi CSS mandiri** dan **tidak berafiliasi dengan, didukung oleh, atau disponsori oleh Google LLC**. "Material Design", "Material You", dan merek dagang terkait adalah milik Google LLC. Panduan desain direferensikan dari [m3.material.io](https://m3.material.io/).

---

## ✨ Fitur

- 🎨 **Design Tokens MD3 Lengkap** — warna, tipografi, shape, motion, elevation
- 🌙 **Dark Mode Otomatis** via `prefers-color-scheme` + class manual `.md-dark`
- ⚡ **Zero Dependencies** — murni CSS, tidak butuh JavaScript untuk styling
- 📦 **Satu File** — cukup satu import, selesai
- ♿ **Aksesibel** — focus states, disabled states, dan state layers sesuai spesifikasi
- 🔧 **Sepenuhnya Customizable** — semua nilai dieksposs sebagai CSS Variables

---

## 🚀 Instalasi

### CDN (jsDelivr) — Disarankan

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/hiratazx/material-you-css@latest/material-you.css">
```

### Download & gunakan secara lokal

```html
<link rel="stylesheet" href="material-you.css">
```

### `@import` di CSS

```css
@import url('https://cdn.jsdelivr.net/gh/hiratazx/material-you-css@latest/material-you.css');
```

---

## 📦 Daftar Komponen

| Komponen | Class Utama |
|---|---|
| Buttons | `.md-btn`, `.md-btn-filled`, `.md-btn-tonal`, `.md-btn-outlined`, `.md-btn-text`, `.md-btn-elevated` |
| FAB | `.md-fab`, `.md-fab-small`, `.md-fab-large` |
| Icon Button | `.md-icon-btn`, `.md-icon-btn-filled`, `.md-icon-btn-tonal`, `.md-icon-btn-outlined` |
| Text Fields | `.md-text-field`, `.md-text-field-filled`, `.md-text-field-outlined` |
| Cards | `.md-card`, `.md-card-elevated`, `.md-card-filled`, `.md-card-outlined` |
| Chips | `.md-chip`, `.md-chip-assist`, `.md-chip-filter`, `.md-chip-suggestion` |
| Dialog | `.md-dialog-scrim`, `.md-dialog` |
| Navigation Bar | `.md-nav-bar`, `.md-nav-item` |
| Navigation Drawer | `.md-drawer`, `.md-drawer-item` |
| Top App Bar | `.md-top-app-bar` |
| Snackbar | `.md-snackbar`, `.md-snackbar-container` |
| Progress | `.md-progress-linear`, `.md-progress-circular` |
| Switch | `.md-switch` |
| Checkbox | `.md-checkbox` |
| Radio Button | `.md-radio` |
| Slider | `.md-slider` |
| Divider | `.md-divider` |
| Badge | `.md-badge`, `.md-badge-wrapper` |
| List | `.md-list`, `.md-list-item` |
| Menu | `.md-menu`, `.md-menu-item` |
| Tabs | `.md-tabs`, `.md-tab` |
| Tipografi | `.md-display-large` … `.md-body-small` |

---

## 📖 Cara Penggunaan

### Template HTML Lengkap

```html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aplikasiku</title>

  <!-- Material Symbols (opsional, untuk ikon) -->
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
  <!-- Font Roboto -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
  <!-- Material You CSS -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/hiratazx/material-you-css@latest/material-you.css">
</head>
<body>
  <!-- konten di sini -->
</body>
</html>
```

---

### Buttons

```html
<!-- Filled — penekanan tertinggi -->
<button class="md-btn md-btn-filled">Simpan</button>

<!-- Filled Tonal -->
<button class="md-btn md-btn-tonal">Lanjutkan</button>

<!-- Outlined -->
<button class="md-btn md-btn-outlined">Batal</button>

<!-- Text -->
<button class="md-btn md-btn-text">Pelajari lebih lanjut</button>

<!-- Elevated -->
<button class="md-btn md-btn-elevated">Lihat detail</button>

<!-- Dengan ikon -->
<button class="md-btn md-btn-filled">
  <span class="md-icon">add</span>
  Tambah Item
</button>

<!-- Disabled -->
<button class="md-btn md-btn-filled" disabled>Tidak tersedia</button>
```

---

### Cards

```html
<!-- Elevated Card -->
<div class="md-card md-card-elevated" style="max-width: 360px;">
  <img class="md-card-media" src="gambar.jpg" alt="..." style="height: 194px;">
  <div class="md-card-content">
    <p class="md-title-large">Judul Card</p>
    <p class="md-body-medium md-text-on-surface-variant">Deskripsi singkat konten card ini.</p>
  </div>
  <div class="md-card-actions">
    <button class="md-btn md-btn-filled">Mulai</button>
    <button class="md-btn md-btn-text">Pelajari</button>
  </div>
</div>

<!-- Filled Card -->
<div class="md-card md-card-filled">...</div>

<!-- Outlined Card -->
<div class="md-card md-card-outlined">...</div>

<!-- Card Interaktif (bisa diklik) -->
<div class="md-card md-card-elevated md-card-interactive" tabindex="0">
  <div class="md-card-content">
    <p class="md-title-medium">Card Interaktif</p>
  </div>
</div>
```

---

### Text Fields

```html
<!-- Filled -->
<div class="md-text-field md-text-field-filled">
  <input type="text" id="nama" placeholder=" ">
  <label for="nama">Nama lengkap</label>
  <span class="md-text-field-support">Masukkan nama sesuai KTP</span>
</div>

<!-- Outlined -->
<div class="md-text-field md-text-field-outlined">
  <input type="email" id="email" placeholder=" ">
  <label for="email">Alamat email</label>
</div>

<!-- Error State -->
<div class="md-text-field md-text-field-outlined md-error-state">
  <input type="text" id="username" placeholder=" " value="nama_sudah_dipakai">
  <label for="username">Username</label>
  <span class="md-text-field-support">Username sudah digunakan</span>
</div>
```

---

### Chips

```html
<!-- Assist Chip -->
<button class="md-chip md-chip-assist">
  <span class="md-icon">location_on</span>
  Jakarta
</button>

<!-- Filter Chip (belum dipilih / terpilih) -->
<button class="md-chip md-chip-filter">Semua</button>
<button class="md-chip md-chip-filter md-chip-selected">
  <span class="md-icon">check</span>
  Aktif
</button>

<!-- Suggestion Chip -->
<button class="md-chip md-chip-suggestion">Terdekat</button>
```

---

### Switch, Checkbox, Radio

```html
<!-- Switch -->
<label class="md-switch">
  <input type="checkbox">
  <div class="md-switch-track">
    <div class="md-switch-thumb"></div>
  </div>
  <span class="md-switch-label">Notifikasi</span>
</label>

<!-- Checkbox -->
<label class="md-checkbox">
  <input type="checkbox">
  <div class="md-checkbox-box">
    <svg class="md-checkbox-check" viewBox="0 0 12 10">
      <polyline points="1.5,5.5 4.5,8.5 10.5,1.5"/>
    </svg>
  </div>
  <span class="md-checkbox-label">Saya setuju dengan syarat dan ketentuan</span>
</label>

<!-- Radio -->
<label class="md-radio">
  <input type="radio" name="opsi">
  <div class="md-radio-circle">
    <div class="md-radio-dot"></div>
  </div>
  <span class="md-radio-label">Opsi A</span>
</label>
```

---

### Navigation Bar

```html
<nav class="md-nav-bar">
  <a href="#" class="md-nav-item md-nav-item-active">
    <div class="md-nav-item-indicator">
      <span class="md-icon md-icon-filled">home</span>
    </div>
    Beranda
  </a>
  <a href="#" class="md-nav-item">
    <div class="md-nav-item-indicator">
      <span class="md-icon">search</span>
    </div>
    Cari
  </a>
  <a href="#" class="md-nav-item">
    <div class="md-badge-wrapper md-nav-item-indicator">
      <span class="md-icon">notifications</span>
      <span class="md-badge">3</span>
    </div>
    Notifikasi
  </a>
  <a href="#" class="md-nav-item">
    <div class="md-nav-item-indicator">
      <span class="md-icon">person</span>
    </div>
    Profil
  </a>
</nav>
```

---

### Top App Bar

```html
<header class="md-top-app-bar">
  <button class="md-icon-btn">
    <span class="md-icon">menu</span>
  </button>
  <span class="md-top-app-bar-title">Judul Halaman</span>
  <div class="md-top-app-bar-actions">
    <button class="md-icon-btn">
      <span class="md-icon">search</span>
    </button>
    <button class="md-icon-btn">
      <span class="md-icon">more_vert</span>
    </button>
  </div>
</header>
```

---

### Dialog

```html
<button class="md-btn md-btn-filled"
  onclick="document.getElementById('my-dialog').classList.add('md-dialog-open')">
  Buka Dialog
</button>

<div class="md-dialog-scrim" id="my-dialog"
  onclick="this.classList.remove('md-dialog-open')">
  <div class="md-dialog" onclick="event.stopPropagation()">
    <h2 class="md-dialog-headline">Hapus item?</h2>
    <div class="md-dialog-content">
      Item yang dihapus tidak dapat dikembalikan. Apakah Anda yakin ingin melanjutkan?
    </div>
    <div class="md-dialog-actions">
      <button class="md-btn md-btn-text"
        onclick="document.getElementById('my-dialog').classList.remove('md-dialog-open')">
        Batal
      </button>
      <button class="md-btn md-btn-filled">Hapus</button>
    </div>
  </div>
</div>
```

---

### Progress Indicators

```html
<!-- Linear — determinate -->
<div class="md-progress-linear">
  <div class="md-progress-linear-track" style="width: 70%;"></div>
</div>

<!-- Linear — indeterminate -->
<div class="md-progress-linear md-progress-linear-indeterminate">
  <div class="md-progress-linear-track"></div>
</div>

<!-- Circular — indeterminate -->
<div class="md-progress-circular md-progress-circular-indeterminate">
  <svg viewBox="0 0 48 48">
    <circle class="md-progress-circular-track" cx="24" cy="24" r="20"/>
    <circle class="md-progress-circular-indicator" cx="24" cy="24" r="20"/>
  </svg>
</div>
```

---

### Tabs

```html
<div class="md-tabs">
  <button class="md-tab md-tab-active">
    Beranda
    <div class="md-tab-indicator"></div>
  </button>
  <button class="md-tab">
    Artikel
    <div class="md-tab-indicator"></div>
  </button>
  <button class="md-tab">
    Video
    <div class="md-tab-indicator"></div>
  </button>
</div>
```

---

### FAB (Floating Action Button)

```html
<!-- FAB Standar -->
<button class="md-fab">
  <span class="md-icon">add</span>
</button>

<!-- FAB Extended -->
<button class="md-fab">
  <span class="md-icon">edit</span>
  Tulis baru
</button>

<!-- Varian warna -->
<button class="md-fab md-fab-surface"><span class="md-icon">share</span></button>
<button class="md-fab md-fab-secondary"><span class="md-icon">favorite</span></button>
<button class="md-fab md-fab-tertiary"><span class="md-icon">bookmark</span></button>

<!-- Varian ukuran -->
<button class="md-fab md-fab-small"><span class="md-icon">add</span></button>
<button class="md-fab md-fab-large"><span class="md-icon">add</span></button>
```

---

### Snackbar

```html
<!-- Statis -->
<div class="md-snackbar">
  <span class="md-snackbar-text">Pesan berhasil dikirim</span>
  <button class="md-snackbar-action">Batalkan</button>
</div>

<!-- Container untuk penggunaan programatik -->
<div class="md-snackbar-container" id="snackbar-container"></div>
```

---

### Lists

```html
<ul class="md-list">
  <!-- Item satu baris -->
  <li class="md-list-item">
    <div class="md-list-item-leading">
      <span class="md-icon">inbox</span>
    </div>
    <div class="md-list-item-content">
      <span class="md-list-item-headline">Kotak Masuk</span>
    </div>
    <div class="md-list-item-trailing">24</div>
  </li>

  <!-- Item dua baris (dapat diklik) -->
  <a href="#" class="md-list-item md-list-item-clickable">
    <div class="md-list-item-content">
      <span class="md-list-item-headline">Judul Item</span>
      <span class="md-list-item-supporting">Teks pendukung</span>
    </div>
  </a>
</ul>
```

---

## 🎨 Kustomisasi Tema

Override CSS variables untuk menyesuaikan dengan warna brand kamu:

```css
:root {
  --md-sys-color-primary: #006495;
  --md-sys-color-on-primary: #FFFFFF;
  --md-sys-color-primary-container: #CBE6FF;
  --md-sys-color-on-primary-container: #001E2F;

  /* Kustomisasi shape */
  --md-sys-shape-corner-full: 16px; /* tombol lebih kotak */
}
```

> 💡 Gunakan [Material Theme Builder](https://material-foundation.github.io/material-theme-builder/) resmi dari Google untuk generate token warna lengkap dari satu seed color.

---

## 🌙 Dark Mode

Dark mode aktif otomatis mengikuti preferensi sistem (`prefers-color-scheme: dark`).

Untuk kontrol manual, tambahkan class `.md-dark`:

```html
<body class="md-dark">...</body>
```

```javascript
// Toggle
document.body.classList.toggle('md-dark');
```

---

## 📐 Skala Tipografi

```html
<p class="md-display-large">Display Large — 57px</p>
<p class="md-display-medium">Display Medium — 45px</p>
<p class="md-display-small">Display Small — 36px</p>
<p class="md-headline-large">Headline Large — 32px</p>
<p class="md-headline-medium">Headline Medium — 28px</p>
<p class="md-headline-small">Headline Small — 24px</p>
<p class="md-title-large">Title Large — 22px</p>
<p class="md-title-medium">Title Medium — 16px</p>
<p class="md-title-small">Title Small — 14px</p>
<p class="md-body-large">Body Large — 16px</p>
<p class="md-body-medium">Body Medium — 14px</p>
<p class="md-body-small">Body Small — 12px</p>
<p class="md-label-large">Label Large — 14px</p>
<p class="md-label-medium">Label Medium — 12px</p>
<p class="md-label-small">Label Small — 11px</p>
```

---

## 🖼 Ikon

Library ini tidak menyertakan ikon. Gunakan [Material Symbols](https://fonts.google.com/icons) dari Google Fonts:

```html
<!-- Di dalam <head> -->
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
```

```html
<!-- Cara pakai -->
<span class="md-icon">home</span>
<span class="md-icon md-icon-filled">favorite</span>
```

---

## 📁 Struktur Repository

```
hiratazx/material-you-css
├── material-you.css   ← satu-satunya file yang perlu diimport
├── LICENSE
├── README.md          ← English
└── README-ID.md       ← Bahasa Indonesia (file ini)
```

---

## ⚖️ Lisensi & Atribusi

Kode CSS dalam repository ini dilisensikan di bawah **[MIT License](LICENSE)**.

| Aset | Pemilik | Lisensi |
|---|---|---|
| Kode CSS dalam repo ini | Kontributor | MIT |
| Brand "Material Design" / "Material You" | Google LLC | Merek Dagang — tidak untuk penamaan produk |
| Spesifikasi & panduan desain MD3 | Google LLC | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |
| Font Roboto & Material Symbols | Google LLC | Apache 2.0 |

Proyek ini **bukan produk resmi Google** dan **tidak berafiliasi dengan atau didukung oleh Google LLC**.

---

## 🤝 Kontribusi

Pull request, issue, dan saran sangat disambut! Pastikan perubahan mengikuti spesifikasi [Material Design 3](https://m3.material.io/).

1. Fork repository ini
2. Buat branch baru: `git checkout -b feat/nama-komponen`
3. Commit perubahan: `git commit -m 'feat: tambah nama-komponen'`
4. Push ke branch: `git push origin feat/nama-komponen`
5. Buka Pull Request

---

<p align="center">
  Implementasi CSS mandiri yang mereferensikan panduan <a href="https://m3.material.io/">Material Design 3</a>.<br>
  Material Design adalah merek dagang Google LLC. Proyek ini tidak berafiliasi dengan atau didukung oleh Google.
</p>
