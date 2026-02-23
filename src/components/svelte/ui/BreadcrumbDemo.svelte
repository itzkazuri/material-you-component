<nav class="breadcrumb">
  <a href="/" class="md-label-medium">Home</a>
  <span class="md-icon">chevron_right</span>
  <a href="/components" class="md-label-medium">Components</a>
  <span class="md-icon">chevron_right</span>
  <span class="md-label-medium active">Buttons</span>
</nav>

<div class="breadcrumb-surface">
  <p class="md-body-small">Use breadcrumbs to reflect navigation depth.</p>
</div>

<style>
  .breadcrumb {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 12px;
    border-radius: 999px;
    background-color: var(--md-sys-color-surface-container);
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .breadcrumb a {
    color: var(--md-sys-color-on-surface-variant);
    text-decoration: none;
  }

  .breadcrumb .active {
    color: var(--md-sys-color-on-surface);
  }

  .breadcrumb .md-icon {
    font-size: 16px;
    color: var(--md-sys-color-on-surface-variant);
  }

  .breadcrumb-surface {
    margin-top: 12px;
    padding: 12px;
    border-radius: 14px;
    background-color: var(--md-sys-color-surface-container-high);
  }

  .breadcrumb-surface p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }
</style>
