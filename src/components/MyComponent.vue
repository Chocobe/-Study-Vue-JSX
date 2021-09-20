<template>
  <h1 class="my-title">{{ msg }}</h1>
</template>

<script>
export default {
  data: () => ({
    msg: "My Component 입니다.",
  }),
};
</script>

<style scoped>
.my-title {
  color: #ff1493;
}
</style>
