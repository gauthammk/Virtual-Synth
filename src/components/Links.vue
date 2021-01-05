<template>
  <div class="mt-5 container">
    <div class="buttons is-centered">
      <a class="button" @click="isGuideActive = true">
        <span class="is-large mr-2">
          <i class="fas fa-info-circle custom-text-dark"></i>
        </span>
        <span class="custom-text-dark custom-regular-text">Guide</span>
      </a>
      <a class="button" href="https://github.com/gauthammk/Virtual-Synth">
        <span class="is-large mr-2">
          <i class="fab fa-github custom-text-dark"></i>
        </span>
        <span class="custom-text-dark custom-regular-text">Source</span>
      </a>
    </div>
    <!-- Display the guide if isGuideActive is true -->
    <div class="modal" v-bind:class="{ 'is-active': isGuideActive }">
      <div
        class="modal-background"
        @click="isGuideActive = !isGuideActive"
      ></div>
      <div class="modal-content">
        <div class="notification  custom-notification custom-text-dark">
          <button
            class="delete"
            aria-label="close"
            @click="isGuideActive = !isGuideActive"
          ></button>
          <strong>Hey there! here's a quick guide on using this synth. </strong>
          <br /><br />
          1. Click on the keys or use your keyboard to play sounds. The keys are
          mapped as follows:
          <strong
            >a - C, w - C#, s - D, e - D#, d - E, f - F, t - F#, g - G, y - G#,
            h - A, u - A#, j - B</strong
          >.
          <br />
          2. Click on the waveform buttons to toggle between the sine, square,
          triangle and sawtooth waveforms.
          <br />
          3. Move the sliders to modify the ADSR(Attack-Delay-Sustain-Release)
          envelope. For more information about <strong>ADSR</strong> envelopes,
          click
          <a href="https://en.wikipedia.org/wiki/Envelope_(music)">here</a>.
          <br />
          <br />If you found this project interesting, please give us a
          <a href="">star</a> on <strong>Github</strong>. Have fun!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Info",
  data: function() {
    return {
      isGuideActive: true,
    };
  },
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
.custom-notification {
  background-color: #e3f6f5;
}
</style>
