<section class="alert-grid">
  <div class="alert info">
    <span class="md-icon">info</span>
    <div>
      <p class="md-label-medium">Info</p>
      <p class="md-body-small">Material You tokens update instantly.</p>
    </div>
  </div>
  <div class="alert success">
    <span class="md-icon">check_circle</span>
    <div>
      <p class="md-label-medium">Success</p>
      <p class="md-body-small">Theme preferences saved.</p>
    </div>
  </div>
  <div class="alert warning">
    <span class="md-icon">warning</span>
    <div>
      <p class="md-label-medium">Warning</p>
      <p class="md-body-small">Contrast ratio needs review.</p>
    </div>
  </div>
  <div class="alert error">
    <span class="md-icon">error</span>
    <div>
      <p class="md-label-medium">Error</p>
      <p class="md-body-small">Unable to sync palette.</p>
    </div>
  </div>
</section>

<style>
  .alert-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 12px;
  }

  .alert {
    display: flex;
    gap: 12px;
    padding: 12px 14px;
    border-radius: 16px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container);
    align-items: center;
  }

  .alert p {
    margin: 0;
  }

  .alert .md-icon {
    font-size: 20px;
    color: var(--md-sys-color-primary);
  }

  .alert.success {
    border-color: var(--md-sys-color-secondary-container);
  }

  .alert.warning {
    border-color: var(--md-sys-color-tertiary-container);
  }

  .alert.error {
    border-color: var(--md-sys-color-error);
  }
</style>
