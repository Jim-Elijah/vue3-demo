<template>
  <div>
    <h2>{{ msg }}</h2>
    <p>
      {{ user.name }} {{ user.age }} {{ user.gender === "m" ? "男" : "女" }}
    </p>
  </div>
</template>

<script setup>
import { ref, reactive } from "vue";
const msg = ref("Reactive Demo");
const ageRef = ref(20);
const user = reactive({
  name: "jim",
  gender: "m",
  age: ageRef,
});

setTimeout(() => {
  console.log("age++");
  ageRef.value++;
}, 2000);
</script>

<style lang="scss" scoped>
</style>