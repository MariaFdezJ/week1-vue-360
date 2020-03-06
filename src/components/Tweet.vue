<template>
  <div>
    <div class="box" v-for="tweet in tweets" :key="tweet">
      <textarea disabled type="text" :value="tweet" />
    </div>
  </div>
</template>
<script>
export default {
  name: "Tweet",
  props: {
    tweets: Array
  }
};
</script>
<style scoped>
.box {
  width: 33%;
  background-color: #b8dcdc;
  height: 100px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1),
    0 10px 10px -5px rgba(0, 0, 0, 0.04);
}
button {
  margin-left: 10px;
}
</style>
