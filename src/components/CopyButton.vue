<template>
  <Button label="Copy" icon="pi pi-copy" @click="copyToClipboard" />
</template>

<script>
import Button from "primevue/button";
import ToastService from "primevue/toastservice";

export default {
  name: "CopyButton",
  components: {
    Button,
    ToastService,
  },
  props: {
    rotateStyle: {
      type: Object,
      required: true,
    },
  },
  methods: {
    copyToClipboard() {
      navigator.clipboard
        .writeText(`transform: ${this.rotateStyle.transform}`)
        .then(() => {
          if (this.$toast) {
            this.$toast.show({
              severity: "success",
              summary: "Success",
              detail: "CSS transform copied to clipboard!",
            });
          } else {
            console.warn("ToastService instance is not available yet.");
          }
        });
    },
  },
  mounted() {
    this.$toast = ToastService.getInstance();
  },
};
</script>
