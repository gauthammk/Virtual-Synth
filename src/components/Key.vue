<template>
  <div
    class="key"
    v-bind:class="{
      'black-key': pianoKey.type === 'black',
      'white-key': pianoKey.type === 'white',
    }"
    @click="keyClickHandler"
  ></div>
</template>

<script>
// import Tone.js to play sounds
import * as Tone from "tone";

export default {
  name: "Key",
  props: ["pianoKey"],
  methods: {
    keyClickHandler() {
      // create a synth and connect it to the main output (your speakers)
      const synth = new Tone.Synth().toDestination();

      // play the note from the clicked key for the duration of an 8th note
      synth.triggerAttackRelease(this.pianoKey.keyName + "4", "8n");
    },
  },
};
</script>

<style>
.black-key {
  width: 2.5vw;
  height: 10vw;
  background-color: black;
  z-index: 1;
  position: absolute;
  margin-top: -17vw;
  margin-left: -1.3vw;
}
.white-key {
  width: 4vw;
  height: 17vw;
}
.key {
  outline: 1px solid grey;
  display: inline-block;
  cursor: pointer;
}
</style>
