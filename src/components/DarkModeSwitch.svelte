<script>
    function toggle() {
        window.document.body.classList.toggle('dark-mode')
    }
    </script>

    <div class="toggle-switch">
        <label>
            <input type="checkbox" on:click={toggle}>
            <span class="slider"></span>
        </label>
    </div>


    <style>

        .toggle-switch {
        position: relative;
        width: 40px;
        height: 100%;
        display: flex;
        align-items: center;
        }

        label {
        position: absolute;
        width: 100%;
        height: 24px;
        
        border-radius: 50px;
        cursor: pointer;
        }

        input {
        position: absolute;
        display: none;
        }

        .slider {
        margin-left: 2px;
        position: absolute;
        width: 40px;
        height: 100%;
        border-radius: 50px;
        transition: 0.3s;
        background-color: #fff;
        outline: 1.5px solid #E5E7EB;
        }

        input:checked ~ .slider {
        background-color: #28292c;
        }

        input:checked ~.slider::before {
        transform: translateX(16px);
        background-color: #28292c;
        box-shadow: inset 5px -4px 0px 0 rgba(216, 219, 224, 1);
        }

        .slider::before {
        content: "";
        position: absolute;
        top: 4px;
        left: 4px;
        width: 16px;
        height: 16px;
        border-radius: 50%;
        box-shadow: 0px 0px 0px 2px rgba(255, 255, 255, 0.5), 0px 0px 0px 4px rgba(255, 255, 255, 0.25),0px 0px 0px 6px rgba(255, 255, 255, 0.25);
        background: linear-gradient(180deg, rgba(207, 105, 105, 0.4) 0%, rgba(249, 177, 177, 0) 100%), #FFC700;
        transition: 0.3s;
        outline: 2px solid rgba(255, 234, 180, 0.4);
        }

        :global(body.dark-mode) .slider::before {
            outline: none;
            background: none;
        }
        :global(body.dark-mode) .slider {
            outline: none;
            background-color: #3E3F43;
        }
    </style>