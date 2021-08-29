<template>
<section class="products section" id="products">
  <h2 class="section__title section__title-gradient products__line">
    <slot name="title"><span v-html="title"></span></slot>
  </h2>

  <div class="products__container container grid">
    <article class="products__card" v-for="item in items">
      <div class="products__content">
        <img :src="item.imgSrc" alt="product_img" class="products__img">
        <h3 class="products__title" v-html="(item.title.length > 16) ? item.title.substr(0, 16-1) + '&hellip;' : item.title"></h3>
        <span class="products__price" v-html="(item.price.length > 9) ? item.price.substr(0, 9-1) + '&hellip;' : item.price"></span>

        <button @click="item.onClick" class="button button--flex products__button">
          <i class="ri-shopping-bag-line button__icon"></i>
        </button>
      </div>
    </article>
  </div>
</section>
</template>

<script>
export default {
  name: "FuiMambaProducts",
  props: {
    title: {
      type: String,
      default: 'Choose <br> Your Style'
    },
    items: {
      type: Array,
      default: () => [
        { title: 'Black', price: '$249', onClick: () => null,imgSrc: 'https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/product1.png',},
        { title: 'Red Black', price: '$249', onClick: () => null,imgSrc: 'https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/product2.png',},
        { title: 'Night Black', price: '$249', onClick: () => null,imgSrc: 'https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/product3.png',},
        { title: 'Blue', price: '$249', onClick: () => null,imgSrc: 'https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/product4.png',},
        { title: 'Twilight Black', price: '$232', onClick: () => null,imgSrc: 'https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/product5.png',},
      ]
    }
  }
}
</script>

<style scoped>

</style>