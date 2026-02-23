<section class="avatar-grid">
  <div class="avatar-card">
    <div class="avatar">AZ</div>
    <div>
      <p class="md-label-medium">Alya Zahra</p>
      <p class="md-body-small">Design lead</p>
    </div>
  </div>
  <div class="avatar-card">
    <div class="avatar image" aria-label="Profile image"></div>
    <div>
      <p class="md-label-medium">Rafi</p>
      <p class="md-body-small">Product manager</p>
    </div>
  </div>
  <div class="avatar-card">
    <div class="avatar status">
      <span>MK</span>
      <span class="status-dot"></span>
    </div>
    <div>
      <p class="md-label-medium">Mika</p>
      <p class="md-body-small">Available</p>
    </div>
  </div>
</section>

<style>
  .avatar-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 12px;
  }

  .avatar-card {
    display: flex;
    gap: 12px;
    align-items: center;
    padding: 12px;
    border-radius: 16px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container);
  }

  .avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background-color: var(--md-sys-color-primary-container);
    color: var(--md-sys-color-on-primary-container);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 600;
    position: relative;
  }

  .avatar.image {
    background: linear-gradient(135deg, rgba(103, 80, 164, 0.4), rgba(0, 0, 0, 0.1));
  }

  .avatar.status .status-dot {
    position: absolute;
    bottom: 2px;
    right: 2px;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background-color: #22c55e;
    border: 2px solid var(--md-sys-color-surface);
  }

  .avatar-card p {
    margin: 0;
  }
</style>
