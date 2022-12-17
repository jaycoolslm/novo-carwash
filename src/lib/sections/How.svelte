<section>
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

<style lang="scss">
	section {
		background-color: var(--blue);
		color: var(--white);
		flex-direction: column;
		min-height: 50vh;
		h2 {
			font-size: 3rem;
			margin-bottom: 2rem;
		}

		.card-container {
			display: flex;
			justify-content: space-evenly;
			flex-wrap: wrap;
			gap: 2rem;
			width: 100%;
			.card {
				padding: 2rem;
				background-color: var(--white);
				color: var(--black);
				width: 40vw;
				min-width: 350px;
				max-width: 600px;
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
</style>
