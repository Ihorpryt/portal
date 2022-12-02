<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
</script>

<svelte:head>
	<title>Portside App / Dashboard</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<div class="flight-stats">
		<h2>Flight Statistics</h2>
		<div class="block">
			<div class="left-cell-group">
				<div class="cell-row">
					<div class="cell">Flights</div>
					<div class="cell">Flight Hours</div>
				</div>
				<div class="cell-row">
					<div class="cell">Gross Revenue</div>
					<div class="cell">Miles Flown</div>
				</div>
			</div>
			<div class="right-map"></div>
		</div>
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
		flex: 0.6;
		padding: 25px;
	}

	.flight-stats {
		width: 100%;
	}
	.block {
		display: flex;
		flex-direction: row;
	}
	.left-cell-group {
		/* background-color: aquamarine; */
		width: 100%;
	}
	.cell-row {
		display: flex;
		flex-direction: row;
	}
	.cell {
		width: 100%;
		border-top: 1px solid rgb(241,245,249);
		border-right: 1px solid rgb(241,245,249);
		border-left: 1px solid rgba(241,245,249, 0); 
		height: 200px;
	}
	.right-map {
		background-color: aqua;
		width: 100%;
	}

	h2 {
		font-size: 25px;
		font-weight: 700;
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
