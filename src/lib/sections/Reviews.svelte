<script lang="ts">
	import Stars from '$lib/components/Stars.svelte';
	import { fade } from 'svelte/transition';
	import { inview } from 'svelte-inview';

	let isInView: boolean;
</script>

<section
	id="four"
	use:inview={{ unobserveOnEnter: true, rootMargin: '-20%' }}
	on:change={({ detail }) => {
		isInView = detail.inView;
	}}
>
	{#if isInView}
		<h2 in:fade>Don't just hear it from us!</h2>
		<div class="card-container">
			<div in:fade={{ delay: 400, duration: 1000 }} class="card">
				<p>
					It was such an easy experience to book & pay for a car cleaner without having to go to an
					ATM machine. The business I chose showed up on time, was extremely friendly & delivered a
					great quality service!
				</p>
				<h3>Caroline</h3>
				<h4>Car owner</h4>
				<Stars stars={5} />
			</div>
			<div in:fade={{ delay: 400, duration: 1000 }} class="card">
				<p>
					Easy to use. I have recommended to friends & family & I will definitely be using again to
					book through NovoWash.
				</p>
				<h3>George</h3>
				<h4>Car owner</h4>
				<Stars stars={5} />
			</div>
			<div in:fade={{ delay: 400, duration: 1000 }} class="card">
				<p>
					Reassuring knowing that if any problems occur, NovoWash can help assist. Good
					customer service.
				</p>
				<h3>Lisa</h3>
				<h4>Car owner</h4>
				<Stars stars={5} />
			</div>
		</div>
	{/if}
</section>

<style lang="scss">
	#four {
		background-color: var(--white);
		color: var(--black);
		flex-direction: column;
		justify-content: center;
		min-height: 70vh;
		// padding: 5vh 5vw;
		h2 {
			font-size: 2rem;
			text-align: center;
			margin-bottom: 2rem;
		}

		.card-container {
			display: flex;
			justify-content: space-evenly;
			flex-wrap: wrap;
			width: 100%;
			gap: 2rem;
			.card {
				padding: 2rem 1rem;
				background-color: var(--blue);
				color: var(--white);
				width: 25vw;
				min-width: 350px;
				text-align: center;
				h3 {
					margin-bottom: 1rem;
				}
				p {
					line-height: 2rem;
					margin-bottom: 2rem;
				}
				h4 {
					margin-bottom: 0.5rem;
				}
			}
		}
	}
</style>
