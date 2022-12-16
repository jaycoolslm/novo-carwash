<script lang="ts">
	import Stars from '$lib/components/Stars.svelte';
</script>

<svelte:head>
	<script src="https://kit.fontawesome.com/d2e5e5458f.js" crossorigin="anonymous"></script>
</svelte:head>

<section id="one">
	<div class="content">
		<h1>A clean car in a few taps</h1>
		<h6>The new e-commerce marketplace which connects customers with car cleaners</h6>
		<div class="buttons">
			<a href="/login" class="ios">Download for iOS<i id="apple" class="fa-brands fa-apple" /></a>
			<a href="/register" class="android">Download for Android<i class="fa-brands fa-android" /></a>
		</div>
	</div>
	<img
		src="https://www.pngall.com/wp-content/uploads/2016/07/Car-Free-Download-PNG.png"
		alt="Novo wash"
	/>
</section>

<section id="two">
	<div class="statement-container">
		<div class="layer1">
			<h3>Purpose</h3>
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
				voluptate. Quisquam, voluptate. Quisquam, voluptate.
			</p>
		</div>
		<div class="layer2">
			<h3>Platform</h3>
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
				voluptate. Quisquam, voluptate. Quisquam, voluptate.
			</p>
		</div>
	</div>
	<h2>Our Purpose & Platform</h2>
</section>

<section id="three">
	<h2>How it works</h2>
	<div class="card-container">
		<div class="card">
			<i class="fa-solid fa-car" />
			<h3>Car owners</h3>
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
				voluptate. Quisquam, voluptate. Quisquam, voluptate.
			</p>
		</div>
		<div class="card">
			<i class="fa-solid fa-business-time" />
			<h3>Business owners</h3>
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
				voluptate. Quisquam, voluptate. Quisquam, voluptate.
			</p>
		</div>
	</div>
</section>

<section id="four">
	<h2>Don't just hear it from us!</h2>
	<div class="card-container">
		<div class="card">
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
				voluptate. Quisquam, voluptate. Quisquam, voluptate.
			</p>
			<h3>Meghan</h3>
			<h4>Car owner</h4>
			<Stars stars={5} />
		</div>
		<div class="card">
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
				voluptate. Quisquam, voluptate. Quisquam, voluptate.
			</p>
			<h3>George</h3>
			<h4>Car owner</h4>
			<Stars stars={5} />
		</div>
		<div class="card">
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptate. Quisquam,
				voluptate. Quisquam, voluptate. Quisquam, voluptate.
			</p>
			<h3>Lucas</h3>
			<h4>Business owner</h4>
			<Stars stars={5} />
		</div>
	</div>
</section>

<style lang="scss">
	:root {
		--blue: #89cff0;
		--white: white;
		--black: black;
		--breakpoint: 583px;
	}

	:global(*) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		font-family: sans-serif;
	}
	section {
		display: flex;
		justify-content: space-evenly;
		align-items: center;
		height: 100vh;
		padding: 5vh 5vw;
		&#one {
			flex-wrap: wrap;

			background-color: var(--blue);
			.content {
				color: var(--white);
				max-width: var(--breakpoint);
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
				object-fit: contain;
				width: 90vw;
				// max-width: calc(90vw - var(--breakpoint));
				height: auto;
			}

			@media screen and (min-width: 583px) {
				img {
					min-width: 583px;
					width: calc(80vw - var(--breakpoint));
				}
			}
		}

		&#two {
			background-color: var(--white);
			color: var(--black);
			justify-content: space-evenly;
			flex-wrap: wrap-reverse;
			h2 {
				font-size: 4rem;
				width: 420px;
			}

			.statement-container {
				position: relative;
				width: 40vw;
				div {
					padding: 2rem;
					&.layer1 {
						background-color: green;
						position: absolute;
						top: -2rem;
						left: -2rem;
					}
					&.layer2 {
						background-color: red;
						position: absolute;
						top: 2rem;
						left: 2rem;
					}
				}
			}
		}

		&#three {
			background-color: var(--white);
			color: var(--black);
			flex-direction: column;
			h2 {
				font-size: 3rem;
				margin-bottom: 2rem;
			}

			.card-container {
				display: flex;
				justify-content: space-evenly;
				flex-wrap: wrap;
				width: 100%;
				.card {
					padding: 2rem;
					background-color: var(--blue);
					color: var(--white);
					width: 40vw;
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

		&#four {
			background-color: var(--blue);
			color: var(--white);
			flex-direction: column;
			h2 {
				font-size: 3rem;
				margin-bottom: 2rem;
			}

			.card-container {
				display: flex;
				justify-content: space-evenly;
				flex-wrap: wrap;
				width: 100%;
				.card {
					padding: 2rem 1rem;
					background-color: var(--white);
					color: var(--black);
					width: 25vw;
					text-align: center;
					h3 {
						margin-bottom: 1rem;
					}
					p {
						line-height: 1.5rem;
						margin-bottom: 2rem;
					}
					h4 {
						margin-bottom: 0.5rem;
					}
				}
			}
		}
	}
</style>
