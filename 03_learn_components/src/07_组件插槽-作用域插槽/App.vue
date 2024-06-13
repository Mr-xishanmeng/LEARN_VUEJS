<template>
  <div class="app">
    <!-- 1.tab-control -->
    <tab-control
      :titles="['衣服', '鞋子', '裤子']"
      @tab-item-click="tabItemClick"
    ></tab-control>
    <!-- <tab-control :titles="['优选', '袜子', '裙子']"></tab-control> -->

    <!-- 2.展示内容 -->
    <h1>{{ pagecontents[currentIndex] }}</h1>

    <tab-control
      :titles="['衣服', '鞋子', '裤子']"
      @tab-item-click="tabItemClick"
    >
      <template v-slot:default="props"
        ><button>{{ props.item }}</button></template
      >
    </tab-control>
    <tab-control
      :titles="['衣服', '鞋子', '裤子']"
      @tab-item-click="tabItemClick"
    >
      <template #default="props">
        <a href="#">{{ props.item }}</a>
      </template>
    </tab-control>
  </div>
</template>

<script>
  import TabControl from './TabControl.vue';

  export default {
    components: {
      TabControl,
    },
    data() {
      return {
        pagecontents: ['衣服列表', '鞋子列表', '裤子列表'],
        currentIndex: 0,
      };
    },
    methods: {
      tabItemClick(index) {
        console.log('app:', index);
        this.currentIndex = index;
      },
    },
  };
</script>

<style scoped></style>
