<template>
  <div class="app">
    <div class="tabs">
      <template v-for="(item, index) in tabs" :key="item">
        <button
          :class="{ active: currentIndex === index }"
          @click="itemClick(index)"
        >
          {{ item }}
        </button>
      </template>
    </div>
    <div class="view">
      <!-- 1.第一种做法:v-if进行逻辑判断,决定要显示哪一个组件 -->
      <!-- <template v-if="currentIndex === 0">
        <home></home>
      </template>
      <template v-else-if="currentIndex === 1">
        <about></about>
      </template>
      <template v-else-if="currentIndex === 2">
        <Category></Category>
      </template> -->

      <!-- 2.第二种做法:动态组件 component -->
      <!-- include:组件的名称来自于组件定义时name选项 -->
      <keep-alive include="home,about">
        <component :is="tabs[currentIndex]"></component>
      </keep-alive>
    </div>
  </div>
</template>

<script>
  import { defineAsyncComponent } from 'vue';
  import Home from './views/Home.vue';
  import About from './views/About.vue';
  const AsyncCategory = defineAsyncComponent(
    () => import('./views/Category.vue')
  );

  export default {
    components: {
      Home,
      About,
      Category: AsyncCategory,
    },
    data() {
      return {
        tabs: ['home', 'about', 'category'],
        currentIndex: 0,
      };
    },
    methods: {
      itemClick(index) {
        this.currentIndex = index;
      },
    },
  };
</script>

<style scoped>
  .active {
    color: red;
  }
</style>
