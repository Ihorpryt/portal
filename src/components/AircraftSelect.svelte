<script>
    import Select from 'svelte-select';
    import Caret from '../lib/images/icons/caret.svelte';

    let items = [
        { value: 'all', label: 'All' },
        { value: 'N849WC', label: 'N849WC' },
        { value: 'T537GL', label: 'T537GL' },
    ];
</script>

<form>
    <label for="bar">Aircraft</label>
    <Select {items} 
        value="all" 
        searchable={false}  
        clearable={false} 
        showChevron 
        id="bar" 
        class="aircraft"
        --background="none"
        --border="0"
        --border-radius="24px"    
        --font-size="13px" 
        --height="40px" 
        --internal-padding="18px"  
        --selected-item-padding="14px 0 0 0"
        --border-hover="0"
        --border-focused="0"
        --chevron-width="40px"
        --selected-item-font-weight="500"
        >

        <div slot="chevron-icon">
            <Caret />
        </div>
    </Select>
</form>

<style>
    :global(#bar) {
        cursor: pointer !important;
    }
    :global(.aircraft) {
        width: 110px !important;
        cursor: pointer !important; 
    }
    :global(.aircraft):hover {
        background: #F6F6F8 !important;
    }
    label {
        pointer-events: none;
        font-family: 'Manrope';
        font-style: normal;
        font-weight: 500;
        font-size: 11px;
        letter-spacing: 0.01em;
        line-height: 16px;
        color: var(--color-text-2);
        margin-left: 16px;
        margin-top: 4px;
        position: absolute;
        z-index: 10;
    }
</style>