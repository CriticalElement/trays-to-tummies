<script lang="ts">
    import closeSrc from '$lib/icons/close.png';
    import menuSrc from '$lib/icons/menu.png';

    let open = false;

    const toggleMenu = () => {
        open = !open;
    }

    const closeMenu = () => {
        open = false;
    }
</script>

<nav class:open>
    <div class="logo-text">
        <a href='/#'>trays to tummies</a>
        <button on:click={toggleMenu}>
            {#if open}
                <img src={closeSrc} alt='close menu' />
            {:else}
                <img src={menuSrc} alt='open menu' />
            {/if}
        </button>
    </div>
    <div class="page-links">
        <p><a href='/#' on:click={closeMenu}>home</a></p>
        <p><a href='/#about' on:click={closeMenu}>about</a></p>
        <p><a href='/#contact' on:click={closeMenu}>contact</a></p>
    </div>
    <div class="outbound-links">
        <p><a href='/chapters' on:click={closeMenu}>chapters</a></p>
        <p><a href='/partners' on:click={closeMenu}>partners</a></p>
        <p><a href='/leaders' on:click={closeMenu}>leaders</a></p>
    </div>
</nav>

<style lang="scss">
    nav {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        align-self: stretch;
        padding: var(--padding-16) var(--page-padding);
        gap: var(--padding-16);
        background: var(--primary);
        z-index: 5;
        overflow: clip;

        a {
            text-decoration: none;
        }

        .logo-text {
            flex: 1 0 0;
            font-size: 2.25rem;
            line-height: 2rem;
            @include cursive;

            button {
                width: 2.5rem;
                height: 2.5rem;
                display: none;
                background: none;
                border: none;
                cursor: pointer;
                place-items: center;
            }
        }

        .page-links {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: var(--padding-16);
            flex: 1 0 0;
        }

        .outbound-links {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            gap: var(--padding-16);
            flex: 1 0 0;
        }

        @media screen and (max-width: 64rem) {
            .page-links {
                justify-content: flex-end;
            }

            .outbound-links {
                flex: 0 0 0;
            }
        }

        @media screen and (max-width: 57rem) {
            flex-direction: column;
            gap: var(--padding-32);
            align-items: center;
            height: 4rem;
            transition: height 0.3s ease-in-out;

            &.open {
                height: 12.125rem; 
            }

            .logo-text {
                width: 100%;
                display: flex;
                justify-content: space-between;
                align-items: center;

                button {
                    display: grid;
                }
            }
        }
        
        @media screen and (max-width: 48rem) {
            &.open {
                height: 11.5rem;
            }
        }
    }
</style>