<template>

</template>

<script>
export default {
  name: "FuiAlexaScrollbarTheme",
  mounted() {
    document.querySelector('html').classList.add('fui__alexa-scrollbar')
  }
}
</script>

<style>
/*Scroll bar*/
.fui__alexa-scrollbar ::-webkit-scrollbar {
  width: .60rem;
  background-color: var(--scroll-bar-color);
  border-radius: .5rem;
}

.fui__alexa-scrollbar ::-webkit-scrollbar-thumb {
  background-color: var(--scroll-thumb-color);
  border-radius: .5rem;
}

.fui__alexa-scrollbar ::-webkit-scrollbar-thumb:hover {
  background-color: var(--text-color-light);
}
</style>