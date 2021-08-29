<template>
  <section class="home section" id="home">
    <div class="home__container container grid">
      <div>
        <slot name="img">
          <img :src="imgSrc" alt="home_img" class="home__img">
        </slot>
      </div>

      <div class="home__data">
        <div class="home__header">
          <h1 class="home__title"><slot name="title">{{title}}</slot></h1>
          <h2 class="home__subtitle"><slot name="subtitle">{{subtitle}}</slot></h2>
        </div>

        <div class="home__footer">
          <h3 class="home__title-description"><slot name="descriptionTitle">{{descriptionTitle}}</slot></h3>
          <p class="home__description"><slot name="description">{{description}}</slot></p>
          <slot name="addToBagBtn">
            <a href="javascript:{}" @click="addToBagOnClick" class="button button--flex">
            <span class="button--flex">
              <i :class="addToBagIcon"></i> <span v-html="addToBagText"></span>
            </span>
              <span class="home__price" v-html="addToBagPrice"></span>
            </a>
          </slot>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FuiMambaHome",
  props: {
    imgSrc: {
      type: String,
      default: "https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/home.png"
    },
    title: {
      type: String,
      default: 'On ear'
    },
    subtitle: {
      type: String,
      default: 'Beats 3'
    },
    descriptionTitle: {
      type: String,
      default: 'Overview'
    },
    description: {
      type: String,
      default: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aut consequatur debitis dignissimos,facilis in incidunt ipsam.'
    },
    addToBagText: {
      type: String,
      default: 'Add to Bag'
    },
    addToBagIcon: {
      type: String,
      default: 'ri-shopping-bag-line'
    },
    addToBagPrice: {
      type: String,
      default: '$291'
    },
    addToBagOnClick: {
      type: Function,
      default: () => null
    },
   }
}
</script>

<style scoped>

</style>