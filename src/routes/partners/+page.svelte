<script lang="ts">
    const partners = [
        ['Frisco Fastpacs', 'https://example.com'],
        ['Frisco Family Services', 'https://example.com'],
        ['Karya Siddhi Hanuman Temple']
    ];
</script>

<div id="hero">
    <h1>partners</h1>
</div>
<section id="info">
    <div class="section-container">
        <h2>about our partners</h2>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sequi, debitis quisquam adipisci minus, explicabo provident nihil repudiandae quae praesentium necessitatibus excepturi error suscipit esse corrupti! Voluptate velit explicabo autem officia?</p>
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
                text-wrap: balance;
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