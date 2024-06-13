<template>
  <h2>{{ title }}</h2>
  <div class="content">
    <slot>
      <p>我是插槽slot的默认值</p>
    </slot>
  </div>
</template>

<script>
  export default {
    props: {
      title: {
        type: String,
        default: '我是title的默认值',
      },
    },
  };
</script>

<style scoped></style>
