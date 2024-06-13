<template>
  <div class="app">
    <h2>Appmessage:{{ message }}</h2>
    <home></home>
    <button @click="toggleBoolean">是否显示category</button>
    <category v-if="isShowCategory"></category>
  </div>
</template>

<script>
  import eventBus from './utils/event-bus';
  import Home from './Home.vue';
  import Category from './Category.vue';

  export default {
    components: {
      Home,
      Category,
    },
    data() {
      return {
        message: 'Hello App',
        isShowCategory: true,
      };
    },
    methods: {
      toggleBoolean() {
        console.log(this.isShowCategory);
        this.isShowCategory = !this.isShowCategory;
        // this.isShowCategory=!isShowCategory
      },
    },
    // 除了可以发送网络请求外
    created() {
      // fetch

      // 事件监听
      // 内部对参数进行了解构
      eventBus.on('whyEvent', (name, age, height) => {
        console.log('whyEvent事件在app中监听', name, age, height);
        this.message = `name:${name},age:${age},height:${height}`;
      });
    },
  };
</script>

<style scoped></style>
