<section class="badge-demo">
  <div class="badge-item md-badge-wrapper">
    <button class="md-icon-btn">
      <span class="md-icon">mail</span>
    </button>
    <span class="md-badge">3</span>
  </div>
  <div class="badge-item md-badge-wrapper">
    <button class="md-icon-btn">
      <span class="md-icon">notifications</span>
    </button>
    <span class="md-badge"></span>
  </div>
  <div class="badge-item">
    <span class="md-label-medium">Updates</span>
    <span class="badge-pill">New</span>
  </div>
</section>

<style>
  .badge-demo {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
    align-items: center;
  }

  .badge-item {
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }

  .badge-pill {
    padding: 4px 10px;
    border-radius: 999px;
    background-color: var(--md-sys-color-primary);
    color: var(--md-sys-color-on-primary);
    font-size: 11px;
  }
</style>
