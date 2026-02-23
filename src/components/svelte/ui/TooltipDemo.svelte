<script>
    // ── Tooltip state factory ──
    function createTooltip() {
        let visible = $state(false);
        let timer;
        return {
            get visible() {
                return visible;
            },
            show() {
                clearTimeout(timer);
                timer = setTimeout(() => (visible = true), 500);
            },
            hide() {
                clearTimeout(timer);
                visible = false;
            },
        };
    }

    // satu instance per tooltip
    const t1 = createTooltip();
    const t2 = createTooltip();
    const t3 = createTooltip();
    const t4 = createTooltip();
    const t5 = createTooltip();
    const t6 = createTooltip();
    const t7 = createTooltip();
    const t8 = createTooltip();
    const t9 = createTooltip();
</script>

<section class="tooltip-demo">
    <div class="demo-row">
        <p class="demo-label">Positions</p>
        <div class="demo-group">
            <!-- Top -->
            <div
                class="tooltip-wrapper"
                onmouseenter={t1.show}
                onmouseleave={t1.hide}
                onfocusin={t1.show}
                onfocusout={t1.hide}
            >
                <button class="md-btn md-btn-tonal">Top</button>
                <div
                    class="tooltip-content tooltip-top"
                    class:visible={t1.visible}
                    role="tooltip"
                >
                    Top tooltip
                </div>
            </div>

            <!-- Bottom -->
            <div
                class="tooltip-wrapper"
                onmouseenter={t2.show}
                onmouseleave={t2.hide}
                onfocusin={t2.show}
                onfocusout={t2.hide}
            >
                <button class="md-btn md-btn-tonal">Bottom</button>
                <div
                    class="tooltip-content tooltip-bottom"
                    class:visible={t2.visible}
                    role="tooltip"
                >
                    Bottom tooltip
                </div>
            </div>

            <!-- Left -->
            <div
                class="tooltip-wrapper"
                onmouseenter={t3.show}
                onmouseleave={t3.hide}
                onfocusin={t3.show}
                onfocusout={t3.hide}
            >
                <button class="md-btn md-btn-tonal">Left</button>
                <div
                    class="tooltip-content tooltip-left"
                    class:visible={t3.visible}
                    role="tooltip"
                >
                    Left tooltip
                </div>
            </div>

            <!-- Right -->
            <div
                class="tooltip-wrapper"
                onmouseenter={t4.show}
                onmouseleave={t4.hide}
                onfocusin={t4.show}
                onfocusout={t4.hide}
            >
                <button class="md-btn md-btn-tonal">Right</button>
                <div
                    class="tooltip-content tooltip-right"
                    class:visible={t4.visible}
                    role="tooltip"
                >
                    Right tooltip
                </div>
            </div>
        </div>
    </div>

    <div class="demo-row">
        <p class="demo-label">Dengan berbagai elemen</p>
        <div class="demo-group">
            <div
                class="tooltip-wrapper"
                onmouseenter={t5.show}
                onmouseleave={t5.hide}
                onfocusin={t5.show}
                onfocusout={t5.hide}
            >
                <button class="md-btn md-btn-filled">Filled</button>
                <div
                    class="tooltip-content tooltip-top"
                    class:visible={t5.visible}
                    role="tooltip"
                >
                    Filled button action
                </div>
            </div>

            <div
                class="tooltip-wrapper"
                onmouseenter={t6.show}
                onmouseleave={t6.hide}
                onfocusin={t6.show}
                onfocusout={t6.hide}
            >
                <button class="md-btn md-btn-outlined">Outlined</button>
                <div
                    class="tooltip-content tooltip-top"
                    class:visible={t6.visible}
                    role="tooltip"
                >
                    Outlined action
                </div>
            </div>

            <div
                class="tooltip-wrapper"
                onmouseenter={t7.show}
                onmouseleave={t7.hide}
                onfocusin={t7.show}
                onfocusout={t7.hide}
            >
                <button class="md-icon-btn">
                    <span class="md-icon">delete</span>
                </button>
                <div
                    class="tooltip-content tooltip-top"
                    class:visible={t7.visible}
                    role="tooltip"
                >
                    Delete item
                </div>
            </div>

            <div
                class="tooltip-wrapper"
                onmouseenter={t8.show}
                onmouseleave={t8.hide}
                onfocusin={t8.show}
                onfocusout={t8.hide}
            >
                <button class="md-icon-btn">
                    <span class="md-icon">edit</span>
                </button>
                <div
                    class="tooltip-content tooltip-top"
                    class:visible={t8.visible}
                    role="tooltip"
                >
                    Edit item
                </div>
            </div>

            <div
                class="tooltip-wrapper"
                onmouseenter={t9.show}
                onmouseleave={t9.hide}
                onfocusin={t9.show}
                onfocusout={t9.hide}
            >
                <button class="md-icon-btn md-icon-btn-tonal">
                    <span class="md-icon">share</span>
                </button>
                <div
                    class="tooltip-content tooltip-top"
                    class:visible={t9.visible}
                    role="tooltip"
                >
                    Share
                </div>
            </div>
        </div>
    </div>
</section>

<style>
    /* ── Layout ── */
    .tooltip-demo {
        display: flex;
        flex-direction: column;
        gap: 32px;
        padding: 32px 16px;
    }
    .demo-row {
        display: flex;
        flex-direction: column;
        gap: 12px;
    }
    .demo-label {
        margin: 0;
        font-size: var(--md-sys-typescale-label-medium-size, 12px);
        font-weight: var(--md-sys-typescale-label-medium-weight, 500);
        letter-spacing: var(--md-sys-typescale-label-medium-tracking, 0.5px);
        color: var(--md-sys-color-on-surface-variant, #49454f);
        text-transform: uppercase;
    }
    .demo-group {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        gap: 12px;
    }

    /* ── Tooltip wrapper ── */
    .tooltip-wrapper {
        position: relative;
        display: inline-flex;
    }

    /* ── Tooltip base ── */
    .tooltip-content {
        position: absolute;
        z-index: 300;
        background-color: var(--md-sys-color-inverse-surface, #313033);
        color: var(--md-sys-color-inverse-on-surface, #f4eff4);
        padding: 6px 10px;
        border-radius: var(--md-sys-shape-corner-extra-small, 4px);
        font-size: var(--md-sys-typescale-label-small-size, 11px);
        font-weight: var(--md-sys-typescale-label-small-weight, 500);
        letter-spacing: var(--md-sys-typescale-label-small-tracking, 0.5px);
        font-family: inherit;
        white-space: nowrap;
        pointer-events: none;
        opacity: 0;
        transition:
            opacity var(--md-sys-motion-duration-short3, 150ms)
                var(--md-sys-motion-easing-standard, cubic-bezier(0.2, 0, 0, 1)),
            transform var(--md-sys-motion-duration-short3, 150ms)
                var(
                    --md-sys-motion-easing-emphasized-decelerate,
                    cubic-bezier(0.05, 0.7, 0.1, 1)
                );
    }
    .tooltip-content.visible {
        opacity: 1;
    }

    /* ── Positions ── */
    .tooltip-top {
        bottom: calc(100% + 8px);
        left: 50%;
        transform: translateX(-50%) scale(0.9);
        transform-origin: center bottom;
    }
    .tooltip-top.visible {
        transform: translateX(-50%) scale(1);
    }

    .tooltip-bottom {
        top: calc(100% + 8px);
        left: 50%;
        transform: translateX(-50%) scale(0.9);
        transform-origin: center top;
    }
    .tooltip-bottom.visible {
        transform: translateX(-50%) scale(1);
    }

    .tooltip-left {
        right: calc(100% + 8px);
        top: 50%;
        transform: translateY(-50%) scale(0.9);
        transform-origin: right center;
    }
    .tooltip-left.visible {
        transform: translateY(-50%) scale(1);
    }

    .tooltip-right {
        left: calc(100% + 8px);
        top: 50%;
        transform: translateY(-50%) scale(0.9);
        transform-origin: left center;
    }
    .tooltip-right.visible {
        transform: translateY(-50%) scale(1);
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
        border-radius: 9999px;
        font-family: inherit;
        font-size: 14px;
        font-weight: 500;
        letter-spacing: 0.1px;
        cursor: pointer;
        user-select: none;
        outline: none;
        position: relative;
        overflow: hidden;
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

    .md-btn-filled {
        background-color: var(--md-sys-color-primary, #6750a4);
        color: var(--md-sys-color-on-primary, #fff);
    }
    .md-btn-tonal {
        background-color: var(--md-sys-color-secondary-container, #e8def8);
        color: var(--md-sys-color-on-secondary-container, #1d192b);
    }
    .md-btn-outlined {
        background: transparent;
        color: var(--md-sys-color-primary, #6750a4);
        border: 1px solid var(--md-sys-color-outline, #79747e);
        padding: 0 23px;
    }

    /* ── Icon button ── */
    .md-icon-btn {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        width: 40px;
        height: 40px;
        border: none;
        border-radius: 9999px;
        background: transparent;
        color: var(--md-sys-color-on-surface-variant, #49454f);
        cursor: pointer;
        user-select: none;
        outline: none;
        padding: 0;
        position: relative;
        overflow: hidden;
    }
    .md-icon-btn::after {
        content: "";
        position: absolute;
        inset: 0;
        border-radius: inherit;
        background: currentColor;
        opacity: 0;
        transition: opacity 200ms cubic-bezier(0.2, 0, 0, 1);
        pointer-events: none;
    }
    .md-icon-btn:hover::after {
        opacity: 0.08;
    }
    .md-icon-btn:active::after {
        opacity: 0.12;
    }
    .md-icon-btn-tonal {
        background-color: var(--md-sys-color-secondary-container, #e8def8);
        color: var(--md-sys-color-on-secondary-container, #1d192b);
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
</style>
