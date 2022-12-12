<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/svelte-logo.svg';
	import logo2 from '$lib/images/portside-logo.svg';
	import logoFull from '$lib/images/portside-logo-full.svg';
	import DashboardIcon from '$lib/images/icons/dashboard.svelte';
	import CalendarIcon from '$lib/images/icons/calendar.svelte';
	import InvoicesIcon from '$lib/images/icons/invoices.svelte';
	import MetricsIcon from '$lib/images/icons/metrics.svelte';
	import CrewIcon from '$lib/images/icons/crew.svelte';
	import ReportsIcon from '$lib/images/icons/reports.svelte';
	import TransactionsIcon from '$lib/images/icons/transactions.svelte';
	import SvelteTooltip from '../components/SvelteTooltip.svelte';
	import Hotkey from '../components/Hotkey.svelte';
	import github from '$lib/images/github.svg';

	let open = false;
    $: console.log(open)

    function onKeydown(e) {
        if (e.keyCode === 219) {
            open = !open
        }
    }

	let w;
	
</script>

<!-- <header class:open={open}   on:keydown={onKeydown} > -->
<header class:open={open}  on:keydown={onKeydown} bind:clientWidth={w}>

	{w}

	<!-- Collapse button -->
    <div class="collapse-btn-wrapper" >
        <SvelteTooltip tip={open ? "Collapse" : "Expand"} right color="black">
            <button class="collapse-btn" on:click={() => open = !open}></button>
        </SvelteTooltip>
    </div>
    <!-- Collapse button -->

	<div class="corner">
		<a href="https://kit.svelte.dev">
			{#if open === false}
			<img class="small-logo" src={logo2} alt="SvelteKit" />
			{:else}
			<img class="big-logo"src={logoFull} alt="SvelteKit" />
			{/if}
		</a>
	</div>

	<nav>
		<ul>
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">
					<DashboardIcon color={$page.url.pathname === '/' ? '#334155' : "#97A3B6"} />
					<span class:visible={open}>Dashboard</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">
					<CalendarIcon color={$page.url.pathname === '/about' ? '#334155' : "#97A3B6"} />
					<span class:visible={open}>Calendar</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/invoices' ? 'page' : undefined}>
				<a href="/invoices">
					<InvoicesIcon color={$page.url.pathname === '/invoices' ? '#334155' : "#97A3B6"} />
					<span class:visible={open}>Invoices</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/metricandstats' ? 'page' : undefined}>
				<a href="/metricandstats">
					<MetricsIcon color={$page.url.pathname === '/metricandstats' ? '#334155' : "#97A3B6"} />
					<span class:visible={open}>Metrics & Stats</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/crew' ? 'page' : undefined}>
				<a href="/crew">
					<CrewIcon color={$page.url.pathname === '/crew' ? '#334155' : "#97A3B6"} />
					<span class:visible={open}>Crew</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/reports' ? 'page' : undefined}>
				<a href="/reports">
					<ReportsIcon color={$page.url.pathname === '/reports' ? '#334155' : "#97A3B6"} />
					<span class:visible={open}>Reports</span>
				</a>
			</li>
			<li aria-current={$page.url.pathname === '/transactions' ? 'page' : undefined}>
				<a href="/transactions">
					<TransactionsIcon color={$page.url.pathname === '/transactions' ? '#334155' : "#97A3B6"} />
					<span class:visible={open}>Transactions</span>
				</a>
			</li>
			<!-- #97A3B6 -->
			<!-- <li aria-current={$page.url.pathname.startsWith('/sverdle') ? 'page' : undefined}>
				<a href="/sverdle">Invoices</a>
			</li> -->
		</ul>

	</nav>

	<div class="footer" class:visible={open}>
		<p>© 2017-2022 Portside, Inc.</p>
		<!-- <a href="https://github.com/sveltejs/kit">
			<img src={github} alt="GitHub" />
		</a> -->
	</div>
</header>


<svelte:window on:keydown={onKeydown} />

<style>

	header {
		position: fixed;
		display: flex;
		flex-direction: column;
		justify-content: center;
		transition: 0.3s ease-in-out;
		height: 100%;
		z-index: 1;
		min-width: 45px;
		width:45px;
		padding: 0px 10px;

		background-color: rgb(248, 250, 252);
		border-right: 1px solid #e5e7eb;
	}

	.corner {
		width: 100%;
		min-height: 57px;
		height: 57px;

		border-bottom: 1px solid rgb(241,245,249);
	}

	.footer {
		white-space: nowrap;
		visibility: hidden;
		font-size: 12px;
		color: rgb(100,116,139);
		opacity: 0;
		transition: 0.3s;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: left;
		padding-left: 5px;
		width: 100%;
		height: 100%;
	}

	.corner .small-logo {
		width: 2.3em;
		height: 2.3em;
		object-fit: contain;
	}

	nav {
		/* margin-top: 10px; */
		display: flex;
		justify-content: left;
		align-items: flex-start;
		--background: rgba(255, 255, 255, 0.7);
		height: 100%;
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
		border-radius: 10px;
		padding: 0 10px;
	}
	li:hover {
		background-color: rgba(27, 27, 40, 0.03);
	}


	li[aria-current='page'] {
		background-color: rgba(27, 27, 40, 0.05);
	}

	li[aria-current='page'] span {
		color: #334155;
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
		height: 45px;
		align-items: center;
		color: var(--color-text);
		font-weight: 600;
		font-size: 13px;
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

	a:hover {
		/* color: var(--color-theme-1); */
	}

	/* Controllers */
	.open {
        width: 200px;
    }
	.visible {
		opacity: 1;
		visibility: visible;	
	}

	header:hover .collapse-btn {
        opacity: 1;
    }
    .collapse-btn-wrapper {
        top: 45px;
        right: -13px;
        position: absolute;
    }
    .collapse-btn {
        width: 25px;
        height: 25px;
        border-radius: 50px;
		border: 1px solid #e5e7eb;
        background-color: white;
        transition: 0.3s ease-in-out;
        opacity: 0;
        z-index: 50;
		cursor: pointer;
    }
</style>
