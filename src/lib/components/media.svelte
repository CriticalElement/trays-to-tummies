<div class="media-container">
    <slot />
</div>

<style lang="scss">
    .media-container {
        position: relative;
        border: 0.125rem solid var(--accent);
        margin-left: 1rem;
        margin-bottom: 1rem;
        z-index: 1;

        &::before {
            content: '';
            display: block;
            position: absolute;
            left: -1rem;
            top: 1rem;
            right: 1rem;
            bottom: -1rem;
            background: var(--primary);
            z-index: -1;
        }
    }
</style>