<template>
  <div class="white-key"></div>
</template>

<script>
export default {
  name: "Key",
};
</script>

<style scoped>
/* styling with inline block to get adjacent keys */
.white-key {
  width: 4vw;
  height: 17vw;
  outline: 1px solid grey;
  display: inline-block;
}
</style>
