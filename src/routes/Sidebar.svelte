<script>
	import { page } from '$app/stores';
	import DashboardIcon from '$lib/images/icons/dashboard.svelte';
	import CalendarIcon from '$lib/images/icons/calendar.svelte';
	import InvoicesIcon from '$lib/images/icons/invoices.svelte';
	import MetricsIcon from '$lib/images/icons/metrics.svelte';
	import CrewIcon from '$lib/images/icons/crew.svelte';
	import ReportsIcon from '$lib/images/icons/reports.svelte';
	import TransactionsIcon from '$lib/images/icons/transactions.svelte';
	
	import logoFull from '$lib/images/portside-logo-full.svg';
	export let open;
    // $: console.log(open)


	
</script>

<header class:open={open} >

	<div class="corner">
		<a href="https://kit.svelte.dev">
			{#if open === false}
			<div></div>
			{:else}
			<img class="big-logo"src={logoFull} alt="SvelteKit" />
			{/if}
		</a>
	</div>


	<nav>
		<ul>
			<li>
				<a href="/">
					<div aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
						<DashboardIcon color={$page.url.pathname === '/' ? '#121929' : "#97A3B6"} />
					</div>
					<span class:visible={open} >Dashboard</span>
				</a>
			</li>
			<li>
				<a href="/about">
					<div aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
						<CalendarIcon color={$page.url.pathname === '/about' ? '#121929' : "#97A3B6"} />
					</div>
					<span class:visible={open}>Calendar</span>
				</a>
			</li>
			<li>
				<a href="/invoices">
					<div aria-current={$page.url.pathname === '/invoices' ? 'page' : undefined}>
						<InvoicesIcon color={$page.url.pathname === '/invoices' ? '#121929' : "#97A3B6"} />
					</div>
					<span class:visible={open}>Invoices</span>
				</a>
			</li>
			<li>
				<a href="/metricandstats">
					<div aria-current={$page.url.pathname === '/metricandstats' ? 'page' : undefined}>
						<MetricsIcon color={$page.url.pathname === '/metricandstats' ? '#121929' : "#97A3B6"} />
					</div>
					<span class:visible={open}>Metrics & Stats</span>
				</a>
			</li>
			<li>
				<a href="/crew">
					<div aria-current={$page.url.pathname === '/crew' ? 'page' : undefined}>
						<CrewIcon color={$page.url.pathname === '/crew' ? '#121929' : "#97A3B6"} />
					</div>
					<span class:visible={open}>Crew</span>
				</a>
			</li>
			<li>
				<a href="/reports">
					<div aria-current={$page.url.pathname === '/reports' ? 'page' : undefined}>
						<ReportsIcon color={$page.url.pathname === '/reports' ? '#121929' : "#97A3B6"} />
					</div>
					<span class:visible={open}>Reports</span>
				</a>
			</li>
			<li>
				<a href="/transactions">
					<div aria-current={$page.url.pathname === '/transactions' ? 'page' : undefined}>
						<TransactionsIcon color={$page.url.pathname === '/transactions' ? '#121929' : "#97A3B6"} />
					</div>
					<span class:visible={open}>Transactions</span>
				</a>
			</li>
		</ul>

	</nav>

	<div class="user-selection">
		<div class="user-avatar">W</div>
	</div>

	<!-- <div class="footer" class:visible={open}>
		<p>© 2017-2022 Portside, Inc.</p>
	</div> -->
</header>


<style>

	header {
		position: fixed;

		display: flex;
		flex-direction: column;
		justify-content: center;
		transition: 0.3s ease-in-out;
		height: 98%;
		z-index: 1;
		min-width: 44px;
		width:44px;
		padding: 0px 20px;
		margin-top: 2px;
		margin-left: 8px;
		margin-bottom: 8px;

		/* background: #111727; */
		/* border-radius: 20px; */
		/* background-color: rgb(248, 250, 252); */
		/* border-right: 1px solid #e5e7eb; */
	}

	.corner {
		position: absolute;
        padding-left: 55px;
        top: 35px;
    }

	.footer {
		white-space: nowrap;
		visibility: hidden;
		font-size: 12px;
		color: rgb(100,116,139);
		opacity: 0;
		transition: 0.3s;
	}



	nav {
		/* margin-top: 10px; */
		display: flex;
		justify-content: left;
		align-items: flex-start;
		--background: rgba(255, 255, 255, 0.7);
		/* height: 100%; */
		margin-top: 65px;
		flex: 1;
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		margin-top:25px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: left;
		list-style: none;
		background-size: contain;
		gap: 5px;
		width: 100%;
	}

	li {
		position: relative;
		border-radius: 50px;
		padding-left: 2px;
	}
	li:hover {
		background-color: rgba(27, 27, 40, 0.03);
	}


	/* li[aria-current='page'] {
		outline: 1.5px solid #18191A;
	} */

	[aria-current='page'] {
		outline: 1.5px solid #121929;
		padding: 8px;
		border-radius: 100px;
	}
	li div {
		padding: 8px;
	}

	li[aria-current='page'] span {
		color: #121929;
	}

	/* li[aria-current='page']::before {
		--size: 8px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top:8px;
		left: -15px;
		transform: rotate(-90deg);
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	} */

	nav a {
		white-space: nowrap;
		display: flex;
		gap:12px;
		height: 44px;
		align-items: center;
		color: var(--color-text);
		font-weight: 500;
		font-size: 14px;
		text-decoration: none;
		transition: color 0.2s linear;
		font-family: 'Manrope', sans-serif;
	}
	nav a span {
		visibility: hidden;
		color: #788395;
		opacity: 0;
		transition: 0.3s;
	}
	.user-selection {
		margin-bottom: 16px;
	}
	.user-avatar {
		width: 44px;
		height: 44px;
		background-color: #FAFE2F;
		border-radius: 100px;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 20px;
	}
	/* a:hover {
		color: var(--color-theme-1);
	} */

	/* Controllers */
	.open {
        width: 180px;
    }
	.visible {
		opacity: 1;
		visibility: visible;	
	}
	:global(body.dark-mode) [aria-current='page'] {
		outline: 1.5px solid white;
		background: rgba(255, 255, 255, 0.9);
	}
</style>
