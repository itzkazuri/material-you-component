<script>
  import Hero from './Hero.svelte';
  import SectionHeader from './SectionHeader.svelte';
  import TokenShowcase from './TokenShowcase.svelte';
  import ComponentGallery from './ComponentGallery.svelte';
</script>

<div class="home" id="home">
  <Hero
    title="Build product-ready Material You UIs"
    subtitle="A modular Svelte showcase for Material Design 3 tokens, surfaces, and components. Update the theme in the sidebar to see everything respond instantly."
    note="Open `src/components/svelte/showcase` to edit each section independently."
  />

  <SectionHeader
    title="Get started"
    subtitle="Start with the building blocks and expand into full pages."
  />
  <div class="doc-grid" id="get-started">
    <article>
      <h3 class="md-title-medium">Setup</h3>
      <p class="md-body-small">Install the tokens and wire up your layout with Svelte components.</p>
    </article>
    <article>
      <h3 class="md-title-medium">Theming</h3>
      <p class="md-body-small">Switch seed colors and surface modes from the sidebar controls.</p>
    </article>
    <article>
      <h3 class="md-title-medium">Scale</h3>
      <p class="md-body-small">Reuse these modules for documentation, product, and marketing pages.</p>
    </article>
  </div>

  <SectionHeader
    title="Design system foundations"
    subtitle="Core tokens that power every surface, component, and state layer."
  />
  <div id="foundations">
    <TokenShowcase />
  </div>

  <SectionHeader
    title="Component previews"
    subtitle="Quickly validate how Material You components feel together."
  />
  <div id="components">
    <ComponentGallery />
  </div>

  <SectionHeader
    title="Styles"
    subtitle="Document voice, elevation, and layout patterns for your product."
  />
  <div class="doc-grid" id="styles">
    <article>
      <h3 class="md-title-medium">Guides</h3>
      <p class="md-body-small">Explain tokens, motion, and layout guidelines with live samples.</p>
    </article>
    <article>
      <h3 class="md-title-medium">Resources</h3>
      <p class="md-body-small">Provide starter kits, Figma files, and usage best practices.</p>
    </article>
    <article>
      <h3 class="md-title-medium">Updates</h3>
      <p class="md-body-small">Share changes to components and system-wide decisions.</p>
    </article>
  </div>

  <SectionHeader
    title="Develop"
    subtitle="Reference implementation details and accessibility guidance."
  />
  <div class="doc-grid" id="develop">
    <article>
      <h3 class="md-title-medium">Tokens API</h3>
      <p class="md-body-small">Map your tokens to code so designers and devs stay aligned.</p>
    </article>
    <article>
      <h3 class="md-title-medium">Components API</h3>
      <p class="md-body-small">Document props, slots, and state behavior for each module.</p>
    </article>
    <article>
      <h3 class="md-title-medium">Accessibility</h3>
      <p class="md-body-small">Keep contrast, focus, and keyboard patterns consistent.</p>
    </article>
  </div>

  <SectionHeader
    title="Blog"
    subtitle="Announcements and release notes for your design system."
  />
  <div class="doc-grid" id="blog">
    <article>
      <h3 class="md-title-medium">Release 1.0</h3>
      <p class="md-body-small">New surfaces, modular Svelte sections, and dynamic theming.</p>
    </article>
    <article>
      <h3 class="md-title-medium">Motion study</h3>
      <p class="md-body-small">Exploring Material easing curves across core interactions.</p>
    </article>
    <article>
      <h3 class="md-title-medium">Component audit</h3>
      <p class="md-body-small">QA notes and improvements on core navigation patterns.</p>
    </article>
  </div>
</div>

<style>
  .home {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .doc-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 16px;
  }

  .doc-grid article {
    padding: 16px;
    border-radius: 18px;
    border: 1px solid var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-low);
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .doc-grid h3 {
    margin: 0;
    color: var(--md-sys-color-on-surface);
  }

  .doc-grid p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }
</style>
