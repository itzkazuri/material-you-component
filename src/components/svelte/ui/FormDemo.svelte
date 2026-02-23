<section class="form-demo">
  <div class="form-grid">
    <label class="md-text-field md-text-field-filled">
      <input type="text" placeholder=" " />
      <label>Project name</label>
    </label>
    <label class="md-text-field md-text-field-outlined">
      <input type="email" placeholder=" " />
      <label>Owner email</label>
    </label>
  </div>

  <div class="form-options">
    <label class="toggle">
      <input type="checkbox" checked />
      <span class="toggle-track"></span>
      <span class="md-body-small">Enable notifications</span>
    </label>
    <label class="toggle">
      <input type="checkbox" />
      <span class="toggle-track"></span>
      <span class="md-body-small">Auto publish</span>
    </label>
  </div>
</section>

<style>
  .form-demo {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .form-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 16px;
  }

  .form-options {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
  }

  .toggle {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .toggle input {
    display: none;
  }

  .toggle-track {
    width: 42px;
    height: 22px;
    border-radius: 999px;
    background-color: var(--md-sys-color-outline-variant);
    position: relative;
  }

  .toggle-track::after {
    content: '';
    position: absolute;
    top: 2px;
    left: 2px;
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background-color: var(--md-sys-color-surface);
    transition: left var(--md-sys-motion-duration-short3) var(--md-sys-motion-easing-standard);
  }

  .toggle input:checked + .toggle-track {
    background-color: var(--md-sys-color-primary);
  }

  .toggle input:checked + .toggle-track::after {
    left: 22px;
    background-color: var(--md-sys-color-on-primary);
  }
</style>
