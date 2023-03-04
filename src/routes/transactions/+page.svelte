<script>
	import Button from "../../components/Button.svelte";
    import ButtonPrimary from "../../components/Button_Primary.svelte";
    import Plus from "../../lib/images/icons/plus.svelte";

	const items = [
    { text: 'Number of Transactions', currency: '', amount: '52' },
    { text: 'Charter Revenue (NET)', currency: 'EUR', amount: '939,300.78' },
    { text: 'Expenses', currency: 'EUR', amount: '6,151' },
    { text: 'Operating Profit/Loss', currency: 'EUR', amount: '120,151' },
  	];

	const numb = [
	{number: 'dasdsad'},
	{number: 'dasdsad'},
	{number: 'dasdsad'},
	{number: 'dasdsad'},
	{number: 'dasdsad'},
	{number: 'dasdsad'},
	{number: 'dasdsad'},
	{number: 'dasdsad'},
	{number: 'dasdsad'},
	];
</script>

<svelte:head>
	<title>Portside App / Transactions</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>


<div class="content">

	<div class="top-title">
		<h2>Transactions</h2>
		<div class="right-tools">
			<Button title="Filter" />
			<ButtonPrimary> <Plus /> Add Transaction</ButtonPrimary>
		</div>
	</div>

	<div class="metrics">
		{#each items as item}
			<div class="metrics_item">{item.text} <div class="metrics_right-info">{item.currency} {item.amount}</div></div>
		{/each}
	</div>

	<div class="table-controls"></div>

	<div class="grid">
		{#each numb as number}
		  <div class="item">{number.number}</div>
		{/each}
	</div>

</div>	


<style>
	.content {
		display: flex;
		flex-direction: column;
		/* width: 100%; */
		padding: 0px 24px;
		margin-top: 24px;
	}
	.top-title {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		
	}
	.right-tools {
		display: flex;
		flex-direction: row;
		gap: 12px;
	}
	h2 {
		font-family: 'Manrope';
		font-style: normal;
		font-weight: 600;
		font-size: 32px;
		line-height: 44px;
		/* identical to box height */

		letter-spacing: -0.04em;

		color: #121929;
		width: 100%;
		margin:0;
	}

	.metrics {
		background: #F0F1F2;
		padding: 4px;
		display: flex;
		flex-direction: row;
		border-radius: 100px;
		gap: 4px;
		width: 100%;
		margin-top: 24px;
	}
	.metrics_item {
		display: flex;
		flex-direction: row;
		width: 100%;
		font-family: 'Manrope';
		font-style: normal;
		font-weight: 500;
		font-size: 14px;
		line-height: 20px;
		justify-content: space-between;
		padding: 12px 24px;
		background-color: white;
		border-radius: 100px;
	}
	.metrics_right-info {
		display: flex;
		flex-direction: row;
	}

	.table-controls {
		height: 40px;
	}

	.grid {
		display: grid;
		grid-template-columns: repeat(9, 1fr);
		grid-template-rows: repeat(3, 1fr);
		gap: 8px;
	}

	.item {
		background-color: #007bff;
		color: #fff;
		padding: 16px;
		text-align: center;
	}
</style>