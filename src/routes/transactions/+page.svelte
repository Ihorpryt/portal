<script>
	import Button from "../../components/Button_Secondary.svelte";
    import ButtonPrimary from "../../components/Button_Primary.svelte";
    import ButtonSmall from "../../components/Button_Small.svelte";
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
    import Selector from "../../components/Selector.svelte";
    import LabelMetrics from "../../components/Label_metrics.svelte";

	const items = [
    { text: 'Number of Transactions', currency: '', amount: '52', percentage: '2.4%', variant: 'red' },
    { text: 'Charter Revenue (NET)', currency: 'EUR', amount: '939,300.78', percentage: '3.8%', variant: 'green' },
    { text: 'Expenses', currency: 'EUR', amount: '6,151', percentage: '5.2%', variant: 'green' },
    { text: 'Operating Profit/Loss', currency: 'EUR', amount: '120,151', percentage: '11.1%', variant: 'green' },
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

	let options = [
      { value: 'option1', label: 'Last 3 months' },
      { value: 'option2', label: 'Last 6 months' },
      { value: 'option3', label: 'Last 12 months' }
    ];
	let aircraft = [
      { value: 'all', label: 'All' },
      { value: 'N849WC', label: 'N849WC' },
      { value: 'T537GL', label: 'T537GL' }
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
			<Selector label="Aircraft" options={aircraft} small/>
			<Selector label="Transactions dates" options={options} large />
			<Button title="Filter" />
			<ButtonPrimary> <Plus /> Add Transaction</ButtonPrimary>
		</div>
	</div>

	<div class="metrics">
		{#each items as item}
			<div class="metrics_item" class:open>
				{item.text} 
				<div class="metrics_right-info">{item.currency} {item.amount}</div>
				<div class:open class="numbers">
					<LabelMetrics variant={item.variant} >{item.percentage}</LabelMetrics>
				</div>
			</div>
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
		<div class="row">
			<div class="item-content number">21 <Expand /></div>
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
			<div class="item-content number">22 <Expand /></div>
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
		font-weight: 400;
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
		box-shadow: 0 24px 48px 0 rgba(0,0,0,.06);
	}
	.metrics_item {
		display: flex;
		flex-direction: row;
		position: relative;
		width: 100%;

		font-weight: 400;
		font-size: 13px;
		line-height: 18px;
		justify-content: space-between;
		padding: 12px 24px;
		
		background-color: white;
		border-radius: 21px;
		transition: 0.3s;

		color: var(--color-text-2);
		/* box-shadow: 0 2px 4px #0000000f; */
	}
	.open {
		flex-direction: column;
		gap: 6px;
		padding: 12px 24px 16px 24px;
	}
	.open .metrics_right-info {
		font-size: 24px;
		font-weight: 400;
	}
	.numbers {
		display: none;
	}
	.open .numbers {
		display: block;
		position: absolute;
		right: 0;
		top:8px;
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
		font-weight: 500;

		color: var(--color-text);
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
		border: 1px solid var(--light-border);
		border-top-right-radius: 8px;
		border-top-left-radius: 8px;
		overflow: hidden;

		
	}
	.row {
		display: flex;
		flex-direction: row;
		border-bottom: 1px solid var(--light-border);
	}
	.item {
		display: flex;
		justify-content: flex-start;
    	align-items: center;
		padding: 0 8px;
		background-color: #f3f5f9;
		color: var(--color-text);
		text-align: center;
		border-right: 1px solid var(--light-border);
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
	:global(body.dark-mode) .metrics {
		background: #2E2F30;
		border: 0.5px solid rgba(255,255,255,0.1);

	}
	:global(body.dark-mode) .metrics_item {
		background: #3A3B3C;
		color: var(--color-text-2d)
	}
	:global(body.dark-mode) .metrics_right-info {
		color: white;
	}
	:global(body.dark-mode) .arrow-control {
		background-color: #3A3B3C;
	}
	:global(body.dark-mode) h2 {
	color: white;
	}
	:global(body.dark-mode) .group-by {
		color: var(--color-text-2d);
	}


	:global(body.dark-mode) .grid {
		border: 1px solid var(--dark-border);
	}
	:global(body.dark-mode) .row {
		border-bottom: 1px solid var(--dark-border);
	}
	:global(body.dark-mode) .item {
		background-color: #0d0e0e;
		color: var(--color-text-2d);
		border-right: 1px solid var(--dark-border);
	}
	:global(body.dark-mode) .item-content {
		border-right: 1px solid var(--dark-border);
		color: white;
	}
	:global(body.dark-mode) .grid-info {
		background: #0d0e0e;
		color: var(--color-text-2d);
	}
</style>