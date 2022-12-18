<script lang="ts">
	import { fade, fly } from 'svelte/transition';
	import { inview } from 'svelte-inview';

	let isInView: boolean;
</script>

<section>
	<span
		use:inview={{ unobserveOnEnter: true, rootMargin: '-20%' }}
		on:change={({ detail }) => {
			isInView = detail.inView;
		}}
	>
		{#if isInView}
			<h2 in:fade>How it works</h2>
		{/if}
	</span>
	<div
		class="card-container"
		use:inview={{ unobserveOnEnter: true, rootMargin: '-20%' }}
		on:change={({ detail }) => {
			isInView = detail.inView;
		}}
	>
		{#if isInView}
			<div class="card" in:fly={{ y: 500, duration: 1000 }}>
				<i class="fa-solid fa-car" />
				<h3>Car owners</h3>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
					voluptate. Quisquam, voluptate. Quisquam, voluptate.
				</p>
			</div>
			<div class="card" in:fly={{ y: 300, duration: 1000, delay: 500 }}>
				<i class="fa-solid fa-business-time" />
				<h3>Business owners</h3>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
					voluptate. Quisquam, voluptate. Quisquam, voluptate.
				</p>
			</div>
		{/if}
	</div>
</section>

<style lang="scss">
	section {
		background-color: var(--blue);
		color: var(--white);
		flex-direction: column;
		min-height: 50vh;
		h2 {
			font-size: 2rem;
			margin-bottom: 2rem;
		}
		.card-container {
			display: flex;
			justify-content: space-evenly;
			flex-wrap: wrap;
			gap: 2rem;
			width: 100%;
			.card {
				padding: 2rem;
				background-color: var(--white);
				color: var(--black);
				width: 40vw;
				min-width: 350px;
				max-width: 600px;
				text-align: center;
				i {
					margin-bottom: 1rem;
					font-size: 3rem;
				}
				h3 {
					margin-bottom: 3rem;
				}
				p {
					line-height: 1.5rem;
				}
			}
		}
	}
</style>
