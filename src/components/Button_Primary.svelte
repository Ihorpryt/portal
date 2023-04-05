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
      box-shadow: 0 8px 16px 0 rgb(27 145 224 / 20%);
      transition: 0.3s;
    }
    button:hover {
        background-color: #1198cd;
        box-shadow: 0 1px 8px 0 rgb(27 145 224 / 20%);
    }
  </style>