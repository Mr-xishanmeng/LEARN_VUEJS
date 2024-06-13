<template>
  <h2>Category</h2>
</template>

<script>
  import eventBus from './utils/event-bus.js';
  export default {
    methods: {
      whyEventHandler() {
        console.log('whyEvent事件在Category中监听');
      },
    },
    created() {
      // fetch

      // 事件监听
      // 内部对参数进行了解构
      eventBus.on('whyEvent', this.whyEventHandler);
    },
    unmounted() {
      console.log('category unmounted');
      eventBus.off('whyEvent', this.whyEventHandler);
    },
  };
</script>

<style scoped></style>
