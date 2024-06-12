<template>
  <div>
    <h2>计数器:{{ counter }}</h2>

    <!-- 1.自定义add-counter，并且监听内部的add事件 -->
    <add-counter @add="addbtnclick"></add-counter>

    <!-- 2.自定义sub-counter，并且监听内部的sub事件 -->
    <sub-counter @sub="subbtnclick"></sub-counter>
  </div>
</template>

<script>
  import AddCounter from './AddCounter.vue';
  import SubCounter from './SubCounter.vue';
  export default {
    components: {
      AddCounter,
      SubCounter,
    },
    data() {
      return {
        counter: 0,
      };
    },
    methods: {
      addbtnclick(count) {
        this.counter += count;
      },
      subbtnclick(count) {
        this.counter -= count;
      },
    },
  };
</script>

<style scoped></style>
