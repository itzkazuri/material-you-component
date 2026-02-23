<section class="gallery">
  <article class="preview-card">
    <div class="preview-header">
      <h3 class="md-title-medium">Action components</h3>
      <span class="md-label-medium">Buttons & chips</span>
    </div>
    <div class="preview-body">
      <button class="md-btn md-btn-filled">Primary</button>
      <button class="md-btn md-btn-tonal">Tonal</button>
      <button class="md-btn md-btn-outlined">Outlined</button>
      <div class="chip-row">
        <span class="md-chip">Seeded</span>
        <span class="md-chip">Responsive</span>
        <span class="md-chip">Adaptive</span>
      </div>
    </div>
  </article>

  <article class="preview-card">
    <div class="preview-header">
      <h3 class="md-title-medium">Inputs</h3>
      <span class="md-label-medium">Fields & toggles</span>
    </div>
    <div class="preview-body">
      <label class="input">
        <span class="md-label-medium">Email</span>
        <input type="email" placeholder="hello@material.app" />
      </label>
      <label class="switch">
        <input type="checkbox" checked />
        <span class="switch-track"></span>
        <span class="md-body-small">Notifications</span>
      </label>
    </div>
  </article>

  <article class="preview-card">
    <div class="preview-header">
      <h3 class="md-title-medium">Surfaces</h3>
      <span class="md-label-medium">Cards & elevation</span>
    </div>
    <div class="preview-body">
      <div class="surface">
        <p class="md-label-medium">Elevated surface</p>
        <p class="md-body-small">Layered containers highlight content without heavy borders.</p>
      </div>
      <div class="surface alt">
        <p class="md-label-medium">Interactive states</p>
        <p class="md-body-small">Hover and focus handled through state layers.</p>
      </div>
    </div>
  </article>
</section>

<style>
  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 16px;
  }

  .preview-card {
    padding: 18px;
    border-radius: 22px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container);
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .preview-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    gap: 12px;
  }

  .preview-header h3 {
    margin: 0;
    color: var(--md-sys-color-on-surface);
  }

  .preview-header span {
    color: var(--md-sys-color-on-surface-variant);
  }

  .preview-body {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .chip-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .md-chip {
    padding: 6px 12px;
    border-radius: 999px;
    background-color: var(--md-sys-color-secondary-container);
    color: var(--md-sys-color-on-secondary-container);
    font-size: 12px;
  }

  .input {
    display: flex;
    flex-direction: column;
    gap: 6px;
    padding: 10px 12px;
    border-radius: 14px;
    background-color: var(--md-sys-color-surface-container-high);
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .input input {
    border: none;
    background: transparent;
    color: var(--md-sys-color-on-surface);
    font-size: 14px;
    outline: none;
  }

  .switch {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .switch input {
    display: none;
  }

  .switch-track {
    width: 40px;
    height: 22px;
    border-radius: 999px;
    background-color: var(--md-sys-color-outline-variant);
    position: relative;
  }

  .switch-track::after {
    content: '';
    position: absolute;
    width: 18px;
    height: 18px;
    border-radius: 50%;
    top: 2px;
    left: 2px;
    background-color: var(--md-sys-color-surface);
    transition: left var(--md-sys-motion-duration-short3) var(--md-sys-motion-easing-standard);
  }

  .switch input:checked + .switch-track {
    background-color: var(--md-sys-color-primary);
  }

  .switch input:checked + .switch-track::after {
    left: 20px;
    background-color: var(--md-sys-color-on-primary);
  }

  .surface {
    padding: 12px;
    border-radius: 16px;
    background-color: var(--md-sys-color-surface-container-high);
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .surface.alt {
    background-color: var(--md-sys-color-surface-container-highest);
  }

  .surface p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }
</style>
