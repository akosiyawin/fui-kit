<template>
<header class="header" :class="{'scroll-header' : offsetY >= 50}" id="header">
  <nav class="nav container">
    <a href="#" class="nav__logo">
      <img class="nav__logo" :src="logoSrc" alt="logo_img">
    </a>
    
    <div class="nav__menu" :class="{'show-menu' : toggle}" id="nav-menu">
      <ul class="nav__list">
        <li v-for="(item,idx) in items" class="nav__item">
          <a @click="toggle = !toggle; item.onClick()" :data-target="'#'+item.id" href="javascript:{}" :class="{'active-link' : idx === 0}" class="nav__link" v-html="item.title"></a>
        </li>
      </ul>
      <div class="nav__close" @click="toggle = !toggle" id="nav-close">
        <i class="ri-close-line"></i>
      </div>
    </div>

    <div class="nav__toggle" @click="toggle = !toggle" id="nav-toggle">
      <i class="ri-function-line"></i>
    </div>
  </nav>
</header>
</template>

<script>
export default {
  name: "FuiMambaNavbar",
  props: {
    logoSrc: {
      type: String,
      default: 'https://raw.githubusercontent.com/bedimcode/responsive-landing-page-headphones/main/assets/img/logo.png'
    },
    items: {
      type: Array,
      default: () => [
        {title: 'Home', id: 'home', onClick: () => location.replace('#home')},
        {title: 'Specs', id: 'specs', onClick: () => location.replace('#specs')},
        {title: 'Case', id: 'case', onClick: () => location.replace('#case')},
        {title: 'Products', id: 'products', onClick: () => location.replace('#products')},
      ]
    }
  },
  data: () => ({
    toggle: false,
    offsetY: 0
  }),
  methods: {
    scrollHeader() {
      this.offsetY = window.pageYOffset
    },
    scrollActive() {
      const sections = document.querySelectorAll('section[id]')
      sections.forEach(current => {
        const sectionHeight = current.offsetHeight
        const sectionTop = current.offsetTop - 50;
        const sectionId = current.getAttribute('id')

        if (this.offsetY > sectionTop && this.offsetY <= sectionTop + sectionHeight) {
          document.querySelector(`.nav__menu a[data-target*='${sectionId}']`)?.classList.add('active-link')
        } else {
          document.querySelector(`.nav__menu a[data-target*='${sectionId}']`)?.classList.remove('active-link')
        }
      })
    },
  },
  mounted() {
    window.addEventListener('scroll', this.scrollHeader)
    window.addEventListener('scroll', this.scrollActive)
  }
}
</script>

<style scoped>

.active-link {
  background: var(--fui-mamba-white-color);
  color: transparent;
  -webkit-background-clip: text;
  background-clip: text;
}
</style>