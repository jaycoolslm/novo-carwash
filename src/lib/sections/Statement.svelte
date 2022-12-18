<script lang="ts">
	import Siema from 'siema';
	import Slide from '$lib/components/Slide.svelte';
	import { onMount } from 'svelte';

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
			text="Providing car cleaners an active working schedule, by aiming to fill a standard 9am-5pm working day, or however long a car cleaner strives to operate. Helping car cleaning businesses achieve greater efficiency, structure & sales. Additionally, making life easy for customers to find the correct & reliable car cleaning business for them based on their need."
		/>
		<Slide
			title="Our purpose"
			text="Striving to help support car cleaning businesses during times of economic uncertainty & instability. The App aims to help car cleaners build resilience, grow & reach more customers through franchising & utilising a booking system to improve efficiency measures. Additionally, providing customers a convenient platform based on preferences, that offers variety, strong quality, & friendly customer service."
		/>
		<Slide
			title="Our platform"
			text="Providing a platform for car cleaners to connect with customers, by offering a booking system, a franchise system, & a platform to advertise their business. Additionally, providing customers a platform to find the right car cleaning business for them, based on their preferences, & needs."
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
