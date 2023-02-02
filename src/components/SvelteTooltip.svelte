<script>
    import Hotkey from "../components/Hotkey.svelte";

    export let tip = "";
    export let top = false;
    export let right = false;
    export let bottom = false;
    export let left = false;
    export let active = false;
    export let color = "#757575";
  
    let style = `background-color: ${color};`;
  </script>
  
  <style>
    .tooltip-wrapper {
      position: relative;
      display: inline-block;
    }
    .tooltip {
      position: absolute;
      font-family: inherit;
      display: inline-block;
      white-space: nowrap;
      color: #fff;
      opacity: 0;
      visibility: hidden;
      transition: opacity 150ms, visibility 150ms;
      transition-timing-function: ease-in-out;

      font-family: 'Inter Tight', sans-serif;
      font-size: 12px;
      line-height: 16px;
    }
  
    .default-tip {
      display: flex;
      flex-direction: row;
      align-items: center;
      gap: 8px;
      padding: 4px 6px;
      border-radius: 6px;
      color: inherit;
    }
  
    .tooltip.top {
      left: 50%;
      transform: translate(-50%, -100%);
      margin-top: -8px;
    }
  
    .tooltip.bottom {
      left: 50%;
      bottom: 0;
      transform: translate(-50%, 100%);
      margin-bottom: -8px;
    }
  
    .tooltip.left {
      left: 0;
      transform: translateX(-100%);
      margin-left: -8px;
    }
  
    .tooltip.right {
      top: 0px;  
      right: 0;
      transform: translateX(100%);
      margin-right: -8px;
      margin-top: 11px;
    }
  
    .tooltip.active {
      opacity: 1;
      visibility: initial;
    }
  
    .tooltip-slot:hover + .tooltip {
      opacity: 1;
      visibility: initial;
    }
  </style>
  
  <div class="tooltip-wrapper">
    <span class="tooltip-slot">
      <slot />
    </span>
    <div
      class="tooltip"
      class:active
      class:left
      class:right
      class:bottom
      class:top>
      {#if tip}
        <div class="default-tip" {style}>{tip} <Hotkey /> </div>
      {:else}
        <slot name="custom-tip" />
      {/if}
    </div>
  </div>