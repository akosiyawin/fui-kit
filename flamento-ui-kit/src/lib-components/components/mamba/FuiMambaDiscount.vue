<template>
<section class="discount section" id="discount">
  <div class="discount__container container grid">
    <div class="discount__animate">
      <h2 class="discount__title"><slot name="title"><span v-html="title"></span></slot></h2>
      <p class="discount__description"><slot name="subtitle"><span v-html="subtitle"></span></slot></p>
      <slot name="shopBtn">
        <a href="javascript:{}" @click="shopNowBtnClick" class="button button--flex">
          <slot name="shopNowBtnIcon"><i :class="shopNowBtnIcon" class="button__icon"></i></slot> <slot name="shopNowBtnText">{{shopNowBtnText}}</slot>
        </a>
      </slot>
    </div>
    <slot name="img">
      <img :src="imgSrc" alt="discount_img" class="discount__img">
    </slot>
  </div>
</section>
</template>

<script>
export default {
  name: "FuiMambaDiscount",
  props: {
    title: {
      type: String,
      default: 'Immerse yourself in your music'
    },
    imgSrc: {
      type: String,
      default: 'https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/discount.png'
    },
    subtitle: {
      type: String,
      default: 'Get it now, up to 50% off.'
    },
    shopNowBtnText: {
      type: String,
      default: 'Shop Now'
    },
    shopNowBtnIcon: {
      type: String,
      default: 'ri-shopping-bag-line'
    },
    shopNowBtnClick: {
      type: Function,
      default: () => null
    },
  }
}
</script>

<style scoped>

</style>