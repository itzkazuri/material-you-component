<section class="demo-row">
  <div class="demo-block">
    <p class="md-label-medium">Filled</p>
    <div class="demo-actions">
      <button class="md-btn md-btn-filled">Primary</button>
      <button class="md-btn md-btn-filled">
        <span class="md-icon">bolt</span>
        Boost
      </button>
    </div>
  </div>

  <div class="demo-block">
    <p class="md-label-medium">Tonal</p>
    <div class="demo-actions">
      <button class="md-btn md-btn-tonal">Tonal</button>
      <button class="md-btn md-btn-tonal">
        <span class="md-icon">auto_awesome</span>
        Magic
      </button>
    </div>
  </div>

  <div class="demo-block">
    <p class="md-label-medium">Outlined</p>
    <div class="demo-actions">
      <button class="md-btn md-btn-outlined">Outlined</button>
      <button class="md-btn md-btn-outlined">
        <span class="md-icon">open_in_new</span>
        Open
      </button>
    </div>
  </div>
</section>

<style>
  .demo-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
  }

  .demo-block {
    padding: 14px;
    border-radius: 16px;
    background-color: var(--md-sys-color-surface-container);
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .demo-block p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  .demo-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
</style>
