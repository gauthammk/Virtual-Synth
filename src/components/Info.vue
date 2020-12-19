<template>
  <div class="mt-5 container has-text-centered">
    <a class="button" href="https://github.com/gauthammk/Virtual-Synth">
      <span class="is-large mr-2">
        <i class="fab fa-github custom-text-dark"></i>
      </span>
      <span class="custom-text-dark custom-regular-text">Source</span>
    </a>
  </div>
</template>

<script>
export default {
  name: "Info",
};
</script>

<style scoped>
.button {
  border: none;
  box-shadow: -0.3rem 0.3rem 0 0 #bae8e8;
}
.button:focus {
  border: none;
  box-shadow: -0.3rem 0.3rem 0 0 #bae8e8;
}
.button:active {
  border: none;
  box-shadow: none;
}
.is-large {
  height: 100%;
  width: 100%;
}
</style>
