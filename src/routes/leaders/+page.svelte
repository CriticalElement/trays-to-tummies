<script lang="ts">
	import Media from "$lib/components/media.svelte";

	const leaders = [
		['Harish Balamurugan', 'Executive Director / CEO', 'harish.jpg'],
		['Anirudh', 'Executive Director / COO', ''],
		['Vedh Amara', 'CFO', 'vedh.jpg'],
		['Suhas Kondu', 'CMO', 'suhas.jpg'],
		['Mithun Kutuva', 'CGO', ''],
		['Pranav Pakanati', 'CTO', 'pranav.jpeg'],
		['Srikar Koppana', 'Secretary', ''],
	];
</script>

<svelte:head>
	<title>trays to tummies - leaders</title>
</svelte:head>
<div id="hero">
	<h1>leaders</h1>
</div>
<section id="content">
    <div class="section-container">
        {#each leaders as leader}
            <div class="leader">
                <div class="info">
                    <h3 class="name">{leader[0]}</h3>
                    <h3>{leader[1]}</h3>
                </div>
                <Media>
                    {#if leader[2] === ''}
                        <div class='placeholder'></div>
                    {:else}
                        <img src='/leaders/{leader[2]}' alt='{leader[0]}' />
                    {/if}
                </Media>
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
        gap: var(--padding-64);

        .leader {
            display: flex;
            flex-direction: row;
            align-items: center;
            gap: var(--padding-64);
            flex-wrap: wrap;

            .info {
                min-width: fit-content;
                margin-right: auto;
            }
            
            img, .placeholder {
                width: 20rem;
                max-width: 85vw;
            }
            
            .placeholder {
                aspect-ratio: 1;
                background: white;
            }
            @media screen and (min-width: 64rem) {
                &:nth-child(odd) {
                    flex-direction: row-reverse;
                    text-align: end;
    
                    .info {
                        margin-right: 0;
                        margin-left: auto;
                    }
                }
            }

            @media screen and (max-width: 56rem) {
                flex-direction: column;
                align-items: flex-start;
            }
        }
    }
</style>