<script>
    import Button from "../Button_Secondary.svelte";
    import Chart1 from "../Chart1.svelte";
    import Tabs from "../Tabs.svelte";
    import CompletedFlights from "./CompletedFlights.svelte";
	import Selector from "../Selector.svelte";
    import ButtonPrimary from "../Button_Primary.svelte";
    import Plus from "../../lib/images/icons/plus.svelte";

	let options = [
      { value: 'option1', label: 'Last 3 months' },
      { value: 'option2', label: 'Last 6 months' },
      { value: 'option3', label: 'Last 12 months' }
    ];

	//Tabs
	let items = ['All', 'Scheduled', 'Completed']
    let activeItem = 'All';
	const tabChange = (e) => {
		activeItem = e.detail;
	}
</script>

<div class="flight-stats">
	<div class="top-title">
		<h2>Dashboard</h2>
		<div class="right-tools">
			<Selector label="Period" options={options} />
			<Button title="Filter"/>
			<ButtonPrimary> <Plus/> Magic</ButtonPrimary>
		</div>
	</div>	
	<!-- <Tabs {items} {activeItem} on:tabChange={tabChange} /> -->

    <div class="block">
		<div class="column">
			<div class="left-cell-group">
				<div class="group-top">
					<div class="title-group">
						<h3>Flights Stats</h3>
						<p>Something that explains all and maybe more</p>
					</div>
					<div class="right-tools">
						<Selector label="Period" options={options}/>
						<Button title="Filter"/>
					</div>
				</div>

				<div class="metrics">
					<div class="cell-row">
						<div class="cell left-top">
							<p>Flights</p>
							<p>24</p>

						</div>
						<div class="cell right-top">
							<p>Flight Hours</p>
							<p>50h 49m</p>
						</div>
					</div>
					<div class="cell-row">
						<div class="cell left-bottom">
							<p>Gross Revenue</p>
							<p>$0.00</p>
						</div>
						<div class="cell right-bottom">
							<p>Miles Flown</p>
							<p>27,791</p>
						</div>
					</div>
				</div>
			</div>
			<CompletedFlights/>
		</div>

        <div class="right-map">
		</div>
    </div>
</div>

<style>
	.flight-stats {
		display: flex;
		flex-direction: column;
		width: 100%;
	}
	.top-title {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
	}
	.column {
		display: flex;
		flex-direction: column;
		width: 100%;
		gap: 24px;
	}
	.group-top {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 10px;
	}
	.right-tools {
		display: flex;
		flex-direction: row;
		gap: 12px;
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
		font-size: 13px;
		line-height: 18px;
		color: var(--color-text-2);
		letter-spacing: 0.02em;
	}
	.block {
		margin-top: 12px;
		display: flex;
		flex-direction: row;
        gap: 24px;
	}
	.left-cell-group {
		/* background-color: aquamarine; */
		display: flex;
		flex-direction: column;
		width: 100%;
		border: 1.5px solid #E5E7EB;
		border-radius: 24px;
		/* background-color: #F4F4F6; */
		box-shadow: 0 24px 48px 0 rgba(0,0,0,.06);
	}
	.metrics {
		display: flex;
		flex-direction: column;
		gap: 4px;
		/* background-color: #F7F7F7; */
		background: #e9ecf5;
		/* background: radial-gradient(circle, rgba(217,217,217,0.5) 10%, rgba(247,247,247,1) 50%); */
		padding: 4px;
		border-radius: 22px;
	}
	.cell-row {
		display: flex;
		flex-direction: row;
		gap: 4px;
	}
	.cell {
		display: flex;
		flex-direction: column;
		width: 100%;
		/* border: 1px solid #ebeef1; */
		background-color: #FFFFFF;
		padding: 16px 24px;
	}
	.left-top {
		border-top-left-radius: 20px;
		border-bottom-right-radius: 24px;
	}
	.left-bottom {
		border-bottom-left-radius: 20px ;
		border-top-right-radius: 24px;
	}
	.right-top {
		border-top-right-radius: 20px;
		border-bottom-left-radius: 24px ;
	}
	.right-bottom {
		border-top-left-radius: 24px;
		border-bottom-right-radius: 20px;
	}

	.cell p:first-child {
		font-size: 13px;
		line-height: 18px;
		/* color: rgb(100,116,139); */
		color: var(--color-text-2);
		margin: 0;
	}
	.cell p:nth-child(2) {
		font-size: 24px;
		margin: 0;
		margin-bottom: -2px;
		color: var(--color-text);
		/* margin-bottom: 15px; */
	}
	.right-map {
		background-image: url("../../lib/images/map.jpg");
		background-size: cover;
        border-radius: 24px;
		width: 100%;
		box-shadow: 0 24px 48px 0 rgba(0,0,0,.06);
	}

	:global(body.dark-mode) .left-cell-group {
		border: 0.5px solid rgba(255,255,255,0.1);
		background: linear-gradient(180deg,#282b30,#24272b 53.65%,#232529);
	}
	:global(body.dark-mode) .metrics {
		background: #2E2F30;
	}
	:global(body.dark-mode) .cell {
		background: #3A3B3C;
	}
	:global(body.dark-mode) .cell p:nth-child(2) {
		color: white;
	}
	:global(body.dark-mode) .cell p:nth-child(1) {
		color: rgba(255, 255, 255, 0.75);
	}
	:global(body.dark-mode) h3 {
		color:white;
	}
	:global(body.dark-mode) h2 {
		color: white;
	}
	:global(body.dark-mode) .title-group p {
		color:rgba(255, 255, 255, 0.75);
	}
</style>