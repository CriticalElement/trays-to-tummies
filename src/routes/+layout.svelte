<script>
	import { afterNavigate, beforeNavigate } from '$app/navigation';
	import Footer from '$lib/components/footer.svelte';
	import Navbar from '$lib/components/navbar.svelte';
	import '$lib/styles/global.scss';
	import { onMount } from 'svelte';

    onMount(() => {
        document.querySelector('html')?.classList.add('smooth-scroll');
    });

    beforeNavigate(() => {
        document.querySelector('html')?.classList.remove('smooth-scroll');
    });

    afterNavigate(() => {
        document.querySelector('html')?.classList.add('smooth-scroll');
    });
</script>

<Navbar />
<main>
	<slot />
</main>
<Footer />

<style lang="scss">
    main {
        display: flex;
        flex-direction: column;
        align-items: stretch;
        justify-content: center;
        flex: 1 0 0;
    }
</style>
