<script>
    import Select from 'svelte-select';
    import Caret from '../lib/images/icons/caret.svelte';

    let items = [
        { value: 'last 3 months', label: 'Last 3 months' },
        { value: 'two', label: 'Two' },
        { value: 'three', label: 'Three' },
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
        --background="none"
        --border="0"
        --border-radius="100px"    
        --font-size="14px" 
        --height="48px" 
        --internal-padding="18px"  
        --selected-item-padding="14px 0 0 0"
        --border-hover="0"
        --border-focused="0"
        --chevron-width="48px"
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
        width: 162px !important;
        cursor: pointer !important; 
    }
    :global(.foo):hover {
        background: #F6F6F8 !important;
    }
    label {
        font-family: 'Manrope';
        font-style: normal;
        font-weight: 500;
        font-size: 12px;
        line-height: 16px;
        color: rgba(77, 85, 98, 0.7);
        margin-left: 17px;
        margin-top: 7px;
        position: absolute;
        z-index: 10;
    }
</style>