<template>
  <div class="app">
    <h2 ref="title" class="title" :style="{ color: titleColor }">
      {{ message }}
    </h2>
    <button ref="btn" @click="changeTitle">修改title</button>
  </div>
  <Banner ref="banner"></Banner>
</template>

<script>
  import Banner from './Banner.vue';
  export default {
    components: {
      Banner,
    },
    data() {
      return {
        message: '你好，李银河',
        titleColor: 'red',
      };
    },
    methods: {
      changeTitle() {
        // 1.不要主动的去获取DOM，并且修改DOM内容
        this.message = 'Hello World';
        this.titleColor = 'blue';

        // 2.获取h2/button元素
        console.log(this.$refs.title);
        console.log(this.$refs.btn);

        // 3.获取Banner组件:组件实例
        console.log(this.$refs.banner);

        // 3.1在父组件中可以主动调用子组件的对象方法
        this.$refs.banner.bannerClick();

        // 3.2获取banner组件实例，获取banner中的元素
        console.log(this.$refs.banner.$el);

        // 3.3如果banner template是多个跟，拿到的是第一个node节点
        console.log(this.$refs.banner.$el.nextElementSibling);
      },
    },
  };
</script>

<style scoped></style>
