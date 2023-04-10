<script>
    import ArrowForChart from "../lib/images/icons/arrow-for-chart.svelte";
    export let variant = null;

</script>
<div 
    class="label"
    class:green={variant==='green'}
    class:red={variant==='red'}
>   
    <div class="dwn">
        <ArrowForChart />
    </div>
    <slot></slot>
</div>

<style>
    .label {
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: var(--green);
        color: white;
        padding: 6px 8px;
        border-radius: 100px;
        font-family: 'Manrope';
		font-style: normal;
		font-weight: 400;
		font-size: 16px;
        gap: 4px;
    }

    .green {
        background-color: var(--green);
    }
    .red {
        background-color: var(--red);
    }
    .dwn {
        height: 16px;
    }
    .red .dwn {
        -webkit-transform: scale(-1,-1);
        transform: scaleX(-1, -1);
    }
</style>