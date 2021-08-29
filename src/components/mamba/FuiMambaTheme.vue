<template>

</template>

<script>
export default {
  name: "FuiMambaTheme",
  mounted() {
    document.body.classList.add('usingFuiMambaApp')
  }
}
</script>

<style>
.usingFuiMambaApp{
  margin: var(--fui-mamba-header-height) 0 0 0;
  background-color: var(--fui-mamba-body-color);
  color: var(--fui-mamba-text-color);
  transition: .5s;
}
</style>