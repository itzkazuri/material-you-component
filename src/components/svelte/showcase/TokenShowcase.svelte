<section class="token-grid">
  <article class="token-card">
    <span class="md-icon">palette</span>
    <h3 class="md-title-medium">Dynamic Color</h3>
    <p class="md-body-small">Seed-based palettes that react to user preference and OS theme.</p>
  </article>
  <article class="token-card">
    <span class="md-icon">text_fields</span>
    <h3 class="md-title-medium">Type Scale</h3>
    <p class="md-body-small">13 typography roles mapped to your interface hierarchy.</p>
  </article>
  <article class="token-card">
    <span class="md-icon">blur_on</span>
    <h3 class="md-title-medium">Shape System</h3>
    <p class="md-body-small">Tokenized radii from sharp cards to pill chips.</p>
  </article>
  <article class="token-card">
    <span class="md-icon">slow_motion_video</span>
    <h3 class="md-title-medium">Motion</h3>
    <p class="md-body-small">Natural easing curves for navigation and micro feedback.</p>
  </article>
</section>

<style>
  .token-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
  }

  .token-card {
    padding: 18px;
    border-radius: 20px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container);
    display: flex;
    flex-direction: column;
    gap: 10px;
    min-height: 140px;
  }

  .token-card h3 {
    margin: 0;
    color: var(--md-sys-color-on-surface);
  }

  .token-card p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  .token-card .md-icon {
    font-size: 22px;
    color: var(--md-sys-color-primary);
  }
</style>
