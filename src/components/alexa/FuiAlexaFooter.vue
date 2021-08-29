<template>
  <footer class="footer fui__alexa" id="footer">
    <div class="footer__bg">
      <div class="footer__container container grid">
        <div>
          <h1 class="footer__title"><slot name="title">{{title}}</slot></h1>
          <span class="footer__subtitle"><slot name="subtitle">{{subTitle}}</slot></span>
        </div>
        <ul class="footer__links">
          <li v-for="(item,idx) in links" :key="item.title">
            <a href="#services" class="footer__link" v-html="item.title"></a>
          </li>
        </ul>

        <div class="footer__socials">
          <a v-for="social in socials" :href="social.url" class="footer__social" target="_blank">
            <i class="uil" :class="social.icon"></i>
          </a>
        </div>
      </div>

      <p class="footer__copy" v-html="copy"></p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FuiAlexaFooter",
  props: {
    title: {
      type: String,
      default: 'Alexa',
    },
    copy: {
      type: String,
      default: '&#169; Flamento. All rights reserved.',
    },
    subTitle: {
      type: String,
      default: 'Frontend developer',
    },
    links: {
      type: Array,
      default: () => [
        {title: "Home", icon: "uil uil-estate", route: "#home", isActive: true},
        {title: "About", icon: "uil uil-user", route: "#about"},
        {title: "Services", icon: "uil uil-briefcase-alt", route: "#services"},
        {title: "Portfolio", icon: "uil uil-scenery", route: "#portfolio"},
        {title: "Contact", icon: "uil uil-message", route: "#contactMe"},
      ]
    },
    socials: {
      type: [Array, Object],
      default: () => [
        {icon: "uil uil-linkedin", url: "#"},
        {icon: "uil uil-dribbble", url: "#"},
        {icon: "uil uil-github-alt", url: "#"},
      ],
    },
  }
}
</script>
