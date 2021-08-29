<template>

</template>

<script>
export default {
  name: "FuiMambaScrollbarTheme",
  mounted() {
    document.querySelector('html').classList.add('fui__mamba-scrollbar')
  }
}
</script>

<style>
.fui__mamba-scrollbar ::-webkit-scrollbar {
  width: .60rem;
  border-radius: .5rem;
}

.fui__mamba-scrollbar ::-webkit-scrollbar-thumb {
  background-color: var(--fui-mamba-scroll-thumb-color);
  border-radius: .5rem;
}

.fui__mamba-scrollbar ::-webkit-scrollbar-thumb:hover {
  background-color: var(--fui-mamba-scroll-thumb-color-alt);
}
</style>