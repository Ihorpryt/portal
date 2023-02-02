<script>
    // export let color = "#97A3B6";
</script>
<div class="menu">
    <div class="icon">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
        </svg>      
    </div> 
</div> 

<style>
    .menu {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 45px;
        height: 45px;
        border-radius: 10px;

    }
    /* .menu:hover {
        background-color: rgba(27, 27, 40, 0.03);
    } */
    .icon {
        width: 24px !important;
        height: 24px;
    }
    :global(body.dark-mode) .icon svg {
        stroke: #99A3B4;
    }
    :global(body.dark-mode) .icon svg:hover {
        stroke: #121929;
    }
</style>