<template>
  <!-- Base App -->
  <div class="main fui__alexa">
    <slot>Nothing to see here!</slot>
  </div>
</template>

<script>

export default {
  name: 'FuiAlexaApp',
  props: {
    hueValue: {
      type: String,
      default: '235'
    }
  },
  mounted() {
    document.documentElement.style.setProperty('--hue-color',this.hueValue)
  }
};
</script>

<style>
@import "../../assets/scss/alexa/all.css";
</style>