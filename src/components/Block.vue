<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTimer: 0,
    };
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTimer += 5;
      }, 5);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.showBlock = false;
      this.$emit("endGame", this.reactionTimer);
    },
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
};
</script>

<style>
.block {
  width: 400px;
  background-color: #0d720d;
  font-weight: bold;
  color: whitesmoke;
  padding: 100px 100px;
  border-radius: 20px;
  margin: 50px auto;
}
</style>
