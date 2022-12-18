<script lang="ts">
	import { fly } from 'svelte/transition';
	import { sineOut } from 'svelte/easing';
	import { onMount } from 'svelte';

	let isInView: boolean;
	onMount(() => (isInView = true));
</script>

<section id="one">
	<div class="content">
		<h1>A clean car in a couple clicks</h1>
		<h6>The new e-commerce marketplace which connects customers with car cleaners</h6>
		<div class="buttons">
			<a href="https://apps.apple.com/gb/app/novowash/id1601206174" class="ios"
				>Download for iOS<i id="apple" class="fa-brands fa-apple" /></a
			>
			<a
				href="https://play.google.com/store/apps/details?id=com.sigmasolve.novowash"
				class="android">Download for Android<i class="fa-brands fa-android" /></a
			>
		</div>
		{#if isInView}
			<div class="socials" in:fly={{ x: -400, easing: sineOut }}>
				<a href="https://www.facebook.com/groups/753796198578054" target="_blank" rel="noreferrer">
					<i class="fa-brands fa-facebook-f" />
				</a>
				<a href="https://www.instagram.com/novo.wash/" target="_blank" rel="noreferrer">
					<i class="x fa-brands fa-instagram" />
				</a>
				<a href="https://www.linkedin.com/company/novowash1/" target="_blank" rel="noreferrer">
					<i class="x fa-brands fa-linkedin-in" />
				</a>
				<a href="https://www.tiktok.com/@novowash" target="_blank" rel="noreferrer">
					<i class="fa-brands fa-tiktok" />
				</a>
			</div>
		{/if}
	</div>
	{#if isInView}
		<img in:fly={{ x: 400, easing: sineOut }} src="novo-car.png" alt="Novo wash" />
	{/if}
</section>

<style lang="scss">
	$hide-image: 783px;
	#one {
		min-height: 100vh;
		position: relative;
		width: 100vw;
		overflow-x: hidden;
		justify-content: space-between;
		background-color: var(--blue);
		.content {
			position: absolute;
			color: var(--white);
			max-width: var(--breakpoint);
			// width: var(--breakpoint);
			top: 50%;
			left: 8vw;
			transform: translateY(-50%);
			z-index: 2;
			float: left;
			h1 {
				font-size: 5rem;
				margin-bottom: 2rem;
				position: relative;
				-webkit-text-stroke: 1px black;
				&::after {
					content: 'A clean car in a couple clicks';
					position: absolute;
					width: 100%;
					height: 100%;
					top: 0;
					left: 0;
					color: #0f5e9c;
					z-index: 100;
					animation: wave 8s infinite;
				}
			}
			h6 {
				font-size: 1rem;
				line-height: 1.5rem;
				margin-bottom: 3rem;
			}
			.buttons {
				display: flex;
				flex-direction: column;
				align-items: flex-start;
				margin-bottom: 1rem;
				a {
					text-decoration: none;
					background-color: var(--black);
					padding: 1rem 2rem;
					margin-bottom: 0.5rem;
					color: var(--white);
					display: flex;
					align-items: center;
					transition: 0.7s all ease;
					&:hover {
						background-color: #0f5e9c;
					}
					i {
						margin-left: 0.5rem;
						font-size: 1.5rem;
						&#apple {
							transform: translateY(-2px);
						}
					}
				}
			}
		}
		img {
			position: absolute;
			right: 0;
			min-width: 583px;
			z-index: 1;
			// width: calc(80vw - var(--breakpoint));
			height: 100vh;
		}

		h3 {
			color: var(--white);
			margin-bottom: 1rem;
		}
		.socials {
			display: flex;
			width: 100%;
			max-width: 500px;
			gap: 1rem;
			margin-bottom: 1rem;
			i {
				font-size: 1.5rem;
				&.x {
					font-size: 1.7rem;
				}
			}
		}
		a {
			color: var(--white);
			margin-bottom: 1rem;
		}
		@media screen and (max-width: $hide-image) {
			.content {
				max-width: 84vw;
				h1,
				h1::after {
					font-size: 3rem !important;
				}
			}
		}
		@media screen and (max-width: 654px) {
			h6 {
				background-color: rgba(0, 0, 0, 0.3);
				border-radius: 1rem;
				padding: 0.5rem;
			}
			.buttons {
				a {
					background-color: var(--blue) !important;
				}
			}
		}
	}

	@keyframes wave {
		0%,
		100% {
			clip-path: polygon(
				0 77%,
				12% 79%,
				24% 85%,
				34% 90%,
				47% 88%,
				59% 84%,
				77% 76%,
				87% 75%,
				97% 76%,
				100% 78%,
				100% 100%,
				0% 100%
			);
		}
		25% {
			clip-path: polygon(
				0 57%,
				11% 44%,
				22% 35%,
				37% 34%,
				49% 38%,
				60% 42%,
				72% 39%,
				82% 32%,
				90% 29%,
				100% 27%,
				100% 100%,
				0% 100%
			);
		}
		50% {
			clip-path: polygon(
				0 19%,
				12% 28%,
				22% 32%,
				36% 30%,
				49% 22%,
				60% 19%,
				74% 19%,
				85% 22%,
				94% 27%,
				100% 36%,
				100% 100%,
				0% 100%
			);
		}
		75% {
			clip-path: polygon(
				0 57%,
				11% 44%,
				22% 35%,
				37% 34%,
				49% 38%,
				60% 42%,
				72% 39%,
				82% 32%,
				90% 29%,
				100% 27%,
				100% 100%,
				0% 100%
			);
		}
	}
</style>
