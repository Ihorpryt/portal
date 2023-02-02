<script>
    import Sidebar from './Sidebar.svelte';
	import './styles.css';
    import Topbar from './Topbar.svelte';
	import SvelteTooltip from '../components/SvelteTooltip.svelte';
    import ChevronRight from '../lib/images/icons/chevron-right.svelte';
    import Menu from '../lib/images/icons/menu.svelte';

	let open = false;
    $: console.log(open)

    function onKeydown(e) {
        if (e.keyCode === 219) {
            open = !open
        }
    }
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@200;300;400;500;600;700;800&display=swap" rel="stylesheet">
</svelte:head>

<div class="app">

	<div class="collapse-btn-wrapper" class:margin-toggle={open} >
        <SvelteTooltip tip={open ? "Collapse" : "Expand"} right color="black">
            <button class="collapse-btn" on:click={() => open = !open} class:rotate={open}>
				<Menu/>
			</button>
        </SvelteTooltip>
    </div>

	<Sidebar open={open} />
	

	<main class:margin={open}>
		<Topbar />
		<slot />
	</main>

	<!-- <footer>
		<p>visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to learn SvelteKit</p>
	</footer> -->
</div>

<svelte:window on:keydown={onKeydown} />

<style>
	.app {
		display: flex;
		flex-direction: row;
	}

	main {
		display: flex;
		flex-direction: column;
		width: 100%;
		margin-left: 76px;
		transition: 0.3s ease-in-out;
	}
	.margin {
		margin-left: calc(20px + 200px);
	}
	/* .margin-toggle {
		margin-left: 156px;
	} */
    .collapse-btn-wrapper {
        top: 7px;
        left: 28px;
        position: fixed;
		z-index: 80;
		transition: 0.3s ease-in-out;
    }
    .collapse-btn {
		display: flex;
		justify-content: center;
		align-items: center;
        border-radius: 50px;
		/* background-color: #ECEEF1; */
		border: none;
		/* border: none; */
        background: none;
        transition: 0.3s ease-in-out;
        opacity: 1;
        z-index: 88;
		cursor: pointer;
		padding: 0;
    }
	.collapse-btn:hover {
		background-color: #E9E9E9;
	}
	/* .rotate {
		transform: rotate(180deg);
	} */

	@media (min-width: 480px) {
		/* footer {
			padding: 12px 0;
		} */
	}

	:global(body.dark-mode) .app {
		background-color: #1E1E1E;
	}
</style>
