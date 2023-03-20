<template>
  <div>{{ mockData }}</div>
</template>

<script>
export default {
  async setup(props) {
    const fn = async () => {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve("获取数据成功!");
        }, 2000);
      });
    };
    const mockData = await fn()
    return {
      mockData,
    };
  },
};
</script>

<style lang="scss" scoped>
</style>