<template>
  <div>
    <h2>{{ msg }}</h2>
  </div>
</template>

<script>
export default {
  props: ["type"],
  data(props) {
    return {
      msg: `${props.type} API`,
    };
  },
  beforeCreate() {
    console.log(this.type, "beforeCreate");
  },
  created() {
    console.log(this.type, "created");
  },
  beforeMount() {
    console.log(this.type, "beforeMount");
  },
  mounted() {
    console.log(this.type, "mounted");
    // 1s后触发组件更新
    setTimeout(() => {
      this.msg += " 生命周期";
    }, 1000);
  },
  beforeUpdate() {
    console.log(this.type, "beforeUpdate");
  },
  updated() {
    console.log(this.type, "updated");
  },
  // beforeDestroy 改名
  beforeUnmount() {
    console.log(this.type, "beforeUnmount");
  },
  // destroyed 改名
  unmounted() {
    console.log(this.type, "unmounted");
  },
};
</script>

<style lang="scss" scoped>
</style>