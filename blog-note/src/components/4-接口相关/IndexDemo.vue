<template>
  <FragmentDemo />
  <hr />
  <SuspenseDemo />
  <hr />
  <TeleportDemo />
</template>

<script>
import FragmentDemo from "./FragmentDemo.vue";
import SuspenseDemo from "./SuspenseDemo.vue";
import TeleportDemo from "./TeleportDemo.vue";

export default {
  components: {
    FragmentDemo,
    SuspenseDemo,
    TeleportDemo,
  },
};
</script>

<style lang="scss" scoped>
</style>