<template>
  <section class="project section fui__alexa">
    <div class="project__bg">
      <div class="project__container container grid">
        <div class="project__data">
          <h2 class="project__title"><slot name="title">{{title}}</slot></h2>
          <p class="project__description"><slot name="description">{{description}}</slot></p>
          <a :href="contactUrl" class="button button--flex button--white project__button">
            Contact Me
            <i class="uil uil-message project__icon button__icon"></i>
          </a>
        </div>
        <img
            :src="imgSrc"
            alt="contact_img" class="project__img">
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'You have a new project',
    },
    description: {
      type: String,
      default: 'Contact me now and get a 30% discount.',
    },
    contactUrl: {
      type: String,
      default: '#contactMe',
    },
    imgSrc: {
      type: String,
      default: 'https://raw.githubusercontent.com/bedimcode/responsive-portfolio-website-Alexa/main/assets/img/project.png',
    },
  },
  name: "FuiAlexaProject"
}
</script>