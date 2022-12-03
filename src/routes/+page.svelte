<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
    import FlightStats from '../components/blocks/FlightStats.svelte';
</script>

<svelte:head>
	<title>Portside App / Dashboard</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<FlightStats />
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
		flex: 0.6;
		padding: 25px 50px;
	}

</style>
