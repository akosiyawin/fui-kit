<template>
  <section class="portfolio section fui__alexa" id="portfolio">
    <h2 class="section__title"><slot name="title">{{title}}</slot></h2>
    <span class="section__subtitle"><slot name="subtitle">{{subTitle}}</slot></span>

    <div class="portfolio__container container swiper swiper-container">
      <div class="swiper-wrapper">
        <!-- Portfolio 1-->
        <div
            v-for="item in items"
            class="portfolio__content grid swiper-slide">
          <img
              :src="item.imageUrl"
              alt="portfolio_image" class="portfolio__img">
          <div class="portfolio__data">
            <h3 class="portfolio__title" v-html="item.title"></h3>
            <p class="portfolio__description" v-html="item.description"></p>
            <a :href="item.demoUrl" class="button button--flex button--small portfolio__button">
              Demo <i class="uil uil-arrow-right button__icon"></i>
            </a>
          </div>
        </div>
      </div>

      <div class="swiper-button-next">
        <i class="uil uil-angle-right-b swiper-portfolio-icon"></i>
      </div>
      <div class="swiper-button-prev">
        <i class="uil uil-angle-left-b swiper-portfolio-icon"></i>
      </div>
      <div class="swiper-pagination"></div>
    </div>


  </section>
</template>

<script>
import Swiper from 'swiper/swiper-bundle.min.js';

export default {
  name: "FuiAlexaPortfolio",
  props: {
    title: {
      type: String,
      default: 'portfolio',
    },
    subTitle: {
      type: String,
      default: 'Most recent work',
    },
    items: {
      type:Array,
      default: () => [
        {imageUrl: 'https://raw.githubusercontent.com/bedimcode/responsive-portfolio-website-Alexa/main/assets/img/portfolio1.jpg', title: 'Modern Website', description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus aliquid error facere molestiae nostrum officia quo repudiandae sint.', demoUrl: '#'},
        {imageUrl: 'https://raw.githubusercontent.com/bedimcode/responsive-portfolio-website-Alexa/main/assets/img/portfolio2.jpg', title: 'Online Store', description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus aliquid error facere molestiae nostrum officia quo repudiandae sint.', demoUrl: '#'},
        {imageUrl: 'https://raw.githubusercontent.com/bedimcode/responsive-portfolio-website-Alexa/main/assets/img/portfolio3.jpg', title: 'Flamento Framework', description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus aliquid error facere molestiae nostrum officia quo repudiandae sint.', demoUrl: '#'},
      ]
    }
  },
  mounted() {
    const swiper = new Swiper(".portfolio__container", {
      cssMode: true,
      loop: true,
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
      pagination: {
        el: ".swiper-pagination",
        clickable: true,
      },
    });
  }
}
</script>

<style scoped>
@import '~swiper/swiper-bundle.min.css';
.portfolio__container {
  overflow: initial;
  padding: 0 15px;
}

.portfolio__content {
  padding: 0 1.5rem;
}

.portfolio__img {
  width: 265px;
  border-radius: .5rem;
  justify-self: center;
}

.portfolio__title {
  font-size: var(--h3-font-size);
  margin-bottom: var(--mb-0-5);
}

.portfolio__description {
  margin-bottom: var(--mb-0-75);
}

.portfolio__button:hover .button__icon {
  transform: translateX(.25rem);
}

.swiper-button-prev::after, .swiper-button-next::after {
  content: '';
}

.swiper-portfolio-icon {
  font-size: 2rem;
  color: var(--first-color);
}

.swiper-pagination-bullets {
  bottom: -2.5rem;
}

/*for medium devices*/
@media screen and (min-width: 568px) {
  .portfolio__content {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (min-width: 768px) {
  .portfolio__img {
    width: 320px;
  }

  .portfolio__content {
    align-items: center;
  }

  .swiper-button-prev {
    left: -1rem;
  }

  .swiper-button-next {
    right: -1rem;
  }
}

@media screen and (min-width: 1024px) {
  .portfolio__content {
    column-gap: 5rem;
  }

  .swiper-portfolio-icon {
    font-size: 3.5rem;
  }

  .swiper-button-prev {
    left: -3.5rem;
  }

  .swiper-button-next {
    right: -3.5rem;
  }

  .swiper-pagination-bullets {
    bottom: -4.5rem;
  }
}
</style>

<style>
.swiper-pagination-bullet-active {
  background-color: var(--first-color);
}

.swiper-button-prev,
.swiper-button-next,
.swiper-pagination-bullet {
  outline: none;
}
</style>