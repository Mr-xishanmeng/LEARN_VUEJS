<template>
  <nav-bar>
    <template v-slot:left>
      <button>{{ message }}</button>
    </template>

    <template v-slot:center>
      <span>内容</span>
    </template>

    <template v-slot:right>
      <a href="#">登录</a>
    </template>
  </nav-bar>

  <!-- nav-bar只给一个插槽传入数据 -->
  <nav-bar>
    <template v-slot:[position]>
      <a href="#">注册</a>
    </template>
  </nav-bar>

  <!-- <button @click="clickPosition('left')">左边</button>
  <button @click="clickPosition('center')">中间</button>
  <button @click="clickPosition('right')">右边</button> -->
  <button @click="position = 'left'">左边</button>
  <button @click="position = 'center'">中间</button>
  <button @click="position = 'right'">右边</button>
</template>

<script>
  import NavBar from './NavBar.vue';

  export default {
    components: {
      NavBar,
    },
    data() {
      return {
        position: 'center',
        message: 'hehe',
      };
    },
  };
</script>

<style scoped></style>
