<script>
	export let variant = null;
</script>

<div 
class="label"
class:green={variant==='green'}
class:grey={variant==='grey'}
>
    <slot></slot>
</div>

<style>
    .label {
        background-color: #6EC8C2;
        padding: 0 8px;
        border-radius: 20px;

        font-family: 'Manrope';
		font-style: normal;
		font-weight: 400;
		font-size: 13px;
		line-height: 18px;
    }
    .green {
        background-color: var(--green-bg);
        color: var(--green-text);
    }
    .grey {
        background-color: var(--grey);
        color: var(--color-text-2);
    }

    :global(body.dark-mode) .green {
        color: var(--green);
        background-color: rgba(226, 251, 232, 0.16);
    }
    :global(body.dark-mode) .grey {
        color: var(--color-text);
        background-color: rgba(233, 236, 245, 40%);
    }
</style>