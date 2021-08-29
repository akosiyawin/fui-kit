<template>
  <a href="#" class="scrollUp" :class="{'show-scroll' : scrollY >= 200}" id="scrollUp">
    <i class="ri-arrow-up-s-line scrollUp__icon"></i>
  </a>
</template>

<script>
export default {
  name: "FuiMambaScrollUp",
  data: () => ({
    scrollY: 0
  }),
  methods: {
    scroll() {
      this.scrollY = window.pageYOffset
    }
  },
  mounted() {
    window.addEventListener('scroll', this.scroll)
  }
}
</script>

<style scoped>
.scrollUp {
  position: fixed;
  right: 1rem;
  bottom: -20%;
  display: flex;
  background-color: var(--fui-mamba-container-color);
  border-radius: .25rem;
  padding: .45rem;
  opacity: 9;
  z-index: var(--fui-mamba-z-tooltip);
  transition: .4s;
}
.scrollUp__icon {
  font-size: 1.35rem;
  color: var(--fui-mamba-white-color);
}

.show-scroll {
  bottom: 5rem;
}

.scrollUp:hover {
  background-color: var(--fui-mamba-black-color);
  opacity: 1;
}
</style>