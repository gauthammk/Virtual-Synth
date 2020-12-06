<template>
  <div
    class="key"
    v-bind:class="{
      'black-key': pianoKey.type === 'black',
      'white-key': pianoKey.type === 'white',
    }"
    @mousedown="keyClick"
  ></div>
</template>

<script>
export default {
  name: "Key",
  props: ["pianoKey"],
  methods: {
    keyClick() {
      // send a custom event with the piano key that was clicked
      this.$emit("key-click-event", this.pianoKey);
    },
  },
};
</script>

<style>
.black-key {
  width: 2.5vw;
  height: 10vw;
  background-color: #272343;
  z-index: 1;
  position: absolute;
  margin-top: -17vw;
  margin-left: -1.3vw;
}
.white-key {
  width: 4vw;
  height: 17vw;
  background-color: #ffffff;
}
.key {
  display: inline-block;
  cursor: pointer;
  padding: 10%;
  border-radius: 4px;
  box-shadow: -0.3rem 0.3rem 0 0 #bae8e8;
}
.key:active {
  box-shadow: none;
}
</style>
