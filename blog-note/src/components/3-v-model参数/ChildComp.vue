<template>
  <input :value="name" @input="emit('update:name', $event.target.value)" />
  <input
    type="number"
    min="0"
    max="200"
    :value="age"
    @input="emit('update:age', $event.target.value)"
  />
</template>

<script setup>
import { defineProps, defineEmits, toRefs } from "vue";

const props = defineProps({
  name: {
    type: String,
    default: "",
  },
  age: {
    type: [Number, String],
    default: 20,
  },
});

const emit = defineEmits({
  "update:name": null,
  // age校验
  "update:age": (val) => {
    if (Number(val) >= 0 && Number(val) <= 200) {
      return true;
    }
    setTimeout(() => {
      alert('age check failed!!!');
    }, 200);
    return false;
  },
});

const { name, age } = toRefs(props);
</script>

<style lang="scss" scoped>
</style>