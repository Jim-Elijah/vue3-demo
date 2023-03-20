<template>
  <div>
    <h2>{{ msg }}</h2>
    count: {{ count }} <button @click="countClickHandler">+1</button>
  </div>
</template>

<script>
// import { ref } from "vue";
// export default {
//   setup() {
//     const msg = ref("Ref Demo");
//     const count = ref(0);

//     const countClickHandler = () => {
//       count.value++;
//     };
//     return {
//       msg,
//       count,
//       countClickHandler,
//     };
//   },
// };
//
</script>

<script setup>
import { ref } from "vue";

const msg = ref("Ref Demo");
const count = ref(0);

const countClickHandler = () => {
  count.value++;
};
</script>

<style lang="scss" scoped>
</style>