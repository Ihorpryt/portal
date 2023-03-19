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
        background-color: #6EC8C2
    }
    .grey {
        background-color: #D7D8D9;
    }
</style>