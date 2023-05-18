<template>
  <div class="nav-bar">
    <div class="nav-left">
      <slot name="left"></slot>
    </div>
    <div class="nav-middle">
      <slot></slot>
    </div>
    <div class="nav-right">
      <slot name="right"></slot>
    </div>
  </div>
</template>
<script setup>

</script>

<style lang="less" scoped>
.nav-bar {
  width: 100%;
  height: 40px;
  display: flex;
  justify-content: center;
  .nav-left, .nav-right {
    width: 80px;
  }
  .nav-middle {
    flex: 1;
    line-height: 40px;
    text-align: center;
    font-size: 20px;
    color: var(--primary-color);
  }

}

</style>