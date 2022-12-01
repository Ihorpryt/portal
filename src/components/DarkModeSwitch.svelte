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
        position: absolute;
        width: 100%;
        height: 100%;
        border-radius: 50px;
        transition: 0.3s;
        background-color: #d8dbe0;
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
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.3) 0%, rgba(0, 0, 0, 0) 65.62%), #CFCFCF;
        transition: 0.3s;
        }
    </style>