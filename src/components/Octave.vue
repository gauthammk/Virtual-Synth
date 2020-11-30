<template>
  <div class="column has-text-centered">
    <div class="buttons is-centered ocatve-style">
      <button class="button is-primary">
        <i class="fas fa-chevron-left"></i>
      </button>
      <button class="button is-primary">
        <i class="fas fa-chevron-right"></i>
      </button>
    </div>
    <p class="is-size-6">Octave</p>
  </div>
</template>

<script>
export default {
  name: "Octave",
};
</script>

<style scoped>
.buttons.is-centered{
  margin: 2px !important;
  justify-content: center;
}
</style>
