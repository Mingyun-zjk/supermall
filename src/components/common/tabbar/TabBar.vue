<template>
  <div id="tab-bar">
    <slot></slot>
  </div>
</template>
<script>
  export default {
    name:'TabBar'
  }
</script>
<style>
  /* 为了让 tab-bar 的宽度是整个屏幕的宽度，最好设置一下 left: 0; right: 0; */
  #tab-bar{
    display: flex;
    position: fixed;
    left: 0;     
    right: 0;
    bottom: 0;
    background-color: #f6f6f6;
    box-shadow: 0 -1px 1px rgba(100, 100, 100, .01) ;
  }
  
</style>