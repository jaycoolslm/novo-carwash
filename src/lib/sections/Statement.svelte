<script lang="ts">
	import Siema from 'siema';
	import Slide from '$lib/components/Slide.svelte';
	import { onMount } from 'svelte';

	let isInView: boolean = false;

	let slider: any, prev: any, next: any, radioSlider;
	let select = 0;
	onMount(() => {
		slider = new Siema({
			selector: '.siema',
			duration: 200,
			easing: 'ease-in-out',
			perPage: 1,
			startIndex: 0,
			draggable: true,
			multipleDrag: true,
			threshold: 20,
			loop: true,
			rtl: false,
			onInit: () => {},
			onChange: () => {}
		}); //end Siema constructor

		prev = () => {
			slider.prev();
			if (select > 0) {
				select--;
			} else {
				select = 2;
			}
		};

		next = () => {
			slider.next();
			if (select < 2) {
				select++;
			} else {
				select = 0;
			}
		};
	}); //end onMount
</script>

<section>
	<button id="left" on:click={prev}>
		<i class="fa-solid fa-arrow-left" />
	</button>
	<button id="right" on:click={next}>
		<i class="fa-solid fa-arrow-right" />
	</button>
	<div class="bullet">
		{#each { length: 3 } as _, i}
			<input
				bind:this={radioSlider}
				type="radio"
				id={i.toString()}
				name="slider-radio"
				value={i}
				checked={select == i}
				on:click={() => {
					slider.goTo(i);
				}}
			/>
		{/each}
	</div>
	<div class="siema">
		<Slide
			title="Our mission"
			text="Maintain a two-sided marketplace which provides car cleaners with an active working schedule & allows customers to find reliable businesses easily."
		/>

		<Slide
			title="Our purpose"
			text="Provide customers a high quality platform with variety & friendly customer service. Connect car cleaners to more customers by utilising efficient booking systems & franchising methods."
		/>
		<Slide
			title="Our platform"
			text="Provides customers convenience through minimising waiting periods & cashless transactions. We settle any problems that may occur with the NovoWash operators so can guarantee satisfaction."
		/>
	</div>
</section>

<style lang="scss">
	section {
		background-color: var(--white);
		color: var(--black);
		// justify-content: space-evenly;
		min-height: 50vh;
		width: 100vw;
		overflow-x: hidden;
		position: relative;
		button {
			background-color: transparent;
			border: 0;
			font-size: 3rem;
			position: absolute;
			top: 45%;
			transform: translateY(-50%);
			z-index: 5;

			&#left {
				left: 8vw;
				transform: translateX(-50%);
			}
			&#right {
				right: 8vw;
				transform: translateX(50%);
			}
		}
		.bullet {
			position: absolute;
			left: 50%;
			transform: translateX(-50%);
			bottom: 4rem;
		}
		input {
			-webkit-appearance: none;
			-moz-appearance: none;
			appearance: none;

			border-radius: 50%;
			width: 8px;
			height: 8px;

			background-color: lightgrey;
			transition: 0.2s all linear;
			margin-right: 5px;

			position: relative;
			top: 4px;
		}
		input:checked {
			background-color: grey;
		}
	}

	@media screen and (max-width: 783px) {
		i {
			font-size: 1.5rem;
		}
	}
</style>
