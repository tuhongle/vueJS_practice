<template>
  <div class="block">Click me</div>
</template>

<script>
export default {
  props: ["delay"],
};
</script>

<style>
.block {
  width: 400px;
  background-color: rgb(13, 114, 13);
  font-weight: bold;
  color: whitesmoke;
  padding: 50px 100px;
  margin: 50px auto;
}
</style>
