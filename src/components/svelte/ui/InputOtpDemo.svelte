<section class="otp-demo">
  <div class="otp-group">
    <input type="text" maxlength="1" value="7" />
    <input type="text" maxlength="1" value="2" />
    <input type="text" maxlength="1" value="4" />
    <input type="text" maxlength="1" value="9" />
    <input type="text" maxlength="1" value="1" />
  </div>
  <p class="md-body-small">One-time password input for verification flows.</p>
</section>

<style>
  .otp-demo {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .otp-group {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .otp-group input {
    width: 48px;
    height: 52px;
    text-align: center;
    border-radius: 14px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-high);
    color: var(--md-sys-color-on-surface);
    font-size: 18px;
  }

  .otp-demo p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }
</style>
