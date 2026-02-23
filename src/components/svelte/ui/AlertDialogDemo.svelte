<script>
  let open = false;
</script>

<div class="dialog-demo">
  <button class="md-btn md-btn-filled" on:click={() => (open = true)}>Open dialog</button>
</div>

<div class="md-dialog-scrim {open ? 'md-dialog-open' : ''}">
  <div class="md-dialog" role="dialog" aria-modal="true" aria-labelledby="alert-title">
    <div class="md-dialog-icon">
      <span class="md-icon">warning</span>
    </div>
    <div class="md-dialog-headline" id="alert-title">Delete component?</div>
    <div class="md-dialog-content">
      This action cannot be undone. The component and its documentation will be removed.
    </div>
    <div class="md-dialog-actions">
      <button class="md-btn md-btn-text" on:click={() => (open = false)}>Cancel</button>
      <button class="md-btn md-btn-filled" on:click={() => (open = false)}>Delete</button>
    </div>
  </div>
</div>
