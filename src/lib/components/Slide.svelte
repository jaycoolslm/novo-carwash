<script lang="ts">
	import { fade } from 'svelte/transition';

	export let title: string;
	export let text: string;
</script>

<div class="slide">
	<h2>{title}</h2>
	<p>
		{text}
	</p>
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
			margin: 2rem 4vw;
			max-width: 700px;
			line-height: 2rem;
		}
	}
</style>
