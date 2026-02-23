<section class="skeleton-grid">
  <div class="skeleton-card">
    <div class="skeleton avatar"></div>
    <div class="skeleton lines"></div>
    <div class="skeleton lines short"></div>
  </div>
  <div class="skeleton-card">
    <div class="skeleton header"></div>
    <div class="skeleton lines"></div>
    <div class="skeleton lines"></div>
  </div>
  <div class="skeleton-card">
    <div class="skeleton hero"></div>
    <div class="skeleton lines"></div>
    <div class="skeleton lines short"></div>
  </div>
</section>

<style>
  .skeleton-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 16px;
  }

  .skeleton-card {
    padding: 16px;
    border-radius: 18px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-low);
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .skeleton {
    border-radius: 999px;
    background: linear-gradient(90deg, rgba(0, 0, 0, 0.06) 0%, rgba(0, 0, 0, 0.12) 50%, rgba(0, 0, 0, 0.06) 100%);
    background-size: 200% 100%;
    animation: shimmer 1.6s ease-in-out infinite;
  }

  .skeleton.avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
  }

  .skeleton.header {
    height: 22px;
    width: 60%;
  }

  .skeleton.hero {
    height: 80px;
    border-radius: 16px;
  }

  .skeleton.lines {
    height: 12px;
    width: 100%;
  }

  .skeleton.lines.short {
    width: 70%;
  }

  @keyframes shimmer {
    0% {
      background-position: 0% 50%;
    }
    100% {
      background-position: 100% 50%;
    }
  }
</style>
