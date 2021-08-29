<template>

</template>

<script>
export default {
  name: "FuiAlexaTheme",
  mounted() {
    document.body.classList.add('usingFuiAlexaApp')
  }
}
</script>

<style >
.usingFuiAlexaApp{
  margin: 0 0 var(--header-height) 0;
  background-color: var(--body-color);
  color: var(--text-color);
  transition: .5s;
}
</style>