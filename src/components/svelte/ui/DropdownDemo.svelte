<section class="dropdown-demo">
  <label class="dropdown">
    <span class="md-label-medium">Variant</span>
    <div class="select-wrap">
      <select>
      <option>Filled</option>
      <option>Tonal</option>
      <option>Outlined</option>
      </select>
      <span class="md-icon">expand_more</span>
    </div>
  </label>
  <label class="dropdown">
    <span class="md-label-medium">Density</span>
    <div class="select-wrap">
      <select>
      <option>Comfortable</option>
      <option>Compact</option>
      <option>Dense</option>
      </select>
      <span class="md-icon">expand_more</span>
    </div>
  </label>
</section>

<style>
  .dropdown-demo {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
  }

  .dropdown {
    display: flex;
    flex-direction: column;
    gap: 6px;
    padding: 12px 14px;
    border-radius: 16px;
    background-color: var(--md-sys-color-surface-container);
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .select-wrap {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 8px 10px;
    border-radius: 12px;
    background-color: var(--md-sys-color-surface-container-high);
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .select-wrap .md-icon {
    font-size: 20px;
    color: var(--md-sys-color-on-surface-variant);
  }

  .dropdown select {
    border: none;
    background: transparent;
    color: var(--md-sys-color-on-surface);
    font-size: 14px;
    outline: none;
    appearance: none;
    width: 100%;
    flex: 1;
  }
</style>
