<template>
  <HelloWorld msg="Welcome to use Vue3" />
  <p>
    destroyChild: {{ destroyChild }}
    <button @click="destroyChild = !destroyChild">toggle destroyChild</button>
  </p>
  <!-- <ApiStyle v-if="!destroyChild" /> -->
  <!-- <ReactiveDemo /> -->
  <!-- <VModelDemo /> -->
  <FeatureDemo />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
// import ApiStyle from "./components/1-选项式和组合式API/IndexDemo.vue";
// import ReactiveDemo from './components/2-响应式/IndexDemo.vue'
// import VModelDemo from './components/3-v-model参数/IndexDemo.vue'
import FeatureDemo from "./components/4-接口相关/IndexDemo.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    // ApiStyle,
    // ReactiveDemo,
    // VModelDemo,
    FeatureDemo,
  },
  data() {
    return {
      destroyChild: false,
    };
  },
};
</script>