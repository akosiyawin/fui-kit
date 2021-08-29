<template>
  <section class="case section grid" id="case">
    <h2 class="section__title section__title-gradient">
      <slot name="title">{{ title }}</slot>
    </h2>

    <div class="case__container container grid">
      <div>
        <slot name="img">
          <img :src="imgSrc" alt="case_img" class="case__img">
        </slot>
      </div>
      <div class="case__data">
        <p class="case__description">
          <slot name="description"><span v-html="description"></span></slot>
        </p>
        <slot name="moreInfoBtn">
          <a @click="moreInfoBtnClick" href="javascript:{}" class="button button--flex">
            <slot name="moreInfoBtnIcon"><i class="button__icon" :class="moreInfoBtnIcon"></i></slot> <slot name="moreInfoBtnText"><span>{{moreInfoBtnText}}</span></slot>
          </a>
        </slot>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FuiMambaCase",
  props: {
    imgSrc: {
      type: String,
      default: "https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/case.png"
    },
    title: {
      type: String,
      default: 'Case'
    },
    moreInfoBtnText: {
      type: String,
      default: 'More info'
    },
    moreInfoBtnIcon: {
      type: String,
      default: 'ri-information-line'
    },
    moreInfoBtnClick: {
      type: Function,
      default: () => null
    },
    description: {
      type: String,
      default: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deserunt, eveniet, exercitationem. Consequuntur ipsa voluptas voluptatem!'
    },
  }
}
</script>

<style scoped>

</style>