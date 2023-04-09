<template>
  <div>
    <div class="rotate-box" :style="rotateStyle"></div>
    <div class="controls">
      <p>Rotate X</p>
      <Slider class="slider" v-model="x" :min="-180" :max="180" />
      <p>Rotate Y</p>
      <Slider class="slider" v-model="y" :min="-180" :max="180" />
      <p>Rotate Z</p>
      <Slider class="slider" v-model="z" :min="-180" :max="180" />

      <ResetButton class="mt-6 mr-3" @reset="reset" />
      <CopyButton :rotate-style="rotateStyle" />
    </div>
  </div>
</template>

<script>
import Slider from "primevue/slider";
import ResetButton from "./ResetButton.vue";
import CopyButton from "./CopyButton.vue";

export default {
  components: {
    Slider,
    ResetButton,
    CopyButton,
  },
  data() {
    return {
      x: 0,
      y: 0,
      z: 0,
      perspective: 1000,
    };
  },
  computed: {
    rotateStyle() {
      return {
        transform: `rotateX(${this.x}deg) rotateY(${this.y}deg) rotateZ(${this.z}deg)`,
      };
    },
  },
  methods: {
    reset() {
      this.x = 0;
      this.y = 0;
      this.z = 0;
      this.perspective = 1000;
    },
  },
};
</script>

<style scoped>
.rotate-box {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 300px;
  height: 300px;
  background-image: linear-gradient(to right, #437797, #2724dc);
  border: 1px solid #2724dc;
  margin: 0 auto;
  transition: transform 0.5s;
}

.controls {
  margin-top: 20px;
}
.slider {
  width: 200px;
  margin: 0 auto;
  background-image: linear-gradient(to right, #437797, #2724dc);
}
</style>
