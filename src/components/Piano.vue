<template>
  <!-- Piano contianer -->
  <div class="container has-text-centered">
    <!-- Loop through all the keys -->
    <div
      class="key-container"
      v-for="whiteKey in whiteKeyCount"
      :key="whiteKey"
    >
      <WhiteKey />
    </div>
  </div>
</template>

<script>
import WhiteKey from "./WhiteKey";
// import BlackKey from "./BlackKey";
export default {
  name: "Piano",
  components: { WhiteKey },
  data: () => ({
    whiteKeyCount: 14,
    blackKeyCount: 10,
  }),
};
</script>

<style scoped>
.key-container {
  padding: 0px !important;
  margin: 0px !important;
  max-width: 50% !important;
  flex-grow: unset !important;
  display: inline-block;
  position: relative;
}
</style>
