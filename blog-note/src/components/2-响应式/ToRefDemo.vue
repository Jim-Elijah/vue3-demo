<template>
  <div>
    <h2>{{ msg }}</h2>
    <p>
      {{ user.name }} {{ user.age }} {{ user.gender === "m" ? "男" : "女" }}
    </p>
    <p>age+1:{{ AgePlusOne }}</p>
  </div>
</template>

<script setup>
import { ref, reactive, toRef, computed, watch, watchEffect } from "vue";
const msg = ref("ToRef Demo");
const user = reactive({
  name: "jim",
  gender: "m",
  age: 20,
});

const age = toRef(user, "age");
setTimeout(() => {
  console.log("age++");
  age.value++;
}, 2000);

const AgePlusOne = computed(() => {
  return user.age + 1;
});

watch(() => user.age, (val, oldVal) => {
  console.log("watch age triggered.", val, oldVal);
});

watchEffect(() => {
  console.log("watchEffect age triggered.", user.age);
});
</script>

<style lang="scss" scoped>
</style>