<nav>
    <div class="logo-text"><a href='/#'>trays to tummies</a></div>
    <div class="page-links">
        <p><a href='/#'>home</a></p>
        <p><a href='/#about'>about</a></p>
        <p><a href='/#contact'>contact</a></p>
    </div>
    <div class="outbound-links">
        <p><a href='/chapters'>chapters</a></p>
        <p><a href='/partners'>partners</a></p>
        <p><a href='/leaders'>leaders</a></p>
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

        a {
            text-decoration: none;
        }

        .logo-text {
            flex: 1 0 0;
            font-size: 2.25rem;
            line-height: 2rem;
            @include cursive;
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
    }
</style>