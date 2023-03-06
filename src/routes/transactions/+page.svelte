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
		{number: '-'},
		{number: 'Review'},
		{number: 'Date'},
		{number: 'Period'},
		{number: 'Category'},
		{number: 'Subcategory'},
		{number: 'Trip No.'},
		{number: 'Publish'},
		{number: 'Aircraft'},
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
		<div class="row">
			{#each numb as number}
			<div class="item">{number.number}</div>
			{/each}
		</div>

		{#each Array(20) as _, index}
		<div class="row">
			<div class="item-content">{index + 1}</div>
			<div class="item-content"></div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
		</div>
		{/each}

		<div class="grid-info"></div>

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
		display: flex;
		flex-direction: column;
		
	}
	.row {
		display: flex;
		flex-direction: row;
		border-bottom: 1px solid #E5E7EB;
	}
	.item {
		display: flex;
		justify-content: flex-start;
    	align-items: center;
		padding: 0 8px;
		background-color: #F0F1F2;
		color: #121929;
		text-align: center;
		border-right: 1px solid #E5E7EB;
		width: 100%;
		height: 32px;

		font-family: 'Manrope';
		font-style: normal;
		font-weight: 600;
		font-size: 13px;
		line-height: 18px;
	}
	.item-content {
		display: flex;
		justify-content: flex-start;
    	align-items: center;
		padding: 0 8px;
		width: 100%;
		height: 32px;

		font-family: 'Manrope';
		font-style: normal;
		font-weight: 500;
		font-size: 13px;
		line-height: 18px;
	}
	.grid div:last-child {
		border-right: 0;
	}
	.grid-info {
		height: 24px;
		background: #F0F1F2;
		position: sticky;
		bottom: 0;
	}
</style>