<script>
    import {createEventDispatcher} from 'svelte';
    const dispatch = createEventDispatcher();

    export let items;
    export let activeItem;
</script>

<div class="tabs">
    <ul>
        {#each items as item}
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <li on:click={() => dispatch('tabChange', item)}>
                <div class:active={item === activeItem}>{item}</div>
            </li>
        {/each}
    </ul>
</div>


<style>
    .tabs {
        width: 100%;
        display: flex;
        /* margin-bottom: 20px; */
        margin-left: 34px;
    }
    ul {
        display: flex;
        justify-content: center;
        padding: 0;
        margin: 0;
        list-style-type: none;
    }
    li {
        margin: 0 15px;
        cursor: pointer;
        color: #788395;
        font-size: 15px;
        font-weight: 500;
    }
    li:first-child {
        margin-left: 0;
    }
    .active {
        color: #121929;
        border-bottom: 2px solid #121929;
        padding-bottom: 8px;
    }
</style>