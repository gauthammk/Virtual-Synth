<template>
  <div class="section is-vcentered">
    <Heading />
    <Piano />
    <Octave />
    <Info />
  </div>
</template>

<script>
import "./../node_modules/bulma/css/bulma.css";
import Heading from "./components/Heading";
import Octave from "./components/Octave";
import Piano from "./components/Piano";
import Info from "./components/Info";

export default {
  name: "App",
  components: { Heading, Octave, Piano, Info },
  methods: {},
};
</script>

<style>
.section {
  min-height: 100vh !important;
  background-color: #e3f6f5;
}
</style>
