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
    import DarkModeSwitch from '../components/DarkModeSwitch.svelte';
	export let open;
    // $: console.log(open)


	
</script>

<header class:open={open} >

	<div class="logo">
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
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">
					<div>
						<DashboardIcon color={$page.url.pathname === '/' ? '#121929' : "#121929"} />
					</div>
					<span class:visible={open} >Dashboard</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">
					<div >
						<CalendarIcon color={$page.url.pathname === '/about' ? '#121929' : "#121929"} />
					</div>
					<span class:visible={open}>Calendar</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/invoices' ? 'page' : undefined}>
				<a href="/invoices">
					<div>
						<InvoicesIcon color={$page.url.pathname === '/invoices' ? '#121929' : "#121929"} />
					</div>
					<span class:visible={open}>Invoices</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/metricandstats' ? 'page' : undefined}>
				<a href="/metricandstats">
					<div>
						<MetricsIcon color={$page.url.pathname === '/metricandstats' ? '#121929' : "#121929"} />
					</div>
					<span class:visible={open}>Metrics & Stats</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/crew' ? 'page' : undefined}>
				<a href="/crew">
					<div>
						<CrewIcon color={$page.url.pathname === '/crew' ? '#121929' : "#121929"} />
					</div>
					<span class:visible={open}>Crew</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/reports' ? 'page' : undefined}>
				<a href="/reports">
					<div>
						<ReportsIcon color={$page.url.pathname === '/reports' ? '#121929' : "#121929"} />
					</div>
					<span class:visible={open}>Reports</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/transactions' ? 'page' : undefined}>
				<a href="/transactions">
					<div>
						<TransactionsIcon color={$page.url.pathname === '/transactions' ? '#121929' : "#121929"} />
					</div>
					<span class:visible={open}>Transactions</span>
				</a>
			</li>
		</ul>

	</nav>

	<div class="bottom-part">
		<div class="darkmode-selector">
			<DarkModeSwitch /><p class:visible={open}>Dark Mode</p>
		</div>

		<div class="user-selection">
			<div class="user-avatar">W</div>

			<div class="user-selector-text" class:visible={open}>
                <p class="user-title">Warren Buffett</p>
                <p class="description">Gulfstream G700</p>
            </div>

		</div>
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
		height: 100%;
		z-index: 1;
		min-width: 44px;
		width:40px;
		padding: 0px 8px;
		/* border-top-right-radius: 24px;
		border-bottom-right-radius: 24px; */
		/* background: radial-gradient(516.18% 38.76% at 50% 61.24%, rgba(30, 170, 226, 0.2) 0%, rgba(30, 170, 226, 0) 100%), rgba(110, 200, 194, 0.2); */
		background-color: #f3f5f9;
		box-shadow: inset -1px 0px 1px rgba(0, 0, 0, 0.05);
		border-right: 0.5px solid rgba(0,0,0,0.1);
	}

	.logo {
		position: absolute;
        padding-left: 50px;
        top: 24px;
    }


	nav {
		/* margin-top: 10px; */
		display: flex;
		justify-content: left;
		align-items: flex-start;
		--background: rgba(255, 255, 255, 0.7);
		/* height: 100%; */
		margin-top: 48px;
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
		background-color: #f3f5f9;
	}


	/* li[aria-current='page'] {
		outline: 1.5px solid #18191A;
	} */

	[aria-current='page']  {
		outline: 1.5px solid #15181E;
		/* padding: 8px; */
		border-radius: 100px;
		/* background: white; */
		/* box-shadow: 0 0 2px rgba(0,0,0,.1), 0 2px 4px rgba(0,0,0,.1); */
	}
	li div {
		padding: 8px;
	}

	[aria-current='page'] ~ span {
		color: #15181E;
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
		gap:6px;
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
		color: #15181E;
		opacity: 0;
		transition: 0.3s;
	}
	.bottom-part {
		display: flex;
		flex-direction: column;
		gap: 36px;
	}
	.darkmode-selector {
		display: flex;
		flex-direction: row;
		flex-wrap: nowrap;
		gap: 12px;
		width: 120px;
	}
	.darkmode-selector p {
		visibility: hidden;
		color: #15181E;
		font-weight: 500;
		font-size: 12px;
		white-space: nowrap;
		opacity: 0;
		transition: 0.3s;
		/* flex-shrink: 0; */
	}
	.user-selection {
		display: flex;
		gap: 10px;
		align-items: center;
		margin-bottom: 16px;
		flex-wrap: nowrap;
		width: 150px;
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
	.user-selector-text {
		opacity: 0;
		visibility: hidden;
        display: flex;
        flex-direction: column;
        gap: 2px;
		transition: 0.3s;
    }
    .user-selector-text p {
        margin: 0;
    }
    .user-title {
        font-weight: 500;
        font-size: 14px;
        line-height: 17px;
        color: #15181E;
        transition: 0.3s;
    }
    .description {
        font-size: 12px;
        line-height: 16px;
        font-weight: 400;
        color: #677489;
    }
	/* a:hover {
		color: var(--color-theme-1);
	} */

	/* Controllers */
	.open {
        width: 180px;
    }
	.visible {
		opacity: 1 !important;
		visibility: visible !important;	
	}
	:global(body.dark-mode) [aria-current='page'] {
		outline: 1.5px solid white;
		background: rgba(255, 255, 255, 0.9);
	}
</style>
