<template>
  <div id="app">
    <h1>Rotating Box</h1>
    <Perspective />
    <Toast />
  </div>
</template>

<script>
import Perspective from "./components/Perspective.vue";
import Toast from "primevue/toast";

export default {
  components: {
    Perspective,
  },
};
</script>

<style></style>
