<script>
    import Select from 'svelte-select';
    import Caret from '../lib/images/icons/caret.svelte';

    let items = [
        { value: 'last 3 months', label: 'Last 3 months' },
        { value: 'last 6 months', label: 'Last 6 months' },
        { value: 'last 12 months', label: 'Last 12 months' },
    ];
</script>

<form>
    <label for="bar">Period</label>
    <Select {items} 
        value="last 3 months" 
        searchable={false}  
        clearable={false} 
        showChevron 
        id="bar" 
        class="foo"
        --border="0"
        --border-radius="24px"    
        --font-size="13px"
        --height="40px" 
        --internal-padding="18px"  
        --selected-item-padding="14px 0 0 0"
        --selected-item-color="var(--color-text)"
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
    :global(.foo) {
        width: 150px !important;
        cursor: pointer !important; 
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
    :global(body.dark-mode) label {
        color: var(--color-text-2d);
    }
</style>