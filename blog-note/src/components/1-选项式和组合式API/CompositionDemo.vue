<template>
  <div>
    <h2>{{ msg }}</h2>
  </div>
</template>

<script>
import {
  ref,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from "vue";

export default {
  props: ["type"],
  setup(props) {
    const type = props.type
    const msg = ref(`${type} API`);

    // beforeCreate和created之前执行
    console.log(type, "setup");

    onBeforeMount(() => {
      console.log(type, "onBeforeMount");
    });
    onMounted(() => {
      console.log(type, "onMounted");
      // 1s后触发组件更新
      setTimeout(() => {
        msg.value += " 生命周期";
      }, 1000);
    });
    onBeforeUpdate(() => {
      console.log(type, "onBeforeUpdate");
    });
    onUpdated(() => {
      console.log(type, "onUpdated");
    });
    onBeforeUnmount(() => {
      console.log(type, "onBeforeUnmount");
    });
    onUnmounted(() => {
      console.log(type, "onUnmounted");
    });

    return {
      msg,
      type,
    };
  },
  beforeCreate() {
    console.log("composition beforeCreate");
  },
  created() {
    console.log("composition created");
  },
};
</script>

<style lang="scss" scoped>
</style>