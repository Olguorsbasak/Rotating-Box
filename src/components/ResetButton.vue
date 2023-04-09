<template>
  <Button label="Reset" @click="handleClick" />
</template>

<script>
import Button from "primevue/button";

export default {
  components: {
    Button,
  },
  methods: {
    handleClick() {
      this.$emit("reset");
    },
  },
};
</script>
<style></style>
