<script>
    let demos = [
        {
            label: "Linear determinate (70%)",
            type: "linear",
            variant: "determinate",
            value: 70,
        },
        {
            label: "Linear indeterminate",
            type: "linear",
            variant: "indeterminate",
            value: 0,
        },
        {
            label: "Circular determinate (70%)",
            type: "circular",
            variant: "determinate",
            value: 70,
            size: 48,
            strokeWidth: 4,
        },
        {
            label: "Circular indeterminate",
            type: "circular",
            variant: "indeterminate",
            value: 0,
            size: 48,
            strokeWidth: 4,
        },
        {
            label: "Circular large (64px)",
            type: "circular",
            variant: "indeterminate",
            value: 0,
            size: 64,
            strokeWidth: 5,
        },
    ];

    function getCircumference(size, strokeWidth) {
        const r = size / 2 - strokeWidth;
        return 2 * Math.PI * r;
    }

    function getDashOffset(size, strokeWidth, value) {
        const c = getCircumference(size, strokeWidth);
        return c - (value / 100) * c;
    }
</script>

<section class="progress-demo">
    {#each demos as demo}
        <div class="progress-block">
            <p class="label">{demo.label}</p>

            {#if demo.type === "linear"}
                <div
                    class="md-progress-linear"
                    class:indeterminate={demo.variant === "indeterminate"}
                    role="progressbar"
                    aria-valuenow={demo.variant === "determinate"
                        ? demo.value
                        : undefined}
                    aria-valuemin="0"
                    aria-valuemax="100"
                >
                    {#if demo.variant === "determinate"}
                        <div
                            class="linear-track"
                            style="width: {demo.value}%;"
                        ></div>
                    {:else}
                        <div class="linear-bar bar1"></div>
                        <div class="linear-bar bar2"></div>
                    {/if}
                </div>
            {:else if demo.type === "circular"}
                {@const size = demo.size ?? 48}
                {@const sw = demo.strokeWidth ?? 4}
                {@const r = size / 2 - sw}
                {@const circ = getCircumference(size, sw)}
                <div
                    class="md-progress-circular"
                    class:indeterminate={demo.variant === "indeterminate"}
                    style="width:{size}px; height:{size}px;"
                    role="progressbar"
                    aria-valuenow={demo.variant === "determinate"
                        ? demo.value
                        : undefined}
                    aria-valuemin="0"
                    aria-valuemax="100"
                >
                    <svg viewBox="0 0 {size} {size}">
                        <circle
                            class="circ-track"
                            cx={size / 2}
                            cy={size / 2}
                            {r}
                            stroke-width={sw}
                        />
                        <circle
                            class="circ-indicator"
                            cx={size / 2}
                            cy={size / 2}
                            {r}
                            stroke-width={sw}
                            stroke-dasharray={circ}
                            stroke-dashoffset={demo.variant === "determinate"
                                ? getDashOffset(size, sw, demo.value)
                                : undefined}
                        />
                    </svg>
                </div>
            {/if}
        </div>
    {/each}
</section>

<style>
    /* ── Layout ── */
    .progress-demo {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
        gap: 16px;
    }

    .progress-block {
        display: flex;
        flex-direction: column;
        gap: 12px;
        padding: 16px;
        border-radius: 16px;
        background-color: var(--md-sys-color-surface-container);
        align-items: flex-start;
    }

    .label {
        margin: 0;
        color: var(--md-sys-color-on-surface-variant);
        font-size: var(--md-sys-typescale-label-medium-size);
        font-weight: var(--md-sys-typescale-label-medium-weight);
        letter-spacing: var(--md-sys-typescale-label-medium-tracking);
    }

    /* ── Linear ── */
    .md-progress-linear {
        width: 100%;
        height: 4px;
        background-color: var(--md-sys-color-surface-container-highest);
        border-radius: 2px;
        overflow: hidden;
        position: relative;
    }

    /* Determinate */
    .linear-track {
        height: 100%;
        background-color: var(--md-sys-color-primary);
        border-radius: 2px;
        transition: width var(--md-sys-motion-duration-medium2)
            var(--md-sys-motion-easing-standard);
    }

    /* Indeterminate — dua bar Material 3 */
    .linear-bar {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        background-color: var(--md-sys-color-primary);
        border-radius: 2px;
        will-change: left, width;
    }

    .bar1 {
        animation: linear-bar1 2.1s cubic-bezier(0.65, 0.815, 0.735, 0.395)
            infinite;
    }

    .bar2 {
        animation: linear-bar2 2.1s cubic-bezier(0.165, 0.84, 0.44, 1) infinite;
        animation-delay: 1.15s;
    }

    @keyframes linear-bar1 {
        0% {
            left: -35%;
            width: 35%;
        }
        60% {
            left: 100%;
            width: 90%;
        }
        100% {
            left: 100%;
            width: 90%;
        }
    }

    @keyframes linear-bar2 {
        0% {
            left: -200%;
            width: 100%;
        }
        60% {
            left: 107%;
            width: 10%;
        }
        100% {
            left: 107%;
            width: 10%;
        }
    }

    /* ── Circular ── */
    .md-progress-circular {
        display: inline-flex;
        align-items: center;
        justify-content: center;
    }

    .md-progress-circular svg {
        width: 100%;
        height: 100%;
        transform: rotate(-90deg);
        transform-origin: center;
    }

    .circ-track {
        fill: none;
        stroke: var(--md-sys-color-surface-container-highest);
    }

    .circ-indicator {
        fill: none;
        stroke: var(--md-sys-color-primary);
        stroke-linecap: round;
        transition: stroke-dashoffset var(--md-sys-motion-duration-medium2)
            var(--md-sys-motion-easing-standard);
    }

    /* Indeterminate circular */
    .md-progress-circular.indeterminate svg {
        animation: circ-rotate 1.4s linear infinite;
        transform: none;
    }

    .md-progress-circular.indeterminate .circ-indicator {
        animation: circ-dash 1.4s ease-in-out infinite;
    }

    @keyframes circ-rotate {
        0% {
            transform: rotate(0deg);
        }
        100% {
            transform: rotate(360deg);
        }
    }

    @keyframes circ-dash {
        0% {
            stroke-dasharray: 1 999;
            stroke-dashoffset: 0;
        }
        50% {
            stroke-dasharray: 80 999;
            stroke-dashoffset: -30;
        }
        100% {
            stroke-dasharray: 80 999;
            stroke-dashoffset: -124;
        }
    }
</style>
