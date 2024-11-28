<script lang="ts">
	const partners = [
		['Frisco Fastpacs', 'https://example.com'],
		['Frisco Family Services', 'https://example.com'],
		['Karya Siddhi Hanuman Temple']
	];
</script>

<svelte:head>
	<title>trays to tummies - partners</title>
</svelte:head>
<div id="hero">
	<h1>partners</h1>
</div>
<section id="info">
	<div class="section-container">
		<h2>about our partners</h2>
		<p>
			we utilize local partners in close proximity to each of our chapters to handle the food that
			is donated. this way, we can ensure that the food is distributed to kids in an efficient and
			fast manner, and that the food is fresh and safe to eat.
			<br /><br />
			below, we have the names of food banks and other organizations that we have partnered with
            to help feed hungry kids.
		</p>
	</div>
</section>
<section id="content">
	<div class="section-container">
		{#each partners as partner}
			<h2>{partner[0]}</h2>
		{/each}
	</div>
</section>

<style lang="scss">
	#hero {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	#info {
		background: var(--accent);

		.section-container {
			display: flex;
			flex-direction: row;
			align-items: center;
			gap: var(--padding-64);

			p {
				text-align: end;
				max-width: 65ch;
				text-wrap: pretty;
			}

			@media screen and (max-width: 64rem) {
				flex-direction: column;
				align-items: flex-start;

				p {
					text-align: left;
				}
			}
		}
	}

	#content {
		.section-container {
			display: grid;
			grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr));
			justify-items: center;
			gap: var(--padding-64);

			h2 {
				text-align: center;
				width: fit-content;
			}
		}
	}
</style>
