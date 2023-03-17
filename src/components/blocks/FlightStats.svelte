<script>
    import Button from "../Button.svelte";
    import Chart1 from "../Chart1.svelte";
    import Tabs from "../Tabs.svelte";
    import CompletedFlights from "./CompletedFlights.svelte";
	import Period from "../Period.svelte";
    import ButtonPrimary from "../Button_Primary.svelte";
    import Plus from "../../lib/images/icons/plus.svelte";

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
			<Period />
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
						<Period />
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
		gap: 12px;
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
		font-size: 14px;
		font-family: 'Manrope';
		font-style: normal;
		font-weight: 400;
		font-size: 14px;
		line-height: 19px;
		letter-spacing: 0.02em;
		color: rgba(21, 24, 30, 0.64);
	}
	.block {
		margin-top: 12px;
		display: flex;
		flex-direction: row;
        gap: 12px;
	}
	.left-cell-group {
		/* background-color: aquamarine; */
		display: flex;
		flex-direction: column;
		width: 100%;
		border: 1.5px solid #E5E7EB;
		border-radius: 24px;
		/* background-color: #F4F4F6; */
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
		border-top-left-radius: 24px;
		border-bottom-right-radius: 24px;
	}
	.left-bottom {
		border-bottom-left-radius: 24px ;
		border-top-right-radius: 24px;
	}
	.right-top {
		border-top-right-radius: 24px;
		border-bottom-left-radius: 24px ;
	}
	.right-bottom {
		border-top-left-radius: 24px;
		border-bottom-right-radius: 24px;
	}

	.cell p:first-child {
		font-size: 15px;
		/* color: rgb(100,116,139); */
		color: rgba(21, 24, 30, 0.64);
		margin: 0;
	}
	.cell p:nth-child(2) {
		font-size: 25px;
		margin: 0;
		margin-bottom: -2px;
		color: #15181E;
		/* margin-bottom: 15px; */
	}
	.right-map {
		background-image: url("../../lib/images/map.jpg");
		background-size: cover;
        border-radius: 24px;
		width: 100%;
	}

	h2 {
		font-family: 'Manrope';
		font-style: normal;
		font-weight: 500;
		font-size: 32px;
		font-weight: 400;
		line-height: 44px;
		/* identical to box height */

		letter-spacing: -0.03em;

		color: #15181E;
		opacity: 0.5;
		width: 100%;
		margin:0;
	}
	h3 {
		font-family: 'Manrope';
		color: #15181E;
		letter-spacing: -0.02em;
		font-weight: 600;
		font-size: 18px;
		line-height: 25px;
		margin: 0;
	}

	:global(body.dark-mode) .left-cell-group {
		border: 0.5px solid rgba(255,255,255,0.1);
		background: #242526;
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
	:global(body.dark-mode) h3 {
		color:white;
	}
	:global(body.dark-mode) h2 {
		color: white;
	}
</style>