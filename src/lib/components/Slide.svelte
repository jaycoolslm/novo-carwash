<script lang="ts">
	import { fade } from 'svelte/transition';
	import { inview } from 'svelte-inview';

	export let title: string;
	export let text: string;

	let isInView: boolean;
</script>

<div
	class="slide"
	use:inview={{ unobserveOnEnter: true, rootMargin: '-20%' }}
	on:change={({ detail }) => {
		isInView = detail.inView;
	}}
>
	{#if isInView}
		<h2 transition:fade={{ delay: 100, duration: 1000 }}>{title}</h2>
		<p transition:fade={{ delay: 100, duration: 1000 }}>
			{text}
		</p>
	{/if}
</div>

<style lang="scss">
	.slide {
		min-width: 100vw;
		padding: 3rem;
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
		h2 {
			font-size: 2rem;
		}
		p {
			margin: 2rem 8vw 0 8vw;
			max-width: 700px;
			line-height: 2rem;
		}
	}
</style>
