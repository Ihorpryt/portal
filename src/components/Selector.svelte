<script>
    import Caret from "../lib/images/icons/caret.svelte";

    // let options = [
    //   { value: 'option1', label: 'Last 3 months' },
    //   { value: 'option2', label: 'Last 6 months' },
    //   { value: 'option3', label: 'Last 12 months' }
    // ];

    export let options;
    
    export let label = "Label";

    export let small = false;
    export let large = false;

    let selectedOption = options[0].value;
  
    function handleSelectOption(event) {
      selectedOption = event.target.value;
    }
</script>

    <div class:small class:large>
        <p class="label">{label}</p>
        <div class="chevron"> <Caret /></div>
        <select value={selectedOption} on:change={handleSelectOption}>
            {#each options as option}
            <option value={option.value}>{option.label}</option>
            {/each}
        </select>

    </div>    

<style>

    .label {
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
    select {
        width: 147px;
        font-size: 13px;
        font-family: 'Manrope';
        font-style: normal;
        font-weight: 500;
        color: (--color-text);

        height: 40px;
        padding: 14px 16px 0 16px;
        border-radius: 48px;
        cursor: pointer;
        border: none;
        -webkit-appearance: none;
        -moz-appearance: none;
        appearance: none;
        background-color: none;
        transition: 0.3s ease-in-out;
    }
    .small select {
        width: 110px;
    }
    .large select {
        width: 155px;
    }
    
    select:hover {
        background-color: #F6F6F8;
    }
    .chevron {
        position: absolute;
        margin-top: 12px;
        margin-left: 120px;
        z-index: 1;
        pointer-events: none;
    }
    .small .chevron {
        margin-left: 83px;
    }
    .large .chevron {
        margin-left: 128px;
    }
    :global(body.dark-mode) select {
        color: white;
        background-color: rgba(255, 255, 255, 0);
    }
    :global(body.dark-mode) .label {
        color: var(--color-text-2d);
    }
    :global(body.dark-mode) select:hover {
        background-color: rgba(255, 255, 255, 0.1);
    }
</style>