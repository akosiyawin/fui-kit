<template>
  <section class="about section fui__alexa" id="about">
    <h2 class="section__title"><slot name="title">{{ title }}</slot></h2>
    <span class="section__subtitle"><slot name="subtitle">{{ subTitle }}</slot></span>
    <div class="about__container container grid">
      <slot name="image">
        <img
            :src="imgSrc"
            alt=""
            class="about__img"
        />
      </slot>
      <div class="about__data">
        <p class="about__description">
          <slot name="description">{{ description }}</slot>
        </p>

        <div class="about__info">
          <slot name="abouts">
            <div v-for="(about, idx) in abouts" :key="idx">
              <span class="about__info-title">{{ about.title }}</span>
              <span class="about__info-name" v-html="about.subTitle"> </span>
            </div>
          </slot>
        </div>

        <div v-if="downloadUrl" class="about__buttons">
          <a :href="downloadUrl" class="button button-flex">
            <slot name="buttonText">Download CV </slot>
            <slot name="buttonIcon"><i class="uil uil-download-alt button__icon"></i></slot>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FuiAlexaAbout",
  props: {
    title: {
      type: String,
      default: 'about me',
    },
    subTitle: {
      type: String,
      default: 'My introduction',
    },
    imgSrc: {
      type: String,
      default: 'https://github.com/bedimcode/responsive-portfolio-website-Alexa/blob/main/assets/img/about.jpg?raw=true',
    },
    downloadUrl: {
      type: String,
      default: '#',
    },
    description: {
      type: String,
      default: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odio, eanihil. Sint repellat illum maxime commodi temporibus modi.',
    },
    abouts: {
      type: [Array,Object],
      default: () => [
        { title: "08+", subTitle: "Years <br>experience" },
        { title: "20+", subTitle: "Completed <br>projects" },
        { title: "02+", subTitle: "Companies <br>worked" },
      ]
    }
  },
};
</script>
