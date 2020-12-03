<template>
  <!-- Piano contianer -->
  <div class="container has-text-centered">
    <!-- Loop through all the keys -->
    <div class="key-container" v-for="key in keys" :key="key.id">
      <WhiteKey v-if="key.type === 'white'" />
      <BlackKey v-else />
    </div>
  </div>
</template>

<script>
import WhiteKey from "./WhiteKey";
import BlackKey from "./BlackKey";
export default {
  name: "Piano",
  components: { WhiteKey, BlackKey },
  data: () => ({
    whiteKeyCount: 14,
    blackKeyCount: 10,
    keys: [
      {
        id: 1,
        keyName: "C",
        type: "white",
      },
      {
        id: 2,
        keyName: "C#",
        type: "black",
      },
      {
        id: 3,
        keyName: "D",
        type: "white",
      },
      {
        id: 4,
        keyName: "D#",
        type: "black",
      },
      {
        id: 5,
        keyName: "E",
        type: "white",
      },
      {
        id: 6,
        keyName: "F",
        type: "white",
      },
      {
        id: 7,
        keyName: "F#",
        type: "black",
      },
      {
        id: 8,
        keyName: "G",
        type: "white",
      },
      {
        id: 9,
        keyName: "G#",
        type: "black",
      },
      {
        id: 10,
        keyName: "A",
        type: "white",
      },
      {
        id: 11,
        keyName: "A#",
        type: "black",
      },
      {
        id: 12,
        keyName: "B",
        type: "white",
      },
    ],
  }),
  computed: {},
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
