<script lang="ts">
	import Siema from 'siema';
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
		<div class="slide">
			<h3>Our mission</h3>
			<p>
				Providing car cleaners an efficient working schedule giving them a standard 9am-5pm working
				day where car cleaners should be reaping more rewards.by achieving business efficiency and
				structure
			</p>
		</div>
		<div class="slide">
			<h3>Our purpose</h3>
			<p>
				Striving to help support car cleaners during times of economic uncertainty and instability.
				The App aims to help car cleaners grow and reach out even more through franchising and
				reaching more customers and utilising a booking system to improve efficiency measures
			</p>
		</div>
		<div class="slide">
			<h3>Our platform</h3>
			<p>
				Providing customers’ convenience from not waiting in car washing sites queues’ anymore nor
				having to withdraw cash. Additionally, providing variety from offering a wide range of
				different cleaning services as well as having the option to choose between a mobile and
				fixed car washing site.
			</p>
		</div>
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
			width: 100%;
			position: absolute;
			left: 50%;
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
		.slide {
			min-width: 100vw;
			padding: 3rem;
			display: flex;
			flex-direction: column;
			align-items: center;
			text-align: center;
			h3 {
				font-size: 2rem;
			}
			p {
				margin: 2rem 8vw 0 8vw;
				max-width: 700px;
				line-height: 2rem;
			}
		}
	}
</style>
