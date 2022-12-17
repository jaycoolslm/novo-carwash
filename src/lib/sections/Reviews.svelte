<script lang="ts">
	import Stars from '$lib/components/Stars.svelte';
</script>

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
	#four {
		background-color: var(--white);
		color: var(--black);
		flex-direction: column;
		justify-content: center;
		min-height: 70vh;
		// padding: 5vh 5vw;
		h2 {
			font-size: 3rem;
			margin-bottom: 2rem;
		}

		.card-container {
			display: flex;
			justify-content: space-evenly;
			flex-wrap: wrap;
			width: 100%;
			gap: 2rem;
			.card {
				padding: 2rem 1rem;
				background-color: var(--blue);
				color: var(--white);
				width: 25vw;
				min-width: 350px;
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
</style>
