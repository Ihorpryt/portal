

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
        font-weight: 600;
        font-size: 13px;
        line-height: 18px;
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