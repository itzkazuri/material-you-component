<script>
  let queue = [];

  const variants = {
    default: {
      title: 'Update',
      message: 'New Material You components are ready.',
      icon: 'info',
    },
    success: {
      title: 'Saved',
      message: 'Your layout updates are live.',
      icon: 'check_circle',
    },
    warning: {
      title: 'Warning',
      message: 'Contrast needs improvement.',
      icon: 'warning',
    },
    error: {
      title: 'Error',
      message: 'Could not sync your theme.',
      icon: 'error',
    },
  };

  const showToast = (variant = 'default') => {
    const id = crypto.randomUUID();
    const data = variants[variant] ?? variants.default;
    queue = [{ id, variant, ...data }, ...queue].slice(0, 4);
    setTimeout(() => {
      queue = queue.filter((item) => item.id !== id);
    }, 2800);
  };
</script>

<div class="toast-demo">
  <div class="toast-actions">
    <button class="md-btn md-btn-filled" on:click={() => showToast('default')}>Toast</button>
    <button class="md-btn md-btn-tonal" on:click={() => showToast('success')}>Success</button>
    <button class="md-btn md-btn-outlined" on:click={() => showToast('warning')}>Warning</button>
    <button class="md-btn md-btn-outlined" on:click={() => showToast('error')}>Error</button>
  </div>

  <div class="toast-preview">
    <p class="md-body-small">Preview appears in the top-right corner.</p>
  </div>
</div>

<div class="toast-stack" aria-live="polite">
  {#each queue as item (item.id)}
    <div class="toast-card {item.variant}">
      <span class="md-icon">{item.icon}</span>
      <div>
        <p class="md-label-medium">{item.title}</p>
        <p class="md-body-small">{item.message}</p>
      </div>
      <button class="md-icon-btn" on:click={() => (queue = queue.filter((t) => t.id !== item.id))}>
        <span class="md-icon">close</span>
      </button>
    </div>
  {/each}
</div>

<style>
  .toast-demo {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .toast-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .toast-preview {
    padding: 12px 14px;
    border-radius: 14px;
    border: 1px dashed var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-high);
  }

  .toast-preview p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  .toast-stack {
    position: fixed;
    top: 88px;
    right: 24px;
    display: flex;
    flex-direction: column;
    gap: 10px;
    z-index: 200;
  }

  .toast-card {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 14px;
    border-radius: 16px;
    background-color: var(--md-sys-color-surface);
    border: 1px solid var(--md-sys-color-outline-variant);
    min-width: 260px;
    box-shadow: 0px 6px 16px rgba(0, 0, 0, 0.16);
  }

  .toast-card p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  .toast-card .md-icon {
    font-size: 20px;
    color: var(--md-sys-color-primary);
  }

  .toast-card.success {
    border-color: var(--md-sys-color-secondary-container);
  }

  .toast-card.warning {
    border-color: var(--md-sys-color-tertiary-container);
  }

  .toast-card.error {
    border-color: var(--md-sys-color-error);
  }
</style>
