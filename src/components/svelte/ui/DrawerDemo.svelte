<script>
    /**
     * Drawer.svelte — Material You modal bottom drawer
     *
     * Props:
     *   open        : boolean ($bindable)
     *   title       : string
     *   description : string
     *   items       : nav items array
     *   activeItem  : string id
     *   onSelect    : (id) => void
     *
     * Slots:
     *   trigger  — elemen pembuka drawer (default: tombol "Open Drawer")
     *   default  — konten custom (override nav items)
     *   footer   — tombol di bawah (default: tombol Tutup)
     */

    let {
        open = $bindable(false),
        title = "Menu",
        description = "",
        items = [
            { id: "home", label: "Home", icon: "home" },
            { id: "themes", label: "Themes", icon: "auto_awesome" },
            { id: "layouts", label: "Layouts", icon: "view_quilt" },
            { type: "section", label: "Library" },
            { id: "components", label: "Components", icon: "widgets" },
            { id: "about", label: "About", icon: "info" },
        ],
        activeItem = "home",
        onSelect = (id) => {},
    } = $props();

    let selected = $state(activeItem);

    function handleSelect(id) {
        selected = id;
        onSelect(id);
        close();
    }

    function close() {
        open = false;
    }

    function handleKeydown(e) {
        if (e.key === "Escape") close();
    }
</script>

<svelte:window onkeydown={handleKeydown} />

<!-- ── Trigger ── -->
<slot name="trigger">
    <button
        class="md-btn md-btn-outlined trigger-default"
        onclick={() => (open = true)}
    >
        <span class="md-icon">menu</span>
        Open Drawer
    </button>
</slot>

<!-- ── Scrim ── -->
<!-- svelte-ignore a11y_click_events_have_key_events -->
<!-- svelte-ignore a11y_no_static_element_interactions -->
<div class="drawer-scrim" class:visible={open} onclick={close}></div>

<!-- ── Panel ── -->
<div
    class="drawer-panel"
    class:open
    role="dialog"
    aria-modal="true"
    aria-label={title}
>
    <!-- Handle bar -->
    <div class="drawer-handle"></div>

    <!-- Header -->
    {#if title || description}
        <div class="drawer-header">
            {#if title}<h2 class="drawer-title">{title}</h2>{/if}
            {#if description}<p class="drawer-description">
                    {description}
                </p>{/if}
        </div>
    {/if}

    <!-- Content -->
    <div class="drawer-content">
        <slot>
            {#each items as item}
                {#if item.type === "section"}
                    <div class="md-drawer-section-label">{item.label}</div>
                {:else}
                    <button
                        class="md-drawer-item"
                        class:md-drawer-item-active={selected === item.id}
                        onclick={() => handleSelect(item.id)}
                    >
                        <span
                            class="md-icon"
                            class:md-icon-filled={selected === item.id}
                        >
                            {item.icon}
                        </span>
                        {item.label}
                    </button>
                {/if}
            {/each}
        </slot>
    </div>

    <!-- Footer -->
    <div class="drawer-footer">
        <slot name="footer">
            <button class="md-btn md-btn-filled" onclick={close}>Tutup</button>
        </slot>
    </div>
</div>

<style>
    /* ── Scrim ── */
    .drawer-scrim {
        position: fixed;
        inset: 0;
        background: transparent;
        z-index: 200;
        pointer-events: none;
        transition: background var(--md-sys-motion-duration-medium2, 300ms)
            var(--md-sys-motion-easing-standard, cubic-bezier(0.2, 0, 0, 1));
    }
    .drawer-scrim.visible {
        background: rgba(0, 0, 0, 0.32);
        pointer-events: all;
    }

    /* ── Panel ── */
    .drawer-panel {
        position: fixed;
        bottom: 0;
        left: 0;
        right: 0;
        z-index: 201;
        background-color: var(--md-sys-color-surface-container-low, #f7f2fa);
        border-radius: var(--md-sys-shape-corner-extra-large, 28px)
            var(--md-sys-shape-corner-extra-large, 28px) 0 0;
        display: flex;
        flex-direction: column;
        max-height: 90dvh;
        /* hidden state */
        transform: translateY(100%);
        visibility: hidden;
        transition:
            transform var(--md-sys-motion-duration-medium2, 300ms)
                var(
                    --md-sys-motion-easing-emphasized-decelerate,
                    cubic-bezier(0.05, 0.7, 0.1, 1)
                ),
            visibility 0ms var(--md-sys-motion-duration-medium2, 300ms);
        box-shadow:
            0px 4px 4px rgba(0, 0, 0, 0.3),
            0px 8px 12px 6px rgba(0, 0, 0, 0.15);
    }
    .drawer-panel.open {
        transform: translateY(0);
        visibility: visible;
        transition:
            transform var(--md-sys-motion-duration-medium2, 300ms)
                var(
                    --md-sys-motion-easing-emphasized-decelerate,
                    cubic-bezier(0.05, 0.7, 0.1, 1)
                ),
            visibility 0ms 0ms;
    }

    /* ── Handle ── */
    .drawer-handle {
        width: 32px;
        height: 4px;
        border-radius: 2px;
        background-color: var(--md-sys-color-on-surface-variant, #49454f);
        opacity: 0.4;
        margin: 12px auto 0;
        flex-shrink: 0;
    }

    /* ── Header ── */
    .drawer-header {
        padding: 20px 24px 8px;
        flex-shrink: 0;
    }
    .drawer-title {
        margin: 0;
        font-size: var(--md-sys-typescale-headline-small-size, 24px);
        font-weight: var(--md-sys-typescale-headline-small-weight, 400);
        line-height: var(--md-sys-typescale-headline-small-line-height, 32px);
        color: var(--md-sys-color-on-surface, #1c1b1f);
        font-family: inherit;
    }
    .drawer-description {
        margin: 4px 0 0;
        font-size: var(--md-sys-typescale-body-medium-size, 14px);
        color: var(--md-sys-color-on-surface-variant, #49454f);
        font-family: inherit;
    }

    /* ── Content ── */
    .drawer-content {
        flex: 1;
        overflow-y: auto;
        padding: 0 12px;
    }

    /* ── Footer ── */
    .drawer-footer {
        padding: 16px 24px 32px;
        display: flex;
        flex-direction: column;
        gap: 8px;
        flex-shrink: 0;
    }

    /* ── Nav items ── */
    .md-drawer-item {
        display: flex;
        align-items: center;
        gap: 12px;
        height: 56px;
        padding: 0 16px;
        border-radius: var(--md-sys-shape-corner-full, 9999px);
        cursor: pointer;
        color: var(--md-sys-color-on-surface-variant, #49454f);
        font-size: var(--md-sys-typescale-label-large-size, 14px);
        font-weight: var(--md-sys-typescale-label-large-weight, 500);
        letter-spacing: var(--md-sys-typescale-label-large-tracking, 0.1px);
        border: none;
        background: transparent;
        width: 100%;
        text-align: left;
        user-select: none;
        outline: none;
        position: relative;
        overflow: hidden;
        transition: color var(--md-sys-motion-duration-short4, 200ms)
            var(--md-sys-motion-easing-standard, cubic-bezier(0.2, 0, 0, 1));
        font-family: inherit;
    }
    .md-drawer-item::after {
        content: "";
        position: absolute;
        inset: 0;
        background: currentColor;
        opacity: 0;
        transition: opacity var(--md-sys-motion-duration-short4, 200ms)
            var(--md-sys-motion-easing-standard, cubic-bezier(0.2, 0, 0, 1));
        pointer-events: none;
    }
    .md-drawer-item:hover::after {
        opacity: 0.08;
    }
    .md-drawer-item:active::after {
        opacity: 0.12;
    }
    .md-drawer-item.md-drawer-item-active {
        background-color: var(--md-sys-color-secondary-container, #e8def8);
        color: var(--md-sys-color-on-secondary-container, #1d192b);
    }
    .md-drawer-section-label {
        padding: 12px 28px 4px;
        font-size: var(--md-sys-typescale-title-small-size, 14px);
        font-weight: var(--md-sys-typescale-title-small-weight, 500);
        color: var(--md-sys-color-on-surface-variant, #49454f);
    }

    /* ── Buttons ── */
    .md-btn {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        gap: 8px;
        height: 40px;
        padding: 0 24px;
        border: none;
        border-radius: var(--md-sys-shape-corner-full, 9999px);
        font-family: inherit;
        font-size: var(--md-sys-typescale-label-large-size, 14px);
        font-weight: var(--md-sys-typescale-label-large-weight, 500);
        letter-spacing: var(--md-sys-typescale-label-large-tracking, 0.1px);
        cursor: pointer;
        user-select: none;
        outline: none;
        position: relative;
        overflow: hidden;
        width: 100%;
    }
    .md-btn-filled {
        background-color: var(--md-sys-color-primary, #6750a4);
        color: var(--md-sys-color-on-primary, #fff);
    }
    .md-btn-outlined {
        background-color: transparent;
        color: var(--md-sys-color-primary, #6750a4);
        border: 1px solid var(--md-sys-color-outline, #79747e);
        width: auto;
        padding: 0 24px;
    }
    .md-btn::after {
        content: "";
        position: absolute;
        inset: 0;
        background: currentColor;
        opacity: 0;
        transition: opacity 200ms cubic-bezier(0.2, 0, 0, 1);
        pointer-events: none;
    }
    .md-btn:hover::after {
        opacity: 0.08;
    }
    .md-btn:active::after {
        opacity: 0.12;
    }

    .trigger-default {
        width: auto;
    }

    /* ── Material Icons ── */
    :global(.md-icon) {
        font-family:
            "Material Symbols Rounded", "Material Symbols Outlined",
            "Material Icons";
        font-weight: normal;
        font-style: normal;
        font-size: 24px;
        line-height: 1;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        width: 24px;
        height: 24px;
        user-select: none;
        flex-shrink: 0;
        font-variation-settings:
            "FILL" 0,
            "wght" 400,
            "GRAD" 0,
            "opsz" 24;
    }
    :global(.md-icon-filled) {
        font-variation-settings:
            "FILL" 1,
            "wght" 400,
            "GRAD" 0,
            "opsz" 24;
    }
</style>
