<section>
	<h3>Be the first to hear about NovoWash news</h3>
	<form action="">
		<input type="text" name="" id="" />

		<button type="submit">Subscribe</button>
	</form>
</section>

<style lang="scss">
	section {
		background-color: var(--blue);
		flex-direction: column;
		align-items: center;
		justify-content: space-evenly;
		min-height: 20vh;
		form {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: space-evenly;
			gap: 1rem;

			button {
				background-color: white;
				border: 0;
				color: black;
				padding: 0.5rem 1.5rem;
				border-radius: 2rem;
				transition: all 0.7s ease;
				&:hover {
					background-color: black;
					color: white;
					transform: scale(1.1);
					font-weight: 600;
				}
			}
		}
	}
</style>
