<template>
  <!-- Piano contianer -->
  <div class="mt-5 container has-text-centered">
    <!-- Loop through all the keys -->
    <div class="key-container" v-for="key in keys" :key="key.id">
      <Key v-bind:pianoKey="key" />
    </div>
  </div>
</template>

<script>
import Key from "./Key";
// import Tone.js to play sounds
import * as Tone from "tone";

export default {
  name: "Piano",
  components: { Key },
  data: () => ({
    whiteKeyCount: 14,
    blackKeyCount: 10,
    keys: [
      {
        id: 1,
        keyName: "C",
        type: "white",
        character: "A",
      },
      {
        id: 2,
        keyName: "C#",
        type: "black",
        character: "W",
      },
      {
        id: 3,
        keyName: "D",
        type: "white",
        character: "S",
      },
      {
        id: 4,
        keyName: "D#",
        type: "black",
        character: "E",
      },
      {
        id: 5,
        keyName: "E",
        type: "white",
        character: "D",
      },
      {
        id: 6,
        keyName: "F",
        type: "white",
        character: "F",
      },
      {
        id: 7,
        keyName: "F#",
        type: "black",
        character: "T",
      },
      {
        id: 8,
        keyName: "G",
        type: "white",
        character: "G",
      },
      {
        id: 9,
        keyName: "G#",
        type: "black",
        character: "Y",
      },
      {
        id: 10,
        keyName: "A",
        type: "white",
        character: "H",
      },
      {
        id: 11,
        keyName: "A#",
        type: "black",
        character: "U",
      },
      {
        id: 12,
        keyName: "B",
        type: "white",
        character: "J",
      },
    ],
  }),
  created() {
    // listen for keypresses and play the corresponding sounds
    window.addEventListener("keydown", (event) => {
      if (event.defaultPrevented) {
        // Do nothing if the event was already processed
        return;
      }

      // get the Unicode value of the pressed key
      var pressedKeyCode = event.keyCode;

      // convert the Unicode value to ASCII
      var pressedCharacter = String.fromCharCode(pressedKeyCode);
      console.log(pressedCharacter + "key was pressed");

      var pianoKey = this.keys.filter(function(e) {
        return e.character === pressedCharacter;
      });
      try {
        // play the sound for the pressed key
        const synth = new Tone.Synth().toDestination();
        synth.triggerAttackRelease(pianoKey[0].keyName + "4", "8n");
      } catch (err) {
        console.log(err);
      }

      // Cancel the default action to avoid it being handled twice
      event.preventDefault();
    });
  },
};
</script>

<style scoped>
.key-container {
  padding: 1px !important;
  margin: 0px !important;
  max-width: 50% !important;
  flex-grow: unset !important;
  display: inline-block;
  position: relative;
}
</style>
