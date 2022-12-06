<script>
    import Chart1 from "../Chart1.svelte";
    import Tabs from "../Tabs.svelte";

	//Tabs
	let items = ['All', 'Scheduled', 'Completed']
    let activeItem = 'All';
	const tabChange = (e) => {
		activeItem = e.detail;
	}
</script>

<div class="flight-stats">
    <h2>Flights Overview</h2>
    <p><span>All</span>  - Scheduled -  Completed</p>
	<Tabs {items} {activeItem} on:tabChange={tabChange} />
    <div class="block">
        <div class="left-cell-group">
            <div class="cell-row">
                <div class="cell left">
                    <p>Flights</p>
                    <p>12</p>

					<!-- Chart -->
					<Chart1 />

                </div>
                <div class="cell right">
                    <p>Flight Hours</p>
                    <p>50h 49m</p>
					<Chart1 />
                </div>
            </div>
            <div class="cell-row">
                <div class="cell left">
                    <p>Gross Revenue</p>
                    <p>$0.00</p>
					<Chart1 />
                </div>
                <div class="cell right">
                    <p>Miles Flown</p>
                    <p>27,791</p>
					<Chart1 />
                </div>
            </div>
        </div>
        <div class="right-map"></div>
    </div>
</div>

<style>

	.flight-stats {
		width: 100%;
	}
	.block {
		display: flex;
		flex-direction: row;
        gap: 25px;
	}
	.left-cell-group {
		/* background-color: aquamarine; */
		width: 100%;
	}
	.cell-row {
		display: flex;
		flex-direction: row;
	}
	.cell-row:nth-child(2) {
		border-bottom: 1px solid rgb(241,245,249);
	}
	.cell {
		display: flex;
		flex-direction: column;
		width: 100%;
		border-top: 1px solid rgb(241,245,249);
		border-right: 1px solid rgb(241,245,249);
		border-left: 1px solid rgba(241,245,249, 0); 
		height: 230px;
		padding: 20px;
	}
    .left {
        padding-left: 0;
	}
    .right {
        padding-right: 0;
        border-right: 0px;
    }
	.cell p:first-child {
		font-size: 15px;
		color: rgb(100,116,139);
		margin: 0;
	}
	.cell p:nth-child(2) {
		font-size: 25px;
		margin: 0;
		/* margin-bottom: 15px; */
	}
	.right-map {
		background-color: lightblue;
        border-radius: 8px;
		width: 100%;
	}

	h2 {
		font-size: 25px;
		font-weight: 700;
		width: 100%;
	}

	.flight-stats p span {
		color: var(--color-theme-1);
	}

	/* Chart */



</style>