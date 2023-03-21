<script>
    import AircraftSelect from "../../components/AircraftSelect.svelte";
	import Button from "../../components/Button_Secondary.svelte";
    import ButtonPrimary from "../../components/Button_Primary.svelte";
    import ButtonSmall from "../../components/Button_Small.svelte";
    import TransactionDatesSelect from "../../components/TransactionDatesSelect.svelte";
    import Caret from "../../lib/images/icons/caret.svelte";
	import Settings from "../../lib/images/icons/settings.svelte";
    import Comment from "../../lib/images/icons/comment.svelte";
    import ExpandColumn from "../../lib/images/icons/expand-column.svelte";
    import Expand from "../../lib/images/icons/expand.svelte";
    import Mark from "../../lib/images/icons/mark.svelte";
    import Plus from "../../lib/images/icons/plus.svelte";
    import DocumentSmall from "../../lib/images/icons/document-small.svelte";
    import ArrowDwn from "../../lib/images/icons/arrow-dwn.svelte";
    import MarkRed from "../../lib/images/icons/mark-red.svelte";
    import Label from "../../components/Label.svelte";
    import ArrowOpen from "../../lib/images/icons/arrow-open.svelte";

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

	let open = false;

	function handleClick() {
		open = !open
	}
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
			<div class="metrics_item" class:open>{item.text} <div class="metrics_right-info">{item.currency} {item.amount}</div></div>
		{/each}
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div class="arrow-control" on:click={handleClick}>
			<div class="arrow-icon" class:turn="{open === true}">
				<ArrowOpen />
			</div>
		</div>
	</div>

	<div class="table-controls">
		<div class="left-part">
			<ButtonSmall><div class="group-by">Group by:</div>  None <Caret/></ButtonSmall>
		</div>
		<div class="right-part">
			<ButtonSmall><DocumentSmall/><ArrowDwn/> </ButtonSmall>
			<ButtonSmall> <Settings/> Columns <Caret/></ButtonSmall>
			<ButtonSmall><ExpandColumn/></ButtonSmall>
		</div>
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

		<!-- {#each Array(20) as _, index}
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
		{/each} -->
		<div class="row">
			<div class="item-content number">1 <Expand /></div>
			<div class="item-content review"><Mark/> </div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="green">Published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">2 <Expand /></div>
			<div class="item-content review"><Mark/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="green">Published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">3 <Expand /></div>
			<div class="item-content review"><MarkRed/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="green">Published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">4 <Expand /></div>
			<div class="item-content review"><MarkRed/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="green">Published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">5 <Expand /></div>
			<div class="item-content review"><Mark/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="green">Published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">6 <Expand /></div>
			<div class="item-content review"><Mark/> </div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">7 <Expand /></div>
			<div class="item-content review"><Mark/> </div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">8 <Expand /></div>
			<div class="item-content review"><Mark color="var(--green)"/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">9 <Expand /></div>
			<div class="item-content review"><Mark color="var(--green)"/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">10 <Expand /></div>
			<div class="item-content review"><Mark/> </div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">11 <Expand /></div>
			<div class="item-content review"><Mark color="var(--green)"/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">12 <Expand /></div>
			<div class="item-content review"><Mark/> </div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">13 <Expand /></div>
			<div class="item-content review"><Mark/> </div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">14 <Expand /></div>
			<div class="item-content review"><Mark/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">15 <Expand /></div>
			<div class="item-content review"><Mark/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">16 <Expand /></div>
			<div class="item-content review"><Mark/> </div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">17 <Expand /></div>
			<div class="item-content review"><Mark/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">18 <Expand /></div>
			<div class="item-content review"><Mark/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">19 <Expand /></div>
			<div class="item-content review"><Mark/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>
		<div class="row">
			<div class="item-content number">20 <Expand /></div>
			<div class="item-content review"><Mark/> <Comment/></div>
			<div class="item-content">17 Jan 2023</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">Fuel</div>
			<div class="item-content">January 2017</div>
			<div class="item-content">January 2017</div>
			<div class="item-content"><Label variant="grey">Not published</Label></div>
			<div class="item-content">January 2017</div>
		</div>


	</div>
	<div class="grid-info">20 items</div>

</div>	


<style>
	.group-by {
		color: var(--color-text-2);
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

	.metrics {
		background: #e9ecf5;
		padding: 4px;
		display: flex;
		flex-direction: row;
		border-radius: 24px;
		gap: 4px;
		/* width: 100%; */
		margin-top: 8px;
		transition: 0.3s;
	}
	.metrics_item {
		display: flex;
		flex-direction: row;
		width: 100%;

		font-weight: 500;
		font-size: 13px;
		line-height: 18px;
		justify-content: space-between;
		padding: 12px 24px;
		background-color: white;
		border-radius: 21px;
		transition: 0.3s;

		color: var(--color-text-2);
	}
	.open {
		flex-direction: column;
		gap: 6px;
	}
	.open .metrics_right-info {
		font-size: 24px;
		font-weight: 400;
	}
	.arrow-control {
		display: flex;
		align-items: center;
		justify-content: center;
		background-color: white;
		border-radius: 100px;
		min-width: 44px;
		cursor: pointer;
	}
	.arrow-icon {
		transition: 0.3s ease;
	}
	.turn {
		transform: rotate(180deg);
	}
	.arrow-control:hover {
		background-color: #F6F6F8;
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
		justify-content: space-between;
	}
	.right-part {
		display: flex;
		gap: 4px;
		align-items: center;
		justify-content: center;
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
		height: 24px;

		font-family: 'Manrope';
		font-style: normal;
		font-weight: 600;
		font-size: 11px;
		line-height: 16px;
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
		font-weight: 400;
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