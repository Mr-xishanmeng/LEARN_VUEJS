<template>
  <div>
    <h2>Counter:{{ counter }}</h2>
    <button @click="changeCounter">修改counter</button>
  </div>

  <!-- why绑定 -->
  <hr />
  <h2>why:{{ why }}</h2>
  <button @click="changeWhy">修改why的值</button>
</template>

<script>
  export default {
    props: {
      counter: {
        type: Number,
        default: 0,
      },
      why: {
        type: String,
        default: '',
      },
    },
    emits: ['update:counter', 'update:why'],
    methods: {
      changeCounter() {
        this.$emit('update:counter', 999);
        console.log('111');
      },
      changeWhy() {
        this.$emit('update:why', 'nihao');
      },
    },
  };
</script>

<style scoped></style>
