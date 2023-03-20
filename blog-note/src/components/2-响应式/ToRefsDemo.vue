<template>
  <div>
    <h2>{{ msg }}</h2>
    <p>{{ name }} {{ age }} {{ gender === "m" ? "男" : "女" }}</p>
  </div>
</template>

<script setup>
import { ref, reactive, toRefs } from "vue";
const msg = ref("ToRefs Demo");
const user = reactive({
  name: "jim",
  gender: "m",
  age: 20,
});

setTimeout(() => {
  console.log("age++");
  user.age++;
  user.name += '又老了一岁'
}, 2000);

// 注意：直接解构响应式对象得到的属性不是响应式的，以下写法2s后age++页面不更新
// const { name, age, gender } = user;

const { name, age, gender } = toRefs(user);
</script>

<style lang="scss" scoped>
</style>