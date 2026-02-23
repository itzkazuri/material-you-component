<section class="drawer-demo">
  <aside class="md-drawer">
    <div class="md-drawer-header">Navigation</div>
    <div class="md-drawer-content">
      <button class="md-drawer-item md-drawer-item-active">
        <span class="md-icon">dashboard</span>
        Overview
      </button>
      <button class="md-drawer-item">
        <span class="md-icon">palette</span>
        Themes
      </button>
      <button class="md-drawer-item">
        <span class="md-icon">widgets</span>
        Components
      </button>
      <button class="md-drawer-item">
        <span class="md-icon">description</span>
        Documentation
      </button>
      <div class="md-drawer-section-label">Resources</div>
      <button class="md-drawer-item">
        <span class="md-icon">book</span>
        Guides
      </button>
      <button class="md-drawer-item">
        <span class="md-icon">support_agent</span>
        Support
      </button>
    </div>
  </aside>
  <div class="drawer-placeholder">
    <p class="md-body-small">Use drawers for extended navigation on larger screens.</p>
  </div>
</section>

<style>
  .drawer-demo {
    display: grid;
    grid-template-columns: minmax(220px, 320px) 1fr;
    gap: 16px;
  }

  .drawer-placeholder {
    padding: 16px;
    border-radius: 16px;
    border: 1px dashed var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-high);
  }

  .drawer-placeholder p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  @media (max-width: 720px) {
    .drawer-demo {
      grid-template-columns: 1fr;
    }

    .md-drawer {
      width: 100%;
      border-radius: var(--md-sys-shape-corner-large);
    }
  }
</style>
