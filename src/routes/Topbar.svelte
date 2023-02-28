<script>
    import DarkModeSwitch from "../components/DarkModeSwitch.svelte";
    import Caret from "../lib/images/icons/caret.svelte";
    import logoFull from '$lib/images/portside-logo-full.svg';
</script>

<div class="top-bar">
    
    <!-- <div class="corner">
		<a href="https://kit.svelte.dev">
			<img class="big-logo"src={logoFull} alt="SvelteKit" />
		</a>
	</div> -->

    <div class="page-title">WOw</div>
    <div class="right-side">
        <DarkModeSwitch />
        <div class="user-selector">
            <div class="avatar">
                <p>W</p>
            </div>
            <div class="user-selector-text">
                <p class="user-title">Warren Buffett</p>
                <p class="description">Gulfstream G700</p>
            </div>
            <div>
                <Caret />
            </div>
        </div>
    </div>
</div>

<style>
    .top-bar {
        position: fixed;

        display: flex;
        align-items: center;
        justify-content: space-between;
        width: 100%;
        right: 0;
        height: 60px;
        border-bottom: 1px solid #ebeef1;
        transition: 0.3s;
        background-color: rgba(255,255,255, 0.8);
        -webkit-backdrop-filter: blur(8px);
        backdrop-filter: blur(8px);
        z-index: 30;
    }
    .corner {
        padding-left: 102px;
        margin-bottom: -2px;
    }
    .page-title {
        font-size: 16px;
        font-weight: 400;
        color: rgb(100,116,139);
        opacity: 0;
    }
    .right-side {
        display: flex;
        align-items: center;
        justify-content: flex-end;
        gap: 25px;
        margin-right: 50px;
    }
    .user-selector {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 10px;
    }
    .avatar {
        display: flex;
        width: 40px;
        height: 40px;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background-color: #FAFE2F;
        border-radius: 8px;
        /* box-shadow: inset 0px 0px 0px 1px rgba(0,0,0, 0.1); */
    }
    .avatar p {
        font-size: 20px;
        font-weight: 300;
        line-height: 24px;
        color: #121929;
    }
    .user-selector-text {
        display: flex;
        flex-direction: column;
        gap: 2px;
    }
    .user-selector-text p {
        margin: 0;
    }
    .user-title {
        font-weight: 500;
        font-size: 14px;
        line-height: 17px;
        color: #121929;
        transition: 0.3s;
    }
    .description {
        font-size: 12px;
        line-height: 16px;
        font-weight: 400;
        color: #677489;
    }
    /* Dark mode */
    :global(body.dark-mode) .top-bar {
        background: #17181C;
        border-bottom: 0.5px solid rgba(255,255,255,0.1);
    }
    :global(body.dark-mode) .user-title {
        color: white;
    }
</style>