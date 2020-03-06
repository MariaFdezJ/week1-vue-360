<template>
  <div id="app">
    <TwitterClone />
  </div>
</template>

<script>
import TwitterClone from "./components/TwitterClone.vue";

export default {
  name: "App",
  components: {
    TwitterClone
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
