<template>
  <header class="header fui__alexa" style="margin-bottom: 0" id="header">
    <nav class="nav container">
      <a href="#" class="nav__logo"><slot name="title"> {{ title }}</slot></a>
      <div class="nav__menu" :class="{ 'show-menu': showMenu }" id="nav-menu">
          <slot name="navItems">
            <ul class="nav__list grid">
                <li class="nav__item" v-for="(item,idx) in items" v-if="idx < 7" :key="item.title">
                  <a
                      :href="item.route"
                      class="nav__link"
                      @click="showMenu = false"
                      :class="{'active-link' : item.isActive}"
                  >
                    <i class="uil nav__icon" :class="item.icon"></i> {{ item.title }}
                  </a>
                </li>
            </ul>
          </slot>
        <i
            class="uil uil-times nav__close"
            @click="handleToggle"
            id="nav-close"
        ></i>
      </div>
      <div class="nav__btns">
        <i @click="themeButtonHandler" class="uil uil-moon change-theme" id="theme-button"></i>
        <div class="nav__toggle" id="nav-toggle">
          <i class="uil uil-apps" @click="handleToggle"></i>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: "FuiAlexaNavbar",
  props: {
    title: {
      type: String,
      default: 'Darwin',
    },
    items: {
      type: [Array, Object],
      default: () => [
        {title: "Home", icon: "uil uil-estate", route: "#home", isActive: true},
        {title: "About", icon: "uil uil-user", route: "#about"},
        {title: "Skills", icon: "uil uil-file-alt", route: "#skills"},
        {title: "Services", icon: "uil uil-briefcase-alt", route: "#services"},
        {title: "Portfolio", icon: "uil uil-scenery", route: "#portfolio"},
        {title: "Contact", icon: "uil uil-message", route: "#contactMe"},
      ]
    }
  },
  data: () => ({
    showMenu: false,
  }),
  methods: {
    handleToggle() {
      this.showMenu = !this.showMenu;
    },
    scrollActive() {
      const sections = document.querySelectorAll('section[id]')
      const scrollY = window.pageYOffset
      sections.forEach(current => {
        const sectionHeight = current.offsetHeight
        const sectionTop = current.offsetTop - 50;
        const sectionId = current.getAttribute('id')

        if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
          document.querySelector(`.nav__menu a[href*='${sectionId}']`)?.classList.add('active-link')
        } else {
          document.querySelector(`.nav__menu a[href*='${sectionId}']`)?.classList.remove('active-link')
        }
      })
    },
    scrollHeader() {
      const nav = document.getElementById('header')
      if (window.pageYOffset >= 80) nav?.classList.add('scroll-header'); else nav?.classList.remove('scroll-header');
    },
    themeButtonHandler() {
      const themeButton = document.getElementById('theme-button')
      const darkTheme = 'dark-theme', iconTheme = 'uil-sun'
      document.body.classList.toggle(darkTheme)
      themeButton?.classList.toggle(iconTheme)

      const getCurrentTheme = () => document.body.classList.contains(darkTheme) ? 'dark' : 'light'
      const getCurrentIcon = () => themeButton?.classList.contains(iconTheme) ? 'uil-moon' : 'uil-sun'

      localStorage.setItem('selected-theme', getCurrentTheme())
      localStorage.setItem('selected-icon', getCurrentIcon())
    },
    themeSetup() {
      const themeButton = document.getElementById('theme-button')
      const darkTheme = 'dark-theme', iconTheme = 'uil-sun'

      const selectedTheme = localStorage.getItem('selected-theme')
      const selectedIcon = localStorage.getItem('selected-icon')

      if (selectedTheme) {
        document.body.classList[selectedTheme === 'dark' ? 'add' : 'remove'](darkTheme)
        themeButton?.classList[selectedIcon === 'uil-moon' ? 'add' : 'remove'](iconTheme)
      }
    }
  },
  mounted() {
    window.addEventListener('scroll', this.scrollActive)
    window.addEventListener('scroll', this.scrollHeader)
    this.themeSetup()
  }
};
</script>
