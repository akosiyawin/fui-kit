<template>
  <section class="specs section grid" id="specs">
    <h2 class="section__title section__title-gradient">
      <slot name="title">{{ title }}</slot>
    </h2>
    <div class="specs__container container grid">
      <div class="specs__content grid">
        <div class="specs__data" v-for="item in items">
          <i class="specs__icon" :class="item.icon"></i>
          <h3 class="specs__title" v-html="item.title"></h3>
          <span class="specs__subtitle" v-html="item.description"></span>
        </div>
      </div>

      <div>
        <slot name="img">
          <img :src="imgSrc" alt="specs_img" class="specs__img">
        </slot>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FuiMambaSpecs",
  props: {
    imgSrc: {
      type: String,
      default: "https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/specs.png"
    },
    title: {
      type: String,
      default: 'Specs'
    },
    items: {
      type: Array,
      default: () => [
        {icon: 'ri-bluetooth-line', title: 'Connection', description: 'Bluetooth v5.2'},
        {icon: 'ri-battery-charge-line', title: 'Battery', description: 'Duration 90h'},
        {icon: 'ri-plug-line', title: 'Load', description: 'Fast charge 4.2-AAC'},
        {icon: 'ri-mic-line', title: 'Microphone', description: 'Supports Apple Siri <br> and Google'},
      ]
    }
  }
}
</script>

<style scoped>

</style>