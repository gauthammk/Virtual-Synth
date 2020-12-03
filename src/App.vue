<template>
  <div class="section">
    <Heading />
    <Piano />
    <Octave />
  </div>
</template>

<script>
import "./../node_modules/bulma/css/bulma.css";
import Heading from "./components/Heading";
import Octave from "./components/Octave";
import Piano from "./components/Piano";

export default {
  name: "App",
  components: { Heading, Octave, Piano },
  methods: {},
};
</script>

<style></style>
