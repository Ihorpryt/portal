<script>
    import FlightStats from '../components/blocks/FlightStats.svelte';
    import Expenses from '../components/blocks/Expenses.svelte';

</script>

<svelte:head>
	<title>Portside App / Dashboard</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<FlightStats />
	<div class="duo">
		<Expenses 
			title="Expenses"
		/>
		<Expenses 
			title="Expenses by Category"
		/>
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
		flex: 0.6;
		padding: 25px 75px;
		gap:25px;
	}
	.duo {
		display: flex;
		flex-direction: row;
		width: 100%;
		gap:25px;
	}

</style>
