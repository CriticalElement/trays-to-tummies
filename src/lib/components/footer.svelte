<footer>
	<p class="logo"><span>trays to tummies</span> © 2024</p>
	<p class="info">
		designed, developed and deployed by <a href="https://pranav-pakanati.netlify.app"
			>pranav pakanati</a
		>
	</p>
</footer>

<style lang="scss">
	footer {
		background: var(--primary);
		display: flex;
		padding: 2rem var(--page-padding);
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 2rem;
		align-self: stretch;
		text-align: center;

		.logo {
			line-height: 2.25rem;

			span {
				font-size: 2.25rem;
				@include cursive;
			}
		}

        .info {
            font-size: 1rem;
        }
	}
</style>
