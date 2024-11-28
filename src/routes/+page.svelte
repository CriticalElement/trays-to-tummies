<script lang="ts">
	import Media from '$lib/components/media.svelte';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import { goto } from '$app/navigation';

	onMount(() => {
		if ($page.url.pathname !== '/') {
			goto($page.url.pathname, { replaceState: true });
		}

		const intersectionObserver = new IntersectionObserver((entries) => {
			entries.forEach((entry) => {
				if (entry.isIntersecting) {
					setTimeout(() => {
						animateNumber({
							suffix: ' chapters',
							end: 36,
							digits: 2,
							element: document.querySelector('#chapters')!
						});
						animateNumber({
							suffix: '+ items',
							end: 8000,
							digits: 4,
							element: document.querySelector('#items')!
						});
						animateNumber({
							suffix: ' partnerships',
							end: 10,
							digits: 1,
							element: document.querySelector('#partnerships')!
						});
						animateNumber({
							suffix: '+ impacted',
							end: 75000,
							digits: 5,
							element: document.querySelector('#impact')!
						});
					}, 200);
					intersectionObserver.disconnect();
				}
			});
		});

		const animateNumber = ({
			suffix,
			end,
			digits,
			element
		}: {
			suffix: string;
			end: number;
			digits: number;
			element: HTMLElement;
		}) => {
			let current = 0;
			let startTime: number | null = null;
			const duration = 2000;
			const step = (timestamp: number) => {
				if (!startTime) {
					startTime = timestamp;
				}
				const timeElapsed = timestamp - startTime;
				const progress = Math.min(timeElapsed / duration, 1);
				current = Math.floor((1 - Math.pow(1 - progress, 4)) * end);
				element.textContent = `${current.toLocaleString(undefined, { minimumSignificantDigits: digits })}${suffix}`;
				requestAnimationFrame(step);
			};
			requestAnimationFrame(step);
		};

		intersectionObserver.observe(document.querySelector('#chapters')!);
	});
</script>

<svelte:head>
	<title>trays to tummies</title>
</svelte:head>
<section id="hero">
	<h1>trays to tummies</h1>
	<div class="info">
		<p>
			trays-to-tummies is an initiative that seeks to reduce wastage and hunger by repurposing
			otherwise wasted food to provide supplements to students that may benefit from it.
			trays-to-tummies also collects school supplies to support students’ learning.
		</p>
		<iframe
			src="https://www.youtube.com/embed/Djxcy8ApOF0?si=qt1O2Kjn_3sq9w4H"
			title="YouTube video player"
			frameborder="0"
			allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
			referrerpolicy="strict-origin-when-cross-origin"
			allowfullscreen
		></iframe>
	</div>
</section>
<section id="stats">
	<h2>benefiting our community</h2>
	<div class="stats">
		<div class="info">
			<h3 id="chapters">36 chapters</h3>
			<p>across local schools</p>
		</div>
		<div class="divider"></div>
		<div class="info">
			<h3 id="items">8,000+ items</h3>
			<p>donated to students</p>
		</div>
		<div class="divider"></div>
		<div class="info">
			<h3 id="partnerships">10 partnerships</h3>
			<p>among food banks</p>
		</div>
		<div class="divider"></div>
		<div class="info">
			<h3 id="impact">75,000+ impacted</h3>
			<p>to date</p>
		</div>
	</div>
</section>
<section id="about">
	<div class="section-container">
		<div class="container">
			<h2>about us!</h2>
			<p>
				in each of our chapters, we use donation boxes to collect unused food from the cafeteria.
				with the collected food, we distribute it to our local partners where they can go to hungry
				kids.
			</p>
			<Media>
				<img src="/food-donation.jpg" alt="A donation box in a school." />
			</Media>
		</div>
		<div class="container">
			<Media>
				<img src="/donation-box.jpg" alt="A man carrying boxes of food to be delivered." />
			</Media>
			<p>
				across our chapters, we have been able to donate over 8,000 items to students in need, and
				spread our message to over 75,000 students. we will continue to grow to more chapters and
				partner with more food banks to help more and more students in need.
				<br /><br />
				do you want to help feed hungry kids? to start a chapter, please contact us below, and give
				us information about yourself and the school you go to—we will get back to you ASAP!
			</p>
		</div>
	</div>
</section>
<section id="contact">
	<div class="section-container">
		<h2>contact us!</h2>
		<div class="container">
			<div class="info">
				<h3><a href="mailto:trays2tummies@gmail.com">trays2tummies@gmail.com</a></h3>
				<p>email us!</p>
			</div>
			<div class="divider"></div>
			<div class="info">
				<h3><a href="https://www.instagram.com/trays_to_tummies/">@trays_to_tummies</a></h3>
				<p>follow our instagram!</p>
			</div>
		</div>
	</div>
</section>

<style lang="scss">
	#hero {
		h1 {
			text-align: center;
			width: 100%;
		}

		.info {
			display: flex;
			justify-content: center;
			align-items: center;
			gap: 4rem;
			align-self: stretch;

			p {
				max-width: 30rem;
			}

			@media screen and (max-width: 64rem) {
				flex-direction: column;
				align-items: center;
			}

			iframe {
				width: 560px;
				height: 315px;
				@media screen and (max-width: 64rem) {
					width: 100%;
					height: 315px;
				}
			}
		}

		@media screen and (max-width: 48rem) {
			gap: var(--padding-64);
		}
	}

	#stats {
		background: var(--accent);
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: var(--padding-64);
		text-align: center;

		.stats {
			display: flex;
			justify-content: center;
			align-items: center;
			gap: var(--padding-48);
			align-self: stretch;

			.info {
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
				gap: var(--padding-16);
			}

			@media screen and (max-width: 86rem) {
				flex-wrap: wrap;

				.divider {
					display: none;
				}
			}
		}
	}

	#about {
		.section-container {
			display: flex;
			gap: var(--padding-64);

			.container {
				display: flex;
				flex-direction: column;
				gap: var(--padding-32);
			}

			@media screen and (max-width: 48rem) {
				flex-direction: column;
				align-items: center;
			}
		}
	}

	#contact {
		background-color: var(--accent);

		.section-container {
			display: flex;
			flex-direction: column;
			align-items: flex-start;
			gap: 4rem;
			align-self: stretch;
			text-align: center;

			h2 {
				width: 100%;
			}

			.container {
				display: flex;
				justify-content: center;
				align-items: center;
				gap: 3rem;
				align-self: stretch;

				.info {
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					gap: 1rem;
					flex: 1 0 0;
				}

				@media screen and (max-width: 64rem) {
					flex-direction: column;
					align-items: center;

					.divider {
						display: none;
					}
				}
			}
		}
	}

	.divider {
		width: 0.125rem;
		height: 5rem;
		background: var(--secondary);
	}
</style>
