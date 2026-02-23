# 🎨 Material You CSS

**English** | [Bahasa Indonesia](README-ID.md)

> An independent, lightweight, CSS-only implementation of [Material Design 3 (Material You)](https://m3.material.io/) — just import and use.

[![License: MIT](https://img.shields.io/badge/License-MIT-purple.svg)](LICENSE)
[![CSS Only](https://img.shields.io/badge/CSS-Only-1e88e5.svg)]()
[![Material Design 3](https://img.shields.io/badge/Material-Design%203-6750A4.svg)](https://m3.material.io/)
[![GitHub](https://img.shields.io/badge/GitHub-hiratazx%2Fmaterial--you--css-181717?logo=github)](https://github.com/hiratazx/material-you-css)

> **⚠️ Disclaimer:** This project is an **independent CSS implementation** and is **not affiliated with, endorsed by, or sponsored by Google LLC**. "Material Design", "Material You", and related trademarks are the property of Google LLC. Design guidelines referenced from [m3.material.io](https://m3.material.io/).

---

## ✨ Features

- 🎨 **Complete MD3 Design Tokens** — colors, typography, shape, motion, elevation
- 🌙 **Auto Dark Mode** via `prefers-color-scheme` + manual `.md-dark` class
- ⚡ **Zero dependencies** — pure CSS, no JavaScript required for styling
- 📦 **Single file** — one import is all you need
- ♿ **Accessible** — proper focus states, disabled states, and state layers
- 🔧 **Fully customizable** — all values exposed as CSS Variables

---

## 🚀 Installation

### CDN (jsDelivr) — Recommended

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/hiratazx/material-you-css@latest/material-you.css">
```

### Download & use locally

```html
<link rel="stylesheet" href="material-you.css">
```

### `@import` in CSS

```css
@import url('https://cdn.jsdelivr.net/gh/hiratazx/material-you-css@latest/material-you.css');
```

---

## 📦 Components

| Component | Main Classes |
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
| Typography | `.md-display-large` … `.md-body-small` |

---

## 📖 Usage

### Full HTML Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My App</title>

  <!-- Material Symbols (optional, for icons) -->
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
  <!-- Roboto Font -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
  <!-- Material You CSS -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/hiratazx/material-you-css@latest/material-you.css">
</head>
<body>
  <!-- content here -->
</body>
</html>
```

---

### Buttons

```html
<!-- Filled — highest emphasis -->
<button class="md-btn md-btn-filled">Save</button>

<!-- Filled Tonal -->
<button class="md-btn md-btn-tonal">Continue</button>

<!-- Outlined -->
<button class="md-btn md-btn-outlined">Cancel</button>

<!-- Text -->
<button class="md-btn md-btn-text">Learn more</button>

<!-- Elevated -->
<button class="md-btn md-btn-elevated">View details</button>

<!-- With icon -->
<button class="md-btn md-btn-filled">
  <span class="md-icon">add</span>
  Add item
</button>

<!-- Disabled -->
<button class="md-btn md-btn-filled" disabled>Unavailable</button>
```

---

### Cards

```html
<!-- Elevated Card -->
<div class="md-card md-card-elevated" style="max-width: 360px;">
  <img class="md-card-media" src="image.jpg" alt="..." style="height: 194px;">
  <div class="md-card-content">
    <p class="md-title-large">Card Title</p>
    <p class="md-body-medium md-text-on-surface-variant">Short description of the card content.</p>
  </div>
  <div class="md-card-actions">
    <button class="md-btn md-btn-filled">Start</button>
    <button class="md-btn md-btn-text">Learn more</button>
  </div>
</div>

<!-- Filled Card -->
<div class="md-card md-card-filled">...</div>

<!-- Outlined Card -->
<div class="md-card md-card-outlined">...</div>

<!-- Clickable / Interactive Card -->
<div class="md-card md-card-elevated md-card-interactive" tabindex="0">
  <div class="md-card-content">
    <p class="md-title-medium">Interactive Card</p>
  </div>
</div>
```

---

### Text Fields

```html
<!-- Filled -->
<div class="md-text-field md-text-field-filled">
  <input type="text" id="name" placeholder=" ">
  <label for="name">Full name</label>
  <span class="md-text-field-support">Enter your legal name</span>
</div>

<!-- Outlined -->
<div class="md-text-field md-text-field-outlined">
  <input type="email" id="email" placeholder=" ">
  <label for="email">Email address</label>
</div>

<!-- Error state -->
<div class="md-text-field md-text-field-outlined md-error-state">
  <input type="text" id="username" placeholder=" " value="taken_name">
  <label for="username">Username</label>
  <span class="md-text-field-support">Username is already taken</span>
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

<!-- Filter Chip (unselected / selected) -->
<button class="md-chip md-chip-filter">All</button>
<button class="md-chip md-chip-filter md-chip-selected">
  <span class="md-icon">check</span>
  Active
</button>

<!-- Suggestion Chip -->
<button class="md-chip md-chip-suggestion">Nearby</button>
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
  <span class="md-switch-label">Notifications</span>
</label>

<!-- Checkbox -->
<label class="md-checkbox">
  <input type="checkbox">
  <div class="md-checkbox-box">
    <svg class="md-checkbox-check" viewBox="0 0 12 10">
      <polyline points="1.5,5.5 4.5,8.5 10.5,1.5"/>
    </svg>
  </div>
  <span class="md-checkbox-label">I agree to the terms and conditions</span>
</label>

<!-- Radio -->
<label class="md-radio">
  <input type="radio" name="option">
  <div class="md-radio-circle">
    <div class="md-radio-dot"></div>
  </div>
  <span class="md-radio-label">Option A</span>
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
    Home
  </a>
  <a href="#" class="md-nav-item">
    <div class="md-nav-item-indicator">
      <span class="md-icon">search</span>
    </div>
    Search
  </a>
  <a href="#" class="md-nav-item">
    <div class="md-badge-wrapper md-nav-item-indicator">
      <span class="md-icon">notifications</span>
      <span class="md-badge">3</span>
    </div>
    Alerts
  </a>
  <a href="#" class="md-nav-item">
    <div class="md-nav-item-indicator">
      <span class="md-icon">person</span>
    </div>
    Profile
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
  <span class="md-top-app-bar-title">Page Title</span>
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
  Open Dialog
</button>

<div class="md-dialog-scrim" id="my-dialog"
  onclick="this.classList.remove('md-dialog-open')">
  <div class="md-dialog" onclick="event.stopPropagation()">
    <h2 class="md-dialog-headline">Delete item?</h2>
    <div class="md-dialog-content">
      Deleted items cannot be recovered. Are you sure you want to continue?
    </div>
    <div class="md-dialog-actions">
      <button class="md-btn md-btn-text"
        onclick="document.getElementById('my-dialog').classList.remove('md-dialog-open')">
        Cancel
      </button>
      <button class="md-btn md-btn-filled">Delete</button>
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
    Home
    <div class="md-tab-indicator"></div>
  </button>
  <button class="md-tab">
    Articles
    <div class="md-tab-indicator"></div>
  </button>
  <button class="md-tab">
    Videos
    <div class="md-tab-indicator"></div>
  </button>
</div>
```

---

### FAB (Floating Action Button)

```html
<!-- Standard FAB -->
<button class="md-fab">
  <span class="md-icon">add</span>
</button>

<!-- Extended FAB -->
<button class="md-fab">
  <span class="md-icon">edit</span>
  New post
</button>

<!-- Color variants -->
<button class="md-fab md-fab-surface"><span class="md-icon">share</span></button>
<button class="md-fab md-fab-secondary"><span class="md-icon">favorite</span></button>
<button class="md-fab md-fab-tertiary"><span class="md-icon">bookmark</span></button>

<!-- Size variants -->
<button class="md-fab md-fab-small"><span class="md-icon">add</span></button>
<button class="md-fab md-fab-large"><span class="md-icon">add</span></button>
```

---

### Snackbar

```html
<!-- Static -->
<div class="md-snackbar">
  <span class="md-snackbar-text">Message sent successfully</span>
  <button class="md-snackbar-action">Undo</button>
</div>

<!-- Programmatic container -->
<div class="md-snackbar-container" id="snackbar-container"></div>
```

---

### Lists

```html
<ul class="md-list">
  <!-- Single-line item -->
  <li class="md-list-item">
    <div class="md-list-item-leading">
      <span class="md-icon">inbox</span>
    </div>
    <div class="md-list-item-content">
      <span class="md-list-item-headline">Inbox</span>
    </div>
    <div class="md-list-item-trailing">24</div>
  </li>

  <!-- Two-line item (clickable) -->
  <a href="#" class="md-list-item md-list-item-clickable">
    <div class="md-list-item-content">
      <span class="md-list-item-headline">Item headline</span>
      <span class="md-list-item-supporting">Supporting text</span>
    </div>
  </a>
</ul>
```

---

## 🎨 Theming & Customization

Override CSS variables to match your brand colors:

```css
:root {
  --md-sys-color-primary: #006495;
  --md-sys-color-on-primary: #FFFFFF;
  --md-sys-color-primary-container: #CBE6FF;
  --md-sys-color-on-primary-container: #001E2F;

  /* Customize shape */
  --md-sys-shape-corner-full: 16px; /* squarish buttons */
}
```

> 💡 Use the official [Material Theme Builder](https://material-foundation.github.io/material-theme-builder/) to generate a full color token set from a single seed color.

---

## 🌙 Dark Mode

Dark mode is automatically activated by the system preference (`prefers-color-scheme: dark`).

For manual control, add the `.md-dark` class:

```html
<body class="md-dark">...</body>
```

```javascript
// Toggle
document.body.classList.toggle('md-dark');
```

---

## 📐 Typography Scale

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

## 🖼 Icons

This library does not bundle icons. Use [Material Symbols](https://fonts.google.com/icons) from Google Fonts:

```html
<!-- In <head> -->
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
```

```html
<!-- Usage -->
<span class="md-icon">home</span>
<span class="md-icon md-icon-filled">favorite</span>
```

---

## 📁 Repository Structure

```
hiratazx/material-you-css
├── material-you.css   ← the only file you need to import
├── LICENSE
├── README.md          ← English (this file)
└── README-ID.md       ← Bahasa Indonesia
```

---

## ⚖️ License & Attribution

The CSS code in this repository is licensed under the **[MIT License](LICENSE)**.

| Asset | Owner | License |
|---|---|---|
| CSS code in this repo | Contributors | MIT |
| "Material Design" / "Material You" brand | Google LLC | Trademark — not for product naming |
| MD3 design specification & guidelines | Google LLC | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |
| Roboto font & Material Symbols | Google LLC | Apache 2.0 |

This project is **not an official Google product** and is **not affiliated with or endorsed by Google LLC**.

---

## 🤝 Contributing

Pull requests, issues, and suggestions are welcome! Please make sure changes follow the [Material Design 3](https://m3.material.io/) specification.

1. Fork the repository
2. Create your feature branch: `git checkout -b feat/component-name`
3. Commit your changes: `git commit -m 'feat: add component-name'`
4. Push to the branch: `git push origin feat/component-name`
5. Open a Pull Request

---

<p align="center">
  An independent CSS implementation referencing <a href="https://m3.material.io/">Material Design 3</a> guidelines.<br>
  Material Design is a trademark of Google LLC. This project is not affiliated with or endorsed by Google.
</p>
