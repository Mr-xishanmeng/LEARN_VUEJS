<template>
  <div class="infos">
    <h2 :class="$attrs.class">姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <h2>身高：{{ height }}</h2>

    <h2>show：{{ showMessage }}</h2>
  </div>
</template>

<script>
  export default {
    // 作用:接受父组件传递过来的属性
    // 1.props数组写法
    // 弊端：1> 不能对类型进行验证 2>没有默认值
    // props: ['name', 'age', 'height'],

    inheritAttrs: false,
    // 2.props对象语法
    props: {
      name: {
        type: String,
        default: '我是默认name',
      },
      age: {
        type: Number,
        default: 0,
      },
      height: {
        type: Number,
        default: 0,
      },
      // 重要的原则：对象类型写默认值时，需要编写default的函数，函数返回默认值
      friend: {
        type: Object,
        default: () => {
          name: 'jamess';
        },
        // default() {
        //   return { name: 'james' };
        // },
      },
      hobbies: {
        type: Array,
        default: () => ['篮球', 'rap', '唱跳'],
      },
      showMessage: {
        type: String,
        default: '',
      },
    },
  };
</script>

<style scoped></style>
