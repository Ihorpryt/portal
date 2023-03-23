<script>
    import Filter from "../lib/images/icons/filter.svelte";

    export let title;
</script>

<button name="button"><Filter/> {title}</button>

<style>
    button {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 12px;
        height: 40px;
        /* border: 1px solid #ccc; */
        border: none;
        padding: 0 18px;
        border-radius: 40px;
        background-color: white;
        font-size: 13px;
        font-weight: 600;
        cursor: pointer;

        transition: 0.3s;
    }
    button:hover {
        background-color: #F6F6F8;
    }
    :global(body.dark-mode) button {
        background: none;
        color: white;
    }
    :global(body.dark-mode) button:hover {
        background-color: rgba(255, 255, 255, 0.1);
    }
</style>