<script>
  let { title, subtitle, note } = $props();
</script>

<section class="hero">
  <div class="hero-copy">
    <p class="hero-kicker">Material You for Svelte</p>
    <h1 class="md-display-small">{title}</h1>
    <p class="md-body-large">{subtitle}</p>
    <div class="hero-actions">
      <button class="md-btn md-btn-filled">Get started</button>
      <button class="md-btn md-btn-outlined">Components</button>
    </div>
    <p class="hero-note md-body-small">{note}</p>
  </div>
  <div class="hero-card">
    <div class="hero-card-header">
      <span class="md-label-medium">Live tokens</span>
      <span class="md-label-small">Responsive to your theme switcher</span>
    </div>
    <div class="hero-card-body">
      <div class="token">
        <span class="token-swatch primary"></span>
        <div>
          <p class="md-label-medium">Primary</p>
          <p class="md-body-small">Action, emphasis, FAB</p>
        </div>
      </div>
      <div class="token">
        <span class="token-swatch secondary"></span>
        <div>
          <p class="md-label-medium">Secondary</p>
          <p class="md-body-small">Complementary surfaces</p>
        </div>
      </div>
      <div class="token">
        <span class="token-swatch surface"></span>
        <div>
          <p class="md-label-medium">Surface</p>
          <p class="md-body-small">Layered elevation system</p>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .hero {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 32px;
    align-items: center;
    padding: 28px;
    border-radius: 28px;
    background: linear-gradient(135deg, rgba(103, 80, 164, 0.2), rgba(255, 255, 255, 0.1));
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .hero-copy h1 {
    margin: 0 0 12px;
    color: var(--md-sys-color-on-surface);
  }

  .hero-copy p {
    margin: 0 0 16px;
    color: var(--md-sys-color-on-surface-variant);
  }

  .hero-kicker {
    margin: 0 0 10px;
    text-transform: uppercase;
    letter-spacing: 2px;
    font-size: 11px;
    color: var(--md-sys-color-primary);
  }

  .hero-actions {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }

  .hero-note {
    margin-top: 16px;
    color: var(--md-sys-color-on-surface-variant);
  }

  .hero-card {
    padding: 20px;
    border-radius: 24px;
    background-color: var(--md-sys-color-surface-container);
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .hero-card-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    gap: 8px;
  }

  .hero-card-body {
    margin-top: 16px;
    display: flex;
    flex-direction: column;
    gap: 14px;
  }

  .token {
    display: flex;
    gap: 12px;
    align-items: center;
  }

  .token-swatch {
    width: 44px;
    height: 44px;
    border-radius: 16px;
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .token-swatch.primary {
    background: var(--md-sys-color-primary);
  }

  .token-swatch.secondary {
    background: var(--md-sys-color-secondary);
  }

  .token-swatch.surface {
    background: var(--md-sys-color-surface-container-high);
  }

  .token p {
    margin: 0;
  }
</style>
