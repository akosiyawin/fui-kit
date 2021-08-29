<script>
import ScrollReveal from 'scrollreveal'
export default {
name: "FuiMambaScrollReveal",
  mounted() {
    const sr = ScrollReveal({
      distance: '60px',
      duration: 2500,
      delay: 400,
    })
    sr.reveal(`.home__header, .section__title`, {delay: 600})
    sr.reveal(`.home__footer`, {delay: 700})
    sr.reveal(`.home__img`, {delay:900,origin:'top'})

    sr.reveal(`.sponsor__img, .products__card, .footer__logo, .footer__content, .footer__copy`, {origin: 'top', interval: 200})
    sr.reveal(`.specs__data, .discount__animate`, {origin: 'left', interval: 100})
    sr.reveal(`.specs__img, .discount__img`, {origin: 'right'})
    sr.reveal(`.case__img`, {origin: 'top'})
    sr.reveal(`.case__data`)
  }
}
</script>

<template></template>
