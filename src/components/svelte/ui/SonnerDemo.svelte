<script>
  let queue = [];

  const pushNotice = (variant) => {
    const id = crypto.randomUUID();
    const entry = {
      id,
      title: variant === 'success' ? 'Synced' : variant === 'warning' ? 'Check this' : 'Update',
      message:
        variant === 'success'
          ? 'Theme saved to your profile.'
          : variant === 'warning'
          ? 'Contrast needs improvement.'
          : 'New Material You components are ready.',
      variant,
    };
    queue = [entry, ...queue].slice(0, 3);
    setTimeout(() => {
      queue = queue.filter((item) => item.id !== id);
    }, 2600);
  };
</script>

<div class="sonner-demo">
  <div class="sonner-actions">
    <button class="md-btn md-btn-filled" on:click={() => pushNotice('default')}>Show sonner</button>
    <button class="md-btn md-btn-tonal" on:click={() => pushNotice('success')}>Success</button>
    <button class="md-btn md-btn-outlined" on:click={() => pushNotice('warning')}>Warning</button>
  </div>

  <div class="sonner-surface">
    {#if queue.length === 0}
      <p class="md-body-small">Trigger a sonner notification to preview the stack.</p>
    {/if}
    <div class="sonner-list">
      {#each queue as item (item.id)}
        <div class="sonner-card {item.variant}">
          <div>
            <p class="md-label-medium">{item.title}</p>
            <p class="md-body-small">{item.message}</p>
          </div>
          <span class="md-icon">close</span>
        </div>
      {/each}
    </div>
  </div>
</div>

<style>
  .sonner-demo {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .sonner-actions {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .sonner-surface {
    padding: 16px;
    border-radius: 18px;
    border: 1px dashed var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-high);
    min-height: 140px;
  }

  .sonner-surface p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  .sonner-list {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 12px;
  }

  .sonner-card {
    display: flex;
    justify-content: space-between;
    gap: 12px;
    padding: 12px 14px;
    border-radius: 16px;
    background-color: var(--md-sys-color-surface);
    border: 1px solid var(--md-sys-color-outline-variant);
    align-items: center;
  }

  .sonner-card p {
    margin: 0;
  }

  .sonner-card .md-icon {
    font-size: 18px;
    color: var(--md-sys-color-on-surface-variant);
  }

  .sonner-card.success {
    border-color: var(--md-sys-color-secondary-container);
  }

  .sonner-card.warning {
    border-color: var(--md-sys-color-tertiary-container);
  }
</style>
