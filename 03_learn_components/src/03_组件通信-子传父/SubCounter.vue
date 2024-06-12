<template>
  <div>
    <button @click="subbtn(1)">-1</button>
    <button @click="subbtn(5)">-5</button>
    <button @click="subbtn(10)">-10</button>
  </div>
</template>

<script>
  export default {
    methods: {
      subbtn(count) {
        this.$emit('sub', count);
      },
    },
  };
</script>

<style scoped></style>
