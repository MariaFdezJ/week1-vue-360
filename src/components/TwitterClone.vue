<template>
  <div>
    <h1>Project Twitter Box Client</h1>
    <div class="box">
      <textarea type="text" v-model="newTweet" @input="checkInputLength" />
      <button @click="submitTweet" :disabled="submitDisable">Submit</button>
      <span class="characters"> {{ charactersLeftMessage }} </span>
    </div>
    <Tweet :tweets="tweets" />
  </div>
</template>

<script>
import Tweet from "./Tweet";

const MAX_CHARACTERS = 280;

export default {
  name: "TwitterClone",
  components: {
    Tweet
  },
  data() {
    return {
      newTweet: "",
      tweets: []
    };
  },
  computed: {
    charactersLeft() {
      return MAX_CHARACTERS - this.newTweet.length;
    },
    charactersLeftMessage() {
      return `${this.charactersLeft}/${MAX_CHARACTERS}`;
    },
    submitDisable() {
      return this.charactersLeft === MAX_CHARACTERS;
    }
  },
  methods: {
    submitTweet() {
      this.tweets.unshift(this.newTweet);
      this.newTweet = "";
    },
    checkInputLength() {
      if (this.newTweet.length > MAX_CHARACTERS)
        this.newTweet = this.newTweet.substring(0, MAX_CHARACTERS);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
  margin-right: 10px;
}
</style>
