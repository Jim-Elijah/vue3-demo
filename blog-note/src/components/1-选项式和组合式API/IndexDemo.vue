<template>
  <div>
    <OptionsDemo type='options' />
    <CompositionDemo type='composition' />
  </div>
</template>

<script>
import OptionsDemo from "./OptionsDemo.vue";
import CompositionDemo from "./CompositionDemo.vue";
export default {
  name: "Api-style",
  components: {
    OptionsDemo,
    CompositionDemo,
  },
};
</script>

<style lang="scss" scoped>
</style>