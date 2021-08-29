<template>
  <section class="testimonial section fui__alexa">
    <h2 class="section__title"><slot name="title">{{title}}</slot></h2>
    <span class="section__subtitle"><slot name="subtitle">{{subTitle}}</slot></span>
    
    <div class="testimonial__container container swiper-container swiper">
      <div class="swiper-wrapper">
        <!--Content 1-->
        <div
            v-for="item in items"
            class="swiper-slide testimonial__content">
          <div class="testimonial__data">
            <div class="testimonial__header">
              <img :src="item.imgSrc" alt="testimonial_img" class="testimonial__img">
              <div>
                <h3 class="testimonial__name" v-html="item.name"></h3>
                <span class="testimonial__client" v-html="item.type"></span>
              </div>
            </div>

            <div>
              <i v-for="i in item.ratings" class="uil uil-star testimonial__icon-star"></i>
            </div>
          </div>
          <p class="testimonial__description" v-html="item.description"></p>
        </div>
      </div>
      <div class="swiper-pagination swiper-pagination-testimonial"></div>
    </div>
  </section>
</template>

<script>
import Swiper from "swiper/swiper-bundle.min";

export default {
  name: "FuiAlexaTestimonial",
  props: {
    title: {
      type: String,
      default: 'testimonial',
    },
    subTitle: {
      type: String,
      default: 'My client feedback',
    },
    items: {
      type: Array,
      default: () => [
        {
          imgSrc: 'https://raw.githubusercontent.com/bedimcode/responsive-portfolio-website-Alexa/main/assets/img/testimonial1.jpg',
          name: 'Sara Smith',
          type: 'Client',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam beatae dolor dolores eum ipsam officia quam quibusdam recusandae sequi vitae.',
          ratings: 5,
        },
        {
          imgSrc: 'https://raw.githubusercontent.com/bedimcode/responsive-portfolio-website-Alexa/main/assets/img/testimonial2.jpg',
          name: 'John Doe',
          type: 'Engineer',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam beatae dolor dolores eum ipsam officia quam quibusdam recusandae sequi vitae.',
          ratings: 4,
        },
        {
          imgSrc: 'https://raw.githubusercontent.com/bedimcode/responsive-portfolio-website-Alexa/main/assets/img/testimonial3.jpg',
          name: 'Dr. Farah Port',
          type: 'Doctor',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam beatae dolor dolores eum ipsam officia quam quibusdam recusandae sequi vitae.',
          ratings: 3,
        },
      ]
    }
  },
  mounted() {
    const swiper = new Swiper(".testimonial__container", {
      loop:true,
      grabCursor: true,
      spaceBetween: 48,
      pagination: {
        el: ".swiper-pagination",
        clickable: true,
        dynamicBullets: true,
      },
      breakpoints: {
        568: {
          slidesPerView: 2,
        }
      }
    });
  }
}
</script>

<style scoped>

</style>