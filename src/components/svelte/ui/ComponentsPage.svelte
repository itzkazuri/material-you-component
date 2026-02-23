<script>
  import ButtonDemo from './ButtonDemo.svelte';
  import AlertDemo from './AlertDemo.svelte';
  import AlertDialogDemo from './AlertDialogDemo.svelte';
  import BreadcrumbDemo from './BreadcrumbDemo.svelte';
  import CalendarDemo from './CalendarDemo.svelte';
  import DrawerDemo from './DrawerDemo.svelte';
  import DropdownDemo from './DropdownDemo.svelte';
  import FormDemo from './FormDemo.svelte';
  import InputOtpDemo from './InputOtpDemo.svelte';
  import SidebarDemo from './SidebarDemo.svelte';
  import ScrollAreaDemo from './ScrollAreaDemo.svelte';
  import TooltipDemo from './TooltipDemo.svelte';
  import BadgeDemo from './BadgeDemo.svelte';
  import ProfilePictureDemo from './ProfilePictureDemo.svelte';
  import ProgressDemo from './ProgressDemo.svelte';
  import SkeletonDemo from './SkeletonDemo.svelte';
  import ToastDemo from './ToastDemo.svelte';
</script>

<div class="components-page">
  <header class="page-header">
    <div>
      <p class="md-label-medium">Components</p>
      <h1 class="md-headline-small">UI documentation</h1>
      <p class="md-body-medium">Reusable modules built with Material You tokens.</p>
    </div>
    <div class="status-chip">
      <span class="md-icon">rocket_launch</span>
      <span class="md-label-medium">Preview</span>
    </div>
  </header>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Buttons</h2>
      <p class="md-body-small">Primary, tonal, and outlined actions for key flows.</p>
    </div>
    <ButtonDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Alert</h2>
      <p class="md-body-small">Inline alerts for status messaging.</p>
    </div>
    <AlertDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Alert dialog</h2>
      <p class="md-body-small">Confirmation dialog with Material You surfaces.</p>
    </div>
    <AlertDialogDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Breadcrumb</h2>
      <p class="md-body-small">Contextual navigation for nested pages.</p>
    </div>
    <BreadcrumbDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Calendar</h2>
      <p class="md-body-small">Date picker layout for scheduling flows.</p>
    </div>
    <CalendarDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Drawer</h2>
      <p class="md-body-small">Permanent navigation drawer example.</p>
    </div>
    <DrawerDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Dropdown</h2>
      <p class="md-body-small">Selection controls for compact forms.</p>
    </div>
    <DropdownDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Form</h2>
      <p class="md-body-small">Text fields and toggles grouped together.</p>
    </div>
    <FormDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Input OTP</h2>
      <p class="md-body-small">Verification inputs for short codes.</p>
    </div>
    <InputOtpDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Sidebar</h2>
      <p class="md-body-small">Navigation drawer example for desktop layouts.</p>
    </div>
    <SidebarDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Profile picture</h2>
      <p class="md-body-small">Avatar styles for teams and presence.</p>
    </div>
    <ProfilePictureDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Scroll area</h2>
      <p class="md-body-small">Contained scroll surfaces for long content.</p>
    </div>
    <ScrollAreaDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Tooltip</h2>
      <p class="md-body-small">Hover and focus helper labels.</p>
    </div>
    <TooltipDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Badge</h2>
      <p class="md-body-small">Notification counts and status indicators.</p>
    </div>
    <BadgeDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Progress</h2>
      <p class="md-body-small">Linear and circular progress indicators.</p>
    </div>
    <ProgressDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Skeleton</h2>
      <p class="md-body-small">Loading placeholders for page content.</p>
    </div>
    <SkeletonDemo />
  </section>

  <section class="doc-section">
    <div class="section-title">
      <h2 class="md-title-large">Toast</h2>
      <p class="md-body-small">Snack-like feedback for quick confirmations.</p>
    </div>
    <ToastDemo />
  </section>
</div>

<style>
  .components-page {
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  .page-header {
    display: flex;
    justify-content: space-between;
    gap: 16px;
    flex-wrap: wrap;
    padding: 20px 24px;
    border-radius: 24px;
    background: linear-gradient(135deg, rgba(103, 80, 164, 0.18), rgba(255, 255, 255, 0.08));
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .page-header h1 {
    margin: 6px 0 8px;
  }

  .page-header p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  .status-chip {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 14px;
    border-radius: 999px;
    background-color: var(--md-sys-color-secondary-container);
    color: var(--md-sys-color-on-secondary-container);
    height: fit-content;
  }

  .doc-section {
    display: flex;
    flex-direction: column;
    gap: 12px;
    padding: 18px 20px;
    border-radius: 20px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-low);
  }

  .section-title h2 {
    margin: 0 0 4px;
  }

  .section-title p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }
</style>
