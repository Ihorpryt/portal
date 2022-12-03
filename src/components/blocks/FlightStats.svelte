<div class="flight-stats">
    <h2>Flights Overview</h2>
    <p>All  -  Completed</p>
    <div class="block">
        <div class="left-cell-group">
            <div class="cell-row">
                <div class="cell">
                    <p>Flights</p>
                    <p>12</p>
                </div>
                <div class="cell">
                    <p>Flight Hours</p>
                    <p>50h 49m</p>
                </div>
            </div>
            <div class="cell-row">
                <div class="cell">
                    <p>Gross Revenue</p>
                    <p>$0.00</p>
                </div>
                <div class="cell">
                    <p>Miles Flown</p>
                    <p>27,791</p>
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
	}
	.left-cell-group {
		/* background-color: aquamarine; */
		width: 70%;
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
		height: 175px;
		padding: 20px;
	}
	.cell p:first-child {
		font-size: 15px;
		color: rgb(100,116,139);
		margin: 0;
	}
	.cell p:nth-child(2) {
		font-size: 25px;
		margin: 0;
	}
	.right-map {
		background-color: aqua;
		width: 100%;
	}

	h2 {
		font-size: 25px;
		font-weight: 700;
		width: 100%;
	}

</style>