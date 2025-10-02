<script lang="ts">
	import Header from '../components/Header.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<div class="app">
	<!-- <Header /> -->

	<main>
		{@render children()}
	</main>

	<footer>
		<p>
			Designed and built by Mel Marochov using <a href="https://svelte.dev/docs/kit">SvelteKit</a>
		</p>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		align-items: center;
		justify-content: space-between;
	}

	main {
		/* flex: 1; */
		display: flex;
		flex-direction: column;
		padding: 3rem 0 0 0;
		width: 100%;
		margin: 0;
		box-sizing: border-box;
	}

	footer {
		color: var(--color-bg-0);
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
		text-align: center;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}

	@media only screen and (max-width: 950px) {
        main {
            padding: 0;
        }
    }
</style>
