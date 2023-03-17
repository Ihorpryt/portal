

<button name="button"><slot></slot></button>

<style>
    button {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 4px;
        height: 28px;
        /* border: 1px solid #ccc; */
        border: none;
        padding: 4px 8px;
        border-radius: 40px;
        background-color: white;
        font-family: 'Manrope';
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 19px;
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
</style>