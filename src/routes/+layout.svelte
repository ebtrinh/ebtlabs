<script lang="ts">
	import Header from './Header.svelte';
	import '../app.css';
	
	let { children } = $props();
</script>

<div class="app">
	<Header />

	<main class="container">
		{@render children()}
	</main>

	<footer class="site-footer">
		<p>
			© 2024 EBT Labs • Built with SvelteKit
		</p>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
	}

	.site-footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 16px 0;
		color: var(--color-text-muted);
	}

	/* removed unused nested selector warning */
</style>
