<template>
  <h1>Tu Hong Le Reaction Timer</h1>
  <button @click="startGame" :disabled="isPlaying">Play Game</button>
  <Block :delay="delay" v-if="isPlaying" @endGame="endGame" />
  <Results :reactionTime="resultTime" v-if="showResult" />
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";

export default {
  name: "App",
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      resultTime: null,
      showResult: false,
    };
  },
  methods: {
    startGame() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTimer) {
      this.isPlaying = false;
      this.showResult = true;
      this.resultTime = reactionTimer;
    },
  },
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
button {
  background-color: #0d720d;
  color: whitesmoke;
  padding: 20px;
  border: none;
  border-radius: 10px;
  font-weight: bold;
}
button:disabled {
  background-color: hsla(120, 80%, 25%, 0.25);
}
</style>
