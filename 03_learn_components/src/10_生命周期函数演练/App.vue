<template>
  <div>AppContent</div>
</template>

<script>
  export default {
    // 1.组件被创建之前
    beforeCreate() {
      console.log('beforeCreate');
    },
    // 2.组件被创建完成
    created() {
      console.log('组件被创建完成:');
      console.log('1.发送网络请求，请求数据');
      console.log('2.监听watch事件');
      console.log('3.监听eventbus事件');
    },
    // 3.组件template准备被挂载
    beforeMount() {
      console.log('beforeMount');
    },
    // 4.组件template被挂载： 虚拟DOM -> 真实DOM
    mounted() {
      console.log('mounted');
      console.log('1.获取DOM');
      console.log('2.使用DOM');
    },
  };
</script>

<style scoped></style>
