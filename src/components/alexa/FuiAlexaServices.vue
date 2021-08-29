<template>
  <section class="services section fui__alexa" id="services">
    <h2 class="section__title"><slot name="title">{{title}}</slot></h2>
    <span class="section__subtitle"><slot name="subtitle">{{subTitle}}</slot></span>

    <div class="services__container container grid">
      <!--      service 1-->
      <div
          v-for="(item,idx) in items"
          class="services__content">
        <div>
          <i class="uil services__icon" :class="item.icon"></i>
          <h3 class="services__title" v-html="item.title"></h3>
        </div>
        <span
            v-if="item.items && item.items.length > 0"
            @click="target = idx"
            class="button button--flex button--small button--link services__button">
          View More
          <i class="uil uil-arrow-right button__icon"></i>
        </span>

        <div
            :class="{'active-modal' : target === idx}"
            class="services__modal">
          <div class="services__modal-content">
            <h4 class="services__modal-title" v-html="item.title"></h4>
            <i @click="target = ''" class="uil uil-times services__modal-close"></i>

            <ul class="services__modal-services grid">
              <li
                  v-for="set in item.items"
                  class="services__modal-service">
                <i class="uil uil-check-circle services__modal-icon"></i>
                <p v-html="set"></p>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FuiAlexaServices",
  props: {
    title: {
      type: String,
      default: 'services',
    },
    subTitle: {
      type: String,
      default: 'What i offer',
    },
    items: {
      type: Array,
      default: () => [
        {
          icon: 'uil-web-grid',
          title: 'Ui/Ux <br> Designer',
          items: [
              'Describe something about this service.',
              'Sample Items For This Service.',
              'Sample Items For This Service.',
              'Sample Items For This Service.',
              'Sample Items For This Service.',
              'Sample Items For This Service.',
          ],
        },
        {
          icon: 'uil-arrow',
          title: 'Frontend <br> Developer',
          items: [
            'Describe something about this service II.',
            'Sample Items For This Service.',
            'Sample Items For This Service.',
            'Sample Items For This Service.',
            'Sample Items For This Service.',
            'Sample Items For This Service.',
          ],
        },
        {
          icon: 'uil-pen',
          title: 'Brand <br> Designer',
          items: [
            'Describe something about this service III.',
            'Sample Items For This Service.',
            'Sample Items For This Service.',
            'Sample Items For This Service.',
            'Sample Items For This Service.',
            'Sample Items For This Service.',
          ],
        },
      ]
    }
  },
  data: () => ({
    target: ''
  })
}
</script>
