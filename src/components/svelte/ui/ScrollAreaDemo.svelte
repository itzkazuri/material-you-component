<section class="scroll-demo">
  <div class="scroll-card">
    <h3 class="md-title-medium">Release notes</h3>
    <div class="scroll-area">
      <p class="md-body-small">Build 1.0 introduces Material You tokens for Svelte.</p>
      <p class="md-body-small">Theme switcher now supports seed colors.</p>
      <p class="md-body-small">New navigation patterns for docs.</p>
      <p class="md-body-small">Component samples updated with motion tokens.</p>
      <p class="md-body-small">Accessibility improvements for focus states.</p>
      <p class="md-body-small">More components coming next sprint.</p>
      <p class="md-body-small">Design kits updated with latest guidelines.</p>
    </div>
  </div>
  <div class="scroll-note">
    <p class="md-body-small">Scroll areas keep long content contained.</p>
  </div>
</section>

<style>
  .scroll-demo {
    display: grid;
    grid-template-columns: minmax(220px, 320px) 1fr;
    gap: 16px;
  }

  .scroll-card {
    padding: 16px;
    border-radius: 20px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container);
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .scroll-card h3 {
    margin: 0;
  }

  .scroll-area {
    max-height: 160px;
    overflow: auto;
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding-right: 6px;
  }

  .scroll-area p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  .scroll-note {
    padding: 16px;
    border-radius: 16px;
    border: 1px dashed var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-high);
  }

  .scroll-note p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  @media (max-width: 720px) {
    .scroll-demo {
      grid-template-columns: 1fr;
    }
  }
</style>
