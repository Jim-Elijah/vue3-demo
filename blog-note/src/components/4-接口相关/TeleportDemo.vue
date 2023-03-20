<template>
  <h2>{{ msg }}</h2>
  <teleport to="body" v-if="isOpen">
    <div class="mask" @click="toggleOpen">
      <div class="center" @click.stop="">
        <div class="header">这是header</div>
        <div class="main">点击mask关闭</div>
        <div class="footer">这是footer</div>
      </div>
    </div>
  </teleport>
  <p>
    isOpen: {{ isOpen }}
    <button @click="toggleOpen">{{ isOpen ? "关闭" : "打开" }}</button>
  </p>
</template>

<script setup>
import { ref, reactive, toRefs } from "vue";

const msg = ref("Teleport Demo");
const isOpen = ref(false);

const toggleOpen = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style scoped>
.mask {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.6);
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.center {
  width: 300px;
  height: 200px;
  border-radius: 10px;
  background: #fff;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.header,
.footer {
  padding: 20px;
  width: 100%;
  box-sizing: border-box;
  text-align: center;
}
.main {
  flex: 1;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>