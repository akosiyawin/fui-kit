<template>
  <footer class="footer section">
    <div class="footer__container container grid">
      <slot name="logo">
        <a href="#" class="footer__logo">
          <img :src="logoSrc" alt="footer_logo">
        </a>
      </slot>

      <div class="footer__content-links">
        <slot name="links">
          <div
              v-for="item in links"
              class="footer__content footer__content-link">
            <h3 class="footer__title" v-html="item.title"></h3>
            <ul class="footer__links">
              <li v-for="link in item.links"><a @click="link.onClick" href="#" class="footer__link"
                                                v-html="link.title"></a></li>
            </ul>
          </div>
        </slot>
      </div>

        <div class="footer__content">
          <slot name="newspaperForm">
            <form v-if="email" :action="'https://formsubmit.co/'+email" method="POST" class="footer__form">
              <input placeholder="Email" v-model="subscriber" type="email" required class="footer__input">
              <button type="submit" class="button button-flex">
                <i class="ri-send-plane-line button__icon"></i> Subscribe
              </button>
            </form>
          </slot>
          <slot name="social">
            <div class="footer__social">
              <a v-for="social in socials" @click="social.onClick" href="javascript:{}" class="footer__social-link">
                <i :class="social.icon"></i>
              </a>
            </div>
          </slot>
        </div>
    </div>

    <slot name="copy">
      <p class="footer__copy">
        <a href="javascript:{}" v-html="copy" class="footer__copy-link">
        </a>
      </p>
    </slot>
  </footer>
</template>

<script>
export default {
  name: "FuiMambaFooter",
  props: {
    logoSrc: {
      type: String,
      default: 'https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/logo.png'
    },
    email: {
      type: String,
      default: 'j.doe@email.com',
    },
    copy: {
      type: String,
      default: '&#169; Flamento. All rights reserved.',
    },
    socials: {
      type: Array,
      default: () => [
        {icon: 'ri-facebook-fill',onClick: () => null},
        {icon: 'ri-instagram-line',onClick: () => null},
        {icon: 'ri-twitter-line',onClick: () => null},
      ]
    },
    links: {
      type: Array,
      default: () => [
        {
          title: 'Products', links: [
            {
              title: 'Headphones', onClick: () => null
            },
            {
              title: 'Earphones', onClick: () => null
            },
            {
              title: 'Earbuds', onClick: () => null
            },
            {
              title: 'Accessories', onClick: () => null
            },
          ]
        },
        {
          title: 'Support', links: [
            {
              title: 'Product Help', onClick: () => null
            },
            {
              title: 'Register', onClick: () => null
            },
            {
              title: 'Support', onClick: () => null
            },
            {
              title: 'Provides', onClick: () => null
            },
          ]
        }
      ]
    }
  },
  data: () => ({
    subscriber: ''
  })
}
</script>
