<template>
  <h2>{{ msg }}</h2>
  <p>name: {{ name }} age: {{ age }}  <button @click="resetAge">修改age</button></p>
  <!-- 两种写法等价 -->
  <ChildComp v-model:name="name" v-model:age="age"></ChildComp>&nbsp;
  <ChildComp
    v-model:name="name"
    :age="age"
    @update:age="age = $event"
  ></ChildComp>
</template>

<script setup>
import { reactive, toRefs, ref } from "vue";
import ChildComp from "./ChildComp.vue";
const user = reactive({
  name: "chang bai",
  age: 20,
});

const msg = ref("v-model参数");
const { name, age } = toRefs(user);

const resetAge = () => {
  age.value = 20;
};
</script>
<script>
export default {
  components: {
    ChildComp,
  },
};
</script>
