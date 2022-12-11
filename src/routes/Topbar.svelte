<script>
    import DarkModeSwitch from "../components/DarkModeSwitch.svelte";
</script>

<div class="top-bar">
    <div class="page-title">WOw</div>
    
    <div class="right-side">
        <DarkModeSwitch />
        <div class="user-selector">
            <div class="avatar">
                <p>JB</p>
            </div>
            <div class="user-selector-text">
                <p class="user-title">N849WC</p>
                <p class="description">Agusta Helicopter</p>
            </div>
        </div>
    </div>
</div>

<style>
    .top-bar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0 25px;
        width: 1fr;
        height: 57px;
        border-bottom: 1px solid rgb(241,245,249);
        transition: 0.3s;
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
    }
    .user-selector {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 10px;
    }
    .avatar {
        display: flex;
        width: 32px;
        height: 32px;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background-color: rgb(241,245,249);
        border-radius: 100px;
        box-shadow: inset 0px 0px 0px 1px rgba(0,0,0, 0.1);
    }
    .avatar p {
        font-size: 12px;
        line-height: 24px;
        color: #677489;
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
        font-size: 15px;
        line-height: 15px;
        transition: 0.3s;
    }
    .description {
        font-size: 12px;
        line-height: 12px;
        font-weight: 400;
        color: #677489;
    }
    /* Dark mode */
    :global(body.dark-mode) .top-bar {
        background: #131419;
        border-color: black;
    }
    :global(body.dark-mode) .user-title {
        color: white;
    }
</style>