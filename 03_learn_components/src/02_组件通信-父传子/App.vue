<template>
  <!-- 1.展示个人信息 -->
  <show-info name="wang" :age="18" :height="1.88" />

  <!-- 2.展示kobe的个人信息 -->
  <!-- 如果当前属性是一个非prop的attribute，那么还属性会默认添加到子组件的根元素上 -->
  <show-info
    name="liu"
    :age="30"
    :height="1.55"
    show-message="广州市"
    cba="abc"
    address="北京市"
    class="nihao"
  />
</template>

<script>
  import ShowInfo from './ShowInfo.vue';
  export default {
    components: {
      ShowInfo,
    },
  };
</script>

<style scoped></style>
