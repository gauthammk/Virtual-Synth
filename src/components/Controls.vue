<template>
  <div class="mt-5 container">
    <div class="buttons is-centered">
      <div>
        <p class="custom-text-dark custom-regular-text">A</p>
        <VueCircleSlider
          v-model="customAttack"
          :circle-width="4"
          :progress-width="6"
          :knob-radius="6"
          :side="60"
          circle-color="#bae8e8"
          progress-color="#272343"
          knob-color="#272343"
        />
      </div>
      <div>
        <p class="custom-text-dark custom-regular-text">D</p>
        <VueCircleSlider
          v-model="customDelay"
          :circle-width="4"
          :progress-width="6"
          :knob-radius="6"
          :side="60"
          circle-color="#bae8e8"
          progress-color="#272343"
          knob-color="#272343"
        />
      </div>
      <div>
        <p class="custom-text-dark custom-regular-text">S</p>
        <VueCircleSlider
          v-model="customSustain"
          :circle-width="4"
          :progress-width="6"
          :knob-radius="6"
          :side="60"
          circle-color="#bae8e8"
          progress-color="#272343"
          knob-color="#272343"
        />
      </div>
      <div>
        <p class="custom-text-dark custom-regular-text">R</p>
        <VueCircleSlider
          v-model="customRelease"
          :circle-width="4"
          :progress-width="6"
          :knob-radius="6"
          :side="60"
          circle-color="#bae8e8"
          progress-color="#272343"
          knob-color="#272343"
        />
      </div>
    </div>
    <div class="buttons is-centered">
      <button class="button" @click="sineOscillatorClick">
        <span class="icon">
          <img class="is-large" src="../../public/sine-wave.svg" />
        </span>
      </button>
      <button class="button" @click="squareOscillatorClick">
        <span class="icon">
          <img class="is-large" src="../../public/square-wave.svg" />
        </span>
      </button>
      <button class="button" @click="triangleOscillatorClick">
        <span class="icon">
          <img class="is-large" src="../../public/triangle-wave.svg" />
        </span>
      </button>
      <button class="button" @click="sawtoothOscillatorClick">
        <span class="icon">
          <img class="is-large" src="../../public/sawtooth-wave.svg" />
        </span>
      </button>
    </div>
  </div>
</template>

<script>
import VueCircleSlider from "../../node_modules/vue-circle-slider/src/components/CircleSlider";

export default {
  name: "Controls",
  components: { VueCircleSlider },
  data: () => ({
    customAttack: 0.1,
    customDelay: 0.1,
    customRelease: 0.1,
    customSustain: 0.1,
  }),
  methods: {
    // send custom events with the oscillators that were clicked
    sineOscillatorClick() {
      this.$emit("oscillator-click-event", "sine");
    },
    squareOscillatorClick() {
      this.$emit("oscillator-click-event", "square");
    },
    triangleOscillatorClick() {
      this.$emit("oscillator-click-event", "triangle");
    },
    sawtoothOscillatorClick() {
      this.$emit("oscillator-click-event", "sawtooth");
    },
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
</style>
