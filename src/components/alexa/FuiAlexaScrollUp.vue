<template>
  <a href="#" class="scrollUp " id="scrollUp">
    <i class="uil uil-arrow-up scrollUp__icon"></i>
  </a>
</template>

<script>
export default {
  name: "FuiAlexaScrollUp",
  methods: {
    scroll(){
      const scrollTop = document.getElementById('scrollUp')
      if(window.pageYOffset >= 560){
        scrollTop.classList.add('show-scroll');
      }else {
        scrollTop.classList.remove('show-scroll')
      }
    }
  },
  mounted() {
    window.addEventListener('scroll',this.scroll)
  }
}
</script>

<style scoped>
.scrollUp {
  position: fixed;
  right: 1rem;
  bottom: -20%;
  background-color: var(--first-color);
  opacity: .8;
  padding: 0 .3rem;
  border-radius: .4rem;
  z-index: var(--z-tooltip);
  transition: .4s;
}
.scrollUp:hover {
  background-color: var(--first-color-alt);
}
.scrollUp__icon {
  font-size: 1.5rem;
  color: #fff;
}
.show-scroll {
  bottom: 5rem;
}
</style>