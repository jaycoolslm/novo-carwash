<script lang="ts">
	import Hero from '$lib/sections/Hero.svelte';
	import Statement from '$lib/sections/Statement.svelte';
	import How from '$lib/sections/How.svelte';
	import Reviews from '$lib/sections/Reviews.svelte';
	import Footer from '$lib/sections/Footer.svelte';
</script>

<svelte:head />

<Hero />

<Statement />

<How />

<Reviews />

<Footer />

<style lang="scss">
	:root {
		--blue: #3e96bf;
		--white: white;
		--black: black;
		--breakpoint: 660px;
	}

	:global(*) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		font-family: 'Poppins', sans-serif;
	}

	:global(section) {
		display: flex;
		align-items: center;
		padding: 5vh 0;
	}

	:global(button) {
		cursor: pointer;
	}
</style>
