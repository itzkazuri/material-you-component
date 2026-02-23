<script>
  import { onMount } from 'svelte';

  let { activeItem = 'home' } = $props();

  const navItems = [
    { id: 'home', label: 'Home', icon: 'home' },
    { id: 'get-started', label: 'Get started', icon: 'grid_view' },
    { id: 'develop', label: 'Develop', icon: 'code' },
    { id: 'foundations', label: 'Foundations', icon: 'book' },
    { id: 'styles', label: 'Styles', icon: 'palette' },
    { id: 'components', label: 'Components', icon: 'add_circle', href: '/components' },
    { id: 'blog', label: 'Blog', icon: 'star' },
  ];

  const THEME_KEY = 'm3-theme';
  const SEED_KEY = 'm3-seed';
  let theme = 'dark';
  let seedColor = '#6750a4';

  const clamp = (value, min, max) => Math.min(Math.max(value, min), max);

  const hexToHsl = (hex) => {
    const clean = hex.replace('#', '');
    const bigint = parseInt(clean, 16);
    const r = (bigint >> 16) & 255;
    const g = (bigint >> 8) & 255;
    const b = bigint & 255;
    const rNorm = r / 255;
    const gNorm = g / 255;
    const bNorm = b / 255;
    const max = Math.max(rNorm, gNorm, bNorm);
    const min = Math.min(rNorm, gNorm, bNorm);
    const delta = max - min;
    let h = 0;
    let s = 0;
    const l = (max + min) / 2;
    if (delta !== 0) {
      s = delta / (1 - Math.abs(2 * l - 1));
      switch (max) {
        case rNorm:
          h = ((gNorm - bNorm) / delta) % 6;
          break;
        case gNorm:
          h = (bNorm - rNorm) / delta + 2;
          break;
        default:
          h = (rNorm - gNorm) / delta + 4;
      }
      h = Math.round(h * 60);
      if (h < 0) h += 360;
    }
    return { h, s: Math.round(s * 100), l: Math.round(l * 100) };
  };

  const setVar = (name, value) => {
    document.documentElement.style.setProperty(name, value);
  };

  const applyTheme = (nextTheme, nextSeed) => {
    const { h, s } = hexToHsl(nextSeed);
    const neutral = clamp(s * 0.2, 6, 18);
    const isDark = nextTheme === 'dark';

    const primary = isDark ? 70 : 40;
    const primaryContainer = isDark ? 28 : 85;
    const secondary = isDark ? 64 : 46;
    const secondaryContainer = isDark ? 26 : 88;
    const tertiary = isDark ? 68 : 44;
    const tertiaryContainer = isDark ? 24 : 88;

    setVar('--md-sys-color-primary', `hsl(${h} ${s}% ${primary}%)`);
    setVar('--md-sys-color-on-primary', isDark ? '#1a1a1a' : '#ffffff');
    setVar('--md-sys-color-primary-container', `hsl(${h} ${s}% ${primaryContainer}%)`);
    setVar('--md-sys-color-on-primary-container', isDark ? '#f4effa' : '#21005d');

    setVar('--md-sys-color-secondary', `hsl(${h} ${Math.max(12, s - 25)}% ${secondary}%)`);
    setVar('--md-sys-color-on-secondary', isDark ? '#111111' : '#ffffff');
    setVar('--md-sys-color-secondary-container', `hsl(${h} ${Math.max(12, s - 30)}% ${secondaryContainer}%)`);
    setVar('--md-sys-color-on-secondary-container', isDark ? '#f5f1f9' : '#1d192b');

    setVar('--md-sys-color-tertiary', `hsl(${(h + 30) % 360} ${Math.max(12, s - 18)}% ${tertiary}%)`);
    setVar('--md-sys-color-on-tertiary', isDark ? '#101010' : '#ffffff');
    setVar('--md-sys-color-tertiary-container', `hsl(${(h + 30) % 360} ${Math.max(12, s - 22)}% ${tertiaryContainer}%)`);
    setVar('--md-sys-color-on-tertiary-container', isDark ? '#f9f1f4' : '#31111d');

    setVar('--md-sys-color-background', isDark ? `hsl(${h} ${neutral}% 10%)` : `hsl(${h} ${neutral}% 98%)`);
    setVar('--md-sys-color-on-background', isDark ? '#f2eff4' : '#1c1b1f');
    setVar('--md-sys-color-surface', isDark ? `hsl(${h} ${neutral}% 12%)` : `hsl(${h} ${neutral}% 99%)`);
    setVar('--md-sys-color-surface-dim', isDark ? `hsl(${h} ${neutral}% 10%)` : `hsl(${h} ${neutral}% 90%)`);
    setVar('--md-sys-color-surface-bright', isDark ? `hsl(${h} ${neutral}% 22%)` : `hsl(${h} ${neutral}% 99%)`);
    setVar('--md-sys-color-surface-container-lowest', isDark ? `hsl(${h} ${neutral}% 8%)` : '#ffffff');
    setVar('--md-sys-color-surface-container-low', isDark ? `hsl(${h} ${neutral}% 14%)` : `hsl(${h} ${neutral}% 96%)`);
    setVar('--md-sys-color-surface-container', isDark ? `hsl(${h} ${neutral}% 16%)` : `hsl(${h} ${neutral}% 94%)`);
    setVar('--md-sys-color-surface-container-high', isDark ? `hsl(${h} ${neutral}% 20%)` : `hsl(${h} ${neutral}% 92%)`);
    setVar('--md-sys-color-surface-container-highest', isDark ? `hsl(${h} ${neutral}% 24%)` : `hsl(${h} ${neutral}% 90%)`);
    setVar('--md-sys-color-on-surface', isDark ? '#f2eff4' : '#1c1b1f');
    setVar('--md-sys-color-on-surface-variant', isDark ? '#d1c9d8' : '#49454f');
    setVar('--md-sys-color-outline', isDark ? `hsl(${h} ${neutral}% 46%)` : '#79747e');
    setVar('--md-sys-color-outline-variant', isDark ? `hsl(${h} ${neutral}% 26%)` : '#cac4d0');
    setVar('--md-sys-color-inverse-surface', isDark ? '#f4eff4' : '#313033');
    setVar('--md-sys-color-inverse-on-surface', isDark ? '#313033' : '#f4eff4');
    setVar('--md-sys-color-inverse-primary', `hsl(${h} ${s}% ${isDark ? 40 : 80}%)`);
    setVar('--md-sys-color-error', isDark ? '#f2b8b5' : '#b3261e');
    setVar('--md-sys-color-on-error', isDark ? '#601410' : '#ffffff');
    setVar('--md-sys-color-error-container', isDark ? '#8c1d18' : '#f9dedc');
    setVar('--md-sys-color-on-error-container', isDark ? '#f9dedc' : '#410e0b');
  };

  const setTheme = (nextTheme) => {
    theme = nextTheme;
    localStorage.setItem(THEME_KEY, theme);
    applyTheme(theme, seedColor);
  };

  const updateSeed = (value) => {
    seedColor = value;
    localStorage.setItem(SEED_KEY, seedColor);
    applyTheme(theme, seedColor);
  };

  onMount(() => {
    const storedTheme = localStorage.getItem(THEME_KEY);
    const storedSeed = localStorage.getItem(SEED_KEY);
    if (storedSeed) seedColor = storedSeed;
    if (storedTheme) {
      theme = storedTheme;
    } else if (window.matchMedia?.('(prefers-color-scheme: dark)').matches) {
      theme = 'dark';
    } else {
      theme = 'light';
    }
    applyTheme(theme, seedColor);

    if (window.location?.pathname === '/components') {
      activeItem = 'components';
    }
  });
</script>

<aside class="navigation-rail">
  <div class="top-nav">
    <button class="search-fab md-ripple">
      <span class="md-icon">search</span>
    </button>
  </div>

  <nav class="rail-items">
    {#each navItems as item (item.id)}
      <a 
        href={item.href ?? `#${item.id}`} 
        class="md-nav-item {activeItem === item.id ? 'md-nav-item-active' : ''}"
      >
        <div class="md-nav-item-indicator">
          <span class="md-icon {activeItem === item.id ? 'md-icon-filled' : ''}">{item.icon}</span>
        </div>
        <span class="md-label-medium">{item.label}</span>
      </a>
    {/each}
  </nav>

  <div class="bottom-items theme-controls">
    <button
      class="md-icon-btn-outlined bottom-btn {theme === 'dark' ? 'is-active' : ''}"
      on:click={() => setTheme('dark')}
    >
      <span class="md-icon">dark_mode</span>
    </button>
    <button
      class="md-icon-btn-outlined bottom-btn {theme === 'light' ? 'is-active' : ''}"
      on:click={() => setTheme('light')}
    >
      <span class="md-icon">light_mode</span>
    </button>
    <label class="color-picker" aria-label="Pick a theme color">
      <input type="color" bind:value={seedColor} on:input={(event) => updateSeed(event.currentTarget.value)} />
      <span class="md-icon">palette</span>
    </label>
  </div>
</aside>

<style>
  .navigation-rail {
    width: 88px;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 16px 0;
    position: fixed;
    left: 0;
    top: 0;
    border-right: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container);
    color: var(--md-sys-color-on-surface);
    z-index: 100;
  }

  .top-nav {
    margin-bottom: 18px;
    display: flex;
    justify-content: center;
    width: 100%;
  }

  .search-fab {
    width: 52px;
    height: 52px;
    border-radius: 14px;
    border: none;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: var(--md-sys-color-surface-container-high);
    color: var(--md-sys-color-on-surface);
    cursor: pointer;
    transition: background-color var(--md-sys-motion-duration-short4) var(--md-sys-motion-easing-standard);
  }

  .search-fab:hover {
    background-color: var(--md-sys-color-surface-container-highest);
  }

  .rail-items {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 10px;
    width: 100%;
  }

  :global(.md-nav-item) {
    width: 100%;
    min-height: 56px !important;
    height: auto !important;
    padding: 4px 0 !important;
    text-decoration: none;
    color: var(--md-sys-color-on-surface);
  }

  .bottom-items {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-top: auto;
    padding-bottom: 20px;
    align-items: center;
  }

  .bottom-btn {
    width: 50px;
    height: 50px;
    border-radius: 50% !important;
    background-color: transparent;
    border: 1px solid var(--md-sys-color-outline-variant);
    color: var(--md-sys-color-on-surface);
  }

  .bottom-btn.is-active {
    background-color: var(--md-sys-color-secondary-container);
    border-color: var(--md-sys-color-secondary-container);
    color: var(--md-sys-color-on-secondary-container);
  }

  .color-picker {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    border: 1px solid var(--md-sys-color-outline-variant);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--md-sys-color-on-surface);
    position: relative;
    cursor: pointer;
  }

  .color-picker input {
    opacity: 0;
    position: absolute;
    inset: 0;
    cursor: pointer;
  }

  /* Manual overrides for rail verticality if not handled by md-nav-item */
  .md-nav-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 6px;
  }

  .md-nav-item-indicator {
    width: 40px;
    height: 40px;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: transparent;
    transition: background-color var(--md-sys-motion-duration-short3) var(--md-sys-motion-easing-standard);
  }

  .md-nav-item-active .md-nav-item-indicator {
    background-color: var(--md-sys-color-secondary-container);
  }

  .md-nav-item .md-icon {
    font-size: 20px;
  }

  .md-label-medium {
    font-size: 10px;
    line-height: 12px;
    color: var(--md-sys-color-on-surface-variant);
  }

  .md-nav-item-active .md-label-medium {
    color: var(--md-sys-color-on-surface);
  }
</style>
