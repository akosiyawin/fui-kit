<template>
  <!-- Base App -->
  <div class="main fui__mamba">
    <slot>Flamento UI Mamba Edition!</slot>
  </div>
</template>

<script>
export default {
  name: "FuiMambaApp",
  props: {
    hueValue: {
      type: String,
      default: '235'
    }
  },
  mounted() {
    document.documentElement.style.setProperty('--hue-color',this.hueValue)
  }
}
</script>

<style >
@import "../../assets/scss/mamba/all.css";
</style>