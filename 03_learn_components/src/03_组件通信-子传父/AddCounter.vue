<template>
  <div>
    <button @click="btnadd(1)">+1</button>
    <button @click="btnadd(5)">+5</button>
    <button @click="btnadd(10)">+10</button>
  </div>
</template>

<script>
  export default {
    // 1.emits数组语法
    emits: ['add'],
    methods: {
      btnadd(count) {
        console.log(count);
        // 让子组件发出去一个自定义事件
        // 第一个参数定义事件名称
        // 第二个参数定义传递的参数
        this.$emit('add', count);
      },
    },
  };
</script>

<style scoped></style>
