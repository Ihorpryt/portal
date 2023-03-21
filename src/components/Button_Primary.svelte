<script>

</script>

<button>
    <slot></slot>
</button>
  
  
  <style>
    button {
      display: flex;
      align-items: center;
      height: 40px;
      gap: 12px;
      background-color: #1EAAE2;
      color: #fff;
      border: none;
      border-radius: 100px;
      padding: 0 18px;
      font-size: 13px;
      font-weight: 600;
      cursor: pointer;
      white-space: nowrap;
    }
    button:hover {
        background-color: #1198cd;
    }
  </style>