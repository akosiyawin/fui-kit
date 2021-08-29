<template>
  <section class="sponsor section" id="sponsor">
    <div class="sponsor__container container grid">
      <slot name="sponsors">
        <img v-for="item in items" :src="item" alt="sponsor_img" class="sponsor__img">
      </slot>
    </div>
  </section>
</template>
<script>
export default {
  name: "FuiMambaSponsor",
  props: {
    items: {
      type: Array,
      default: () => [
        "https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/sponsor1.png",
        "https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/sponsor2.png",
        "https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/sponsor3.png",
        "https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/sponsor4.png",
      ]
    }
  }
}
</script>

<style scoped>

</style>