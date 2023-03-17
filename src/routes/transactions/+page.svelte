<script>
    import AircraftSelect from "../../components/AircraftSelect.svelte";
	import Button from "../../components/Button.svelte";
    import ButtonPrimary from "../../components/Button_Primary.svelte";
    import ButtonSmall from "../../components/Button_Small.svelte";
    import TransactionDatesSelect from "../../components/TransactionDatesSelect.svelte";
    import Caret from "../../lib/images/icons/caret.svelte";
    import Comment from "../../lib/images/icons/comment.svelte";
    import Expand from "../../lib/images/icons/expand.svelte";
    import Mark from "../../lib/images/icons/mark.svelte";
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
			<AircraftSelect />
			<TransactionDatesSelect />
			<Button title="Filter" />
			<ButtonPrimary> <Plus /> Add Transaction</ButtonPrimary>
		</div>
	</div>

	<div class="metrics">
		{#each items as item}
			<div class="metrics_item">{item.text} <div class="metrics_right-info">{item.currency} {item.amount}</div></div>
		{/each}
	</div>

	<div class="table-controls">
		<ButtonSmall><div class="ddsds">Group by:</div>  None <Caret/></ButtonSmall>
	</div>

	<div class="grid">
		<div class="row">
			<div class="item number"></div>
			<div class="item">Review</div>
			<div class="item">Date</div>
			<div class="item">Period</div>
			<div class="item">Category</div>
			<div class="item">Subcategory</div>
			<div class="item">Trip No.</div>
			<div class="item">Publish</div>
			<div class="item">Aircraft</div>
		</div>

		{#each Array(20) as _, index}
		<div class="row">
			<div class="item-content number">{index + 1} <Expand /></div>
			<div class="item-content review"><Mark/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
		</div>
		{/each}


	</div>
	<div class="grid-info">20 items</div>

</div>	


<style>
	.ddsds {
		color: aqua;
	}
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
		background: #e9ecf5;
		padding: 4px;
		display: flex;
		flex-direction: row;
		border-radius: 100px;
		gap: 4px;
		/* width: 100%; */
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

		color: rgba(21, 24, 30, 0.64);
	}
	.metrics_right-info {
		display: flex;
		flex-direction: row;

		color: #15181E;
	}

	.table-controls {
		display: flex;
		height: 40px;
		justify-content: flex-start;
    	align-items: center;
	}

	.grid {
		display: flex;
		flex-direction: column;
		border: 1px solid #E5E7EB;
		border-top-right-radius: 8px;
		border-top-left-radius: 8px;
		overflow: hidden;

		
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
		background-color: #f3f5f9;
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
		border-right: 1px solid #E5E7EB;

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
		display: flex;
		justify-content: flex-start;
    	align-items: center;
		height: 24px;
		background: #f3f5f9;
		position: sticky;
		bottom: 0;
		padding: 0 8px;

		font-size: 11px;
		line-height: 15px;
	}

	.number {
		color: #99A3B4;
		display: flex;
		flex-direction: row;
		gap: 12px;
		width: 40%;
	}
	.review {
		display: flex;
		flex-direction: row;
		gap: 12px;
		justify-content: flex-start;
    	align-items: center;
	}
</style>