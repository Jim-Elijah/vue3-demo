<template>
  <h2>{{ msg }}</h2>
  <p>name: {{ name }} age: {{ age }}</p>
</template>

<script setup>
import { ref, reactive, toRefs } from "vue";

const msg = ref("Fragment Demo");
const user = reactive({
  name: "chang bai",
  age: 20,
});

const { name, age } = toRefs(user);
</script>

<style lang="scss" scoped>
</style>