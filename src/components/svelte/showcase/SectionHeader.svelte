<script>
  let { title, subtitle = '' } = $props();
</script>

<section class="section-header">
  <h2 class="md-title-large">{title}</h2>
  {#if subtitle}
    <p class="md-body-medium">{subtitle}</p>
  {/if}
</section>

<style>
  .section-header {
    display: flex;
    flex-direction: column;
    gap: 6px;
    margin: 36px 0 18px;
  }

  .section-header h2 {
    margin: 0;
    color: var(--md-sys-color-on-surface);
  }

  .section-header p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }
</style>
