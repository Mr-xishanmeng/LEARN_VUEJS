<template>
  <div class="nav-bar">
    <div class="left">
      <slot name="left">left</slot>
    </div>
    <div class="center">
      <slot name="center">center</slot>
    </div>
    <div class="right">
      <slot name="right">right</slot>
    </div>
  </div>
</template>

<script>
  export default {};
</script>

<style scoped>
  .nav-bar {
    display: flex;
    height: 44px;
    line-height: 44px;
    text-align: center;
  }
  .left {
    width: 80px;
    background-color: pink;
  }
  .center {
    flex: 1;
    background-color: skyblue;
  }
  .right {
    width: 80px;
    background-color: orange;
  }
</style>
