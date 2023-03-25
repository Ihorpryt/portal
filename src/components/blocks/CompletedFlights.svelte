<script>
    import Button from "../Button_Secondary.svelte";
	import Tabs from "../Tabs.svelte";
	import Selector from "../Selector.svelte";

	let options = [
      { value: 'option1', label: 'Last 3 months' },
      { value: 'option2', label: 'Last 6 months' },
      { value: 'option3', label: 'Last 12 months' }
    ];

	//Tabs
	let items = ['Flights', 'Hours Flown', 'Miles Flown']
    let activeItem = 'Flights';
	const tabChange = (e) => {
		activeItem = e.detail;
	}
</script>

<div class="left-cell-group">
    <div class="group-top">
        <div class="title-group">
            <h3>Completed Flights</h3>
            <p>Another description that explains all</p>
        </div>
		<div class="right-tools">
			<Selector label="Period" options={options} />
			<Button title="Filter"/>
		</div>
    </div>

	<Tabs {items} {activeItem} on:tabChange={tabChange} />

	<div class="block">
		<div class="months">
			<p>Sep 2022</p>
			<p>3</p>
			<div class="rectangle top"></div>
		</div>
		<div class="months">
			<p>Aug 2022</p>
			<p>10</p>
			<div class="rectangle middle"></div>
		</div>
		<div class="months">
			<p>Jul 2022</p>
			<p>6</p>
			<div class="rectangle"></div>
		</div>
	</div>
</div>

<style>
    .left-cell-group {
		/* background-color: aquamarine; */
		display: flex;
		flex-direction: column;
		width: 100%;
		border: 1.5px solid #E5E7EB;
		border-radius: 24px;
		/* background-color: #F4F4F6; */
	}
    .group-top {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 10px;
	}
    .title-group {
		display: flex;
		flex-direction: column;
		gap: 6px;
		padding: 16px 0px 16px 20px;
	}
    .title-group p {
		margin: 0;
		font-family: 'Manrope';
		font-style: normal;
		font-weight: 400;
		letter-spacing: 0.02em;
		font-size: 13px;
		line-height: 18px;
		color: var(--color-text-2);
	}
	.block {
		display: flex;
		flex-direction: column;
		gap: 16px;
		background-color: #f3f5f9;
		padding: 20px 10px 20px 30px;
		border-bottom-left-radius: 24px;
		border-bottom-right-radius: 24px;
		border-top: 1px solid #E5E7EB;

	}
	.right-tools {
		display: flex;
		flex-direction: row;
		gap: 12px;
	}
	.months {
		display: flex;
		flex-direction: row;
		align-items: center;
	}
	.months p:first-child {
		width: 100px;
		margin: 0;
		font-size: 13px;
	}
	.months p:nth-child(2) {
		width: 50px;
		text-align: end;
		margin: 0 24px 0 0;
		font-size: 13px;
	}
	.rectangle {
		background-color: #0373B7;
		height: 14px;
		width: 270px;
		border-radius: 40px;
	}
	.top {
		width: 135px;
		background-color: #6EC8C2;
	}
	.middle {
		width: 450px;
		background-color: #1EAAE2;
	}
	:global(body.dark-mode) .left-cell-group {
		background: #242526;
		border: 0.5px solid rgba(255,255,255,0.1);
	}
	:global(body.dark-mode) h3 {
		color: white;
	}
	:global(body.dark-mode) .block {
		background: #2E2F30;
		border: none;
	}
	:global(body.dark-mode) .months p {
		color: #fff;
	}
	:global(body.dark-mode) .title-group p {
		color:rgba(255, 255, 255, 0.75);
	}
</style>