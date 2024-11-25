<script>
	import Media from "$lib/components/media.svelte";

    const chapters = [
        ['', 'Heritage HS', 'Frisco, TX (founding chapter)'],
        ['', 'Lone Star HS', 'Frisco, TX'],
        ['', 'Wisconsin Dells HS', 'Wisconsin Dells, WI'],
        ['', 'Centennial HS', 'Frisco, TX'],
        ['', 'Rockwall-Heath HS', 'Heath, TX'],
        ['', 'Independence HS', 'Frisco, TX'],
        ['', 'Memorial HS', 'Frisco, TX'],
        ['', 'Millburn HS', 'Millburn, NJ'],
        ['', 'Wakeland HS', 'Frisco, TX'],
        ['', 'Argyle HS', 'Argyle, TX'],
        ['', 'Lincoln Way East HS', 'Frankfort, IL'],
        ['', 'Piper HS', 'Kansas City, KS'],
        ['', 'Mills HS', 'Millbrae, CA'],
        ['', 'School of the Future HS', 'New York, NY'],
        ['', 'Frisco HS', 'Frisco, TX'],
        ['', 'Lebanon HS', 'Frisco, TX'],
        ['', 'Cedar Park HS', 'Cedar Park, TX'],
        ['', 'Emerson HS', 'Frisco, TX'],
        ['', 'Ardrey Kell HS', 'Charlotte, NC'],
        ['', 'Stanton HS', 'Stanton, TX'],
        ['', 'Buffalo HS', 'Buffalo, MN'],
        ['', 'Allen HS', 'Allen, TX'],
        ['', 'Reedy HS', 'Frisco, TX'],
        ['', 'Germantown HS', 'Germantown, WI'],
        ['', 'Plano West HS', 'Plano, TX'],
        ['', 'Prosper HS', 'Prosper, TX'],
        ['', 'Walnut Grove HS', 'Prosper, TX'],
        ['', 'Hebron HS', 'Carrollton, TX'],
        ['', 'Bordentown Regional HS', 'Bordentown, NJ'],
        ['', 'Melissa HS', 'Melissa, TX'],
        ['', 'Liberty HS', 'Liberty, NC'],
        ['', 'John Champe HS', 'Aldie, VA'],
        ['', 'Westwood HS', 'Austin, TX'],
        ['', 'Suncoast HS', 'Riviera Beach, FL'],
        ['', 'Jacobs HS', 'Algonquin, IL'],
        ['', 'Eastview HS', 'Apple Valley, MN'],
    ]
</script>

<div id="hero">
	<h1>chapters</h1>
</div>
<section id="content">
	<div class="section-container">
		{#each chapters as chapter}
            <div class="chapter">
                {#if chapter[0] === ''}
                    <Media>
                        <div class='placeholder'></div>
                    </Media>
                {:else}
                    <Media>
                        <img src='/{chapters[0]}' alt='chapter[1]' />
                    </Media>
                {/if}
                <h3>{chapter[1]}</h3>
                <p>{chapter[2]}</p>
            </div>
        {/each}
	</div>
</section>

<style lang="scss">
	#hero {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.section-container {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(24rem, 1fr));
        justify-items: center;
        gap: 4rem;

		.chapter {
			display: flex;
			flex-direction: column;
			align-items: flex-start;
			gap: 1.5rem;
            max-width: 21.25rem;
            margin: 0 auto;

            .placeholder {
                width: 20rem;
                max-width: 70vw;
                height: 13rem;
                background: white;
            }
		}
	}
</style>
