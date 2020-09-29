<style scoped>
* {
  font-family: Arial, Helvetica, sans-serif;
}
</style>

<template>
  <div class="container">
    <h1 v-if="seen">{{ msg }}</h1>
    <button @click="count++">count is: {{ count }}</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      greeting: "hello worls",
      seen: true,
      count: 0,
    };
  },
};
</script>