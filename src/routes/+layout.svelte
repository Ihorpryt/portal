<script>
    import Sidebar from './Sidebar.svelte';
	import './styles.css';
    import Topbar from './Topbar.svelte';
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@200;300;400;500;600;700;800&display=swap" rel="stylesheet">
</svelte:head>

<div class="app">
	<Sidebar />

	<main>
		<Topbar />
		<slot />
	</main>

	<!-- <footer>
		<p>visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to learn SvelteKit</p>
	</footer> -->
</div>

<style>
	.app {
		/* display: flex;
		flex-direction: column;
		min-height: 100vh; */

		display: flex;
		flex-direction: row;
		width: 100%;
		height: 100%;
		min-height: 100%;
		overflow: hidden;
		-webkit-box-align: stretch;
		align-items: stretch;
	}

	main {
		/* flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box; */

		display: flex;
		flex-direction: column;
		width: 100%;
		height: 100vh;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
