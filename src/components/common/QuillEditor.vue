<template>
  <div>
    <div ref="editor"></div>
  </div>
</template>

<script>
import Quill from 'quill';
import 'quill/dist/quill.snow.css'; // Import Quill's styles

export default {
  mounted() {
    // Create an instance of Quill
    this.quill = new Quill(this.$refs.editor, {
      theme: 'snow', // Specify the theme ('snow' or 'bubble')
      // Other Quill configuration options here
    });
  },
  beforeDestroy() {
    // Clean up Quill instance when component is destroyed
    if (this.quill) {
      this.quill.destroy();
      this.quill = null;
    }
  }
};
</script>

<style scoped>
/* Your component-specific styles here */
</style>
