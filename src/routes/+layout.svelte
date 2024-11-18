<script>
	import Footer from '$lib/components/footer.svelte';
	import Navbar from '$lib/components/navbar.svelte';
	import '$lib/styles/global.scss';
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
