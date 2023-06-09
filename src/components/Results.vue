<template>
  <p>
    Your reaction Time is: <span>{{ reactionTime }}</span> ms
  </p>
  <h3>{{ rank }}</h3>
</template>

<script>
export default {
  props: ["reactionTime"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.reactionTime < 250) {
      this.rank = "Ninja Fingers";
    } else if (this.reactionTime < 400) {
      this.rank = "Rapid Reflexes";
    } else {
      this.rank = "Snail Pace...";
    }
  },
};
</script>

<style>
p {
  font-weight: bold;
  font-size: 1.5rem;
  font-style: italic;
  color: firebrick;
  margin-top: 50px;
  border-radius: 20px;
}

h3 {
  color: forestgreen;
  font-size: 4rem;
}

p span {
  font-size: 2rem;
}
</style>
