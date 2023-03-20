<template>
  <h2>{{ msg }}</h2>
  <Suspense>
    <!-- 加载完成渲染的内容 -->
    <template #default>
      <DialogDemo></DialogDemo>
    </template>
    <!-- 加载中显示的内容 -->
    <template #fallback>
      <span>{{ loadingInfo }}</span>
    </template>
  </Suspense>
</template>

<script setup>
import { defineAsyncComponent, ref } from "vue";

const DialogDemo = defineAsyncComponent(() => import("./FetchDataDemo.vue"));
const msg = ref("Suspense Demo");
const loadingInfo = ref("加载中...");
</script>

<style lang="scss" scoped>
</style>