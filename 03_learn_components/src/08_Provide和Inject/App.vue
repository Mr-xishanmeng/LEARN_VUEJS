<template>
  <div class="app">
    <home></home>
    <h2>App:{{ message }}</h2>
    <button @click="message = 'hello world'">修改message</button>
  </div>
</template>

<script>
  import { computed } from 'vue';
  import Home from './Home.vue';
  export default {
    components: {
      Home,
    },
    data() {
      return {
        message: 'Hello App',
      };
    },
    // provide一般写成函数
    provide() {
      console.log(this);
      return {
        name: 'why',
        age: 18,
        message: computed(() => {
          return this.message;
        }),
      };
    },
    // provide() {
    //   return {
    //     name: 'why',
    //     age: 18,
    //     message: computed(function () {
    //       console.log(this); // 打印出来的 this 不再是组件实例
    //       return this.message; // 无法正确访问到组件实例中的 message
    //     }),
    //   };
    // },
  };
</script>

<style scoped></style>
