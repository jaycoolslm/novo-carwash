<section id="one">
	<div class="content">
		<h1>A clean car in a few taps</h1>
		<h6>The new e-commerce marketplace which connects customers with car cleaners</h6>
		<div class="buttons">
			<a href="/login" class="ios">Download for iOS<i id="apple" class="fa-brands fa-apple" /></a>
			<a href="/register" class="android">Download for Android<i class="fa-brands fa-android" /></a>
		</div>
	</div>
	<img src="novo-car.png" alt="Novo wash" />
</section>

<style lang="scss">
	$hide-image: 783px;
	#one {
		min-height: 100vh;
		position: relative;
		width: 100vw;
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
				a {
					text-decoration: none;
					background-color: var(--black);
					padding: 1rem 2rem;
					margin-bottom: 0.5rem;
					color: var(--white);
					display: flex;
					// justify-content: space-between;
					// width: 252px;
					align-items: center;
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
		@media screen and (max-width: $hide-image) {
			.content {
				max-width: 84vw;
				h1 {
					font-size: 3rem !important;
				}
			}

			img {
				// display: none;
			}
		}
	}
</style>
