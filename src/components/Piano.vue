<template>
  <!-- Piano container -->
  <div class="mt-5 container has-text-centered">
    <!-- Display controls -->
    <Controls
      class="mb-5"
      v-on:oscillator-click-event="handleOscillatorClick"
    />
    <!-- Loop through all the keys -->
    <div class="key-container" v-for="key in keys" :key="key.id">
      <Key v-bind:pianoKey="key" v-on:key-click-event="handleKeyClick" />
    </div>
    <!-- <div>
      <strong> For debugging only</strong>
      <br />
      Attack: {{ this.synth.envelope.attack }}
      <br />
      Sustain: {{ this.synth.envelope.sustain }}
      <br />
      Decay: {{ this.synth.envelope.decay }}
      <br />
      Release: {{ this.synth.envelope.release }}
      <br />
      Oscillator: {{ this.synth.oscillator.type }}
    </div> -->
  </div>
</template>

<script>
import Key from "./Key";
import Controls from "./Controls";
import * as Tone from "tone";

export default {
  name: "Piano",
  components: { Key, Controls },
  data: () => ({
    customAttack: 0.1,
    synth: new Tone.Synth({
      oscillator: {
        type: "sine",
      },
      envelope: {
        // attack goes from 0 to 1 in steps of 0.01
        attack: 0.1,

        // decay goes from 0 to 1 in steps of 0.01
        decay: 1,

        // sustain goes from 0 to 1 in steps of 0.01
        sustain: 0.35,

        // release goes from 0 to 1 in steps of 0.01
        release: 0.1,
      },
    }),
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

      var pianoKey = this.keys.filter(function(e) {
        return e.character === pressedCharacter;
      });
      try {
        // play the sound for the pressed key
        this.synth.toDestination();
        this.synth.triggerAttackRelease(pianoKey[0].keyName + "4", "8n");
      } catch (err) {
        console.log(err);
      }

      // Cancel the default action to avoid it being handled twice
      event.preventDefault();
    });
  },
  methods: {
    handleKeyClick(pianoKey) {
      // play sound from the clicked key
      this.synth.toDestination();
      this.synth.triggerAttackRelease(pianoKey.keyName + "4", "8n");
    },
    handleOscillatorClick(newOscillator) {
      // change the oscillator on click to the new oscillator
      this.synth.oscillator.type = newOscillator;

      // update the synth state to reflect changes
      this.$forceUpdate();
    },
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
