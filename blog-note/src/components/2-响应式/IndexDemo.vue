<template>
  <RefDemo />
  <ReactiveDemo />
  <ToRefDemo />
  <ToRefsDemo />
</template>

<script>
import RefDemo from "./RefDemo.vue";
import ReactiveDemo from "./ReactiveDemo.vue";
import ToRefDemo from "./ToRefDemo.vue";
import ToRefsDemo from "./ToRefsDemo.vue";
export default {
  name: "index-demo",
  components: {
    RefDemo,
    ReactiveDemo,
    ToRefDemo,
    ToRefsDemo,
  },
};
</script>

<style lang="scss" scoped>
</style>