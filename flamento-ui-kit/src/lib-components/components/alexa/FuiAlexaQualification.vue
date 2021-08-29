<template>
  <!-- Qualifications -->
  <section class="qualification section fui__alexa">
    <h2 class="section__title"><slot name="title">{{title}}</slot></h2>
    <span class="section__subtitle"><slot name="subtitle">{{subTitle}}</slot></span>

    <div class="qualification__container container">
      <div class="qualification__tabs">
        <div
            v-for="(item,idx) in items"
            class="qualification__button button--flex"
             :class="{ 'qualification__active':target === idx}"
             @click="target = idx">
          <i class="uil uil-graduation-cap qualification__icon"></i>
          {{item.title}}
        </div>
      </div>

      <div class="qualification__sections">
        <!-- Qualification Content 1 -->
        <div
            v-for="(item, idx) in items"
            data-content
            :id="idx"
            class="qualification__content"
            data-target
            :class="{ 'qualification__active':target === idx}"
        >
          <!-- Qualification Item 1 -->
          <div
              v-for="(set,setIdx) in item.sets"
              class="qualification__data">
            <div v-if="setIdx % 2 === 1"></div>
            <!-- Alternate Splitter -->
            <div v-if="setIdx % 2 === 1">
              <span class="qualification__rounder"></span>
              <span v-if="setIdx !== item.sets.length-1"  class="qualification__line"></span>
            </div>

            <div>
              <h3 class="qualification__title" v-html="set.title"></h3>
              <span class="qualification__subtitle" v-html="set.subtitle"></span>
              <div class="qualification__calendar">
                <i class="uil uil-calendar-alt"></i>
                {{set.date}}
              </div>
            </div>

            <!-- Alternate Splitter -->
            <div v-if="setIdx % 2 === 0">
              <span class="qualification__rounder"></span>
              <span v-if="setIdx !== item.sets.length-1" class="qualification__line"></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FuiAlexaQualification",
  props: {
    title: {
      type: String,
      default: 'qualification',
    },
    subTitle: {
      type: String,
      default: 'My personal journey',
    },
    items: {
      type: Array,
      default: () => [
        {
          title: 'Education',
          sets: [
            {title: 'Education Test Data 1', subtitle: 'School Test Data', date: '2021 - 2032'},
            {title: 'Education Test Data 2', subtitle: 'School Test Data II', date: '2009 - 2000'},
            {title: 'Education Test Data 3', subtitle: 'School Test Data IIV', date: '2003 - 2014'},
          ]
        },
        {
          title: 'Work',
          sets: [
            {title: 'Work Test Data I', subtitle: 'Work Location Data.', date: '2001 - 2034'},
            {title: 'Work Test Data II', subtitle: 'Work Location Data.', date: '2009 - 2012'},
            {title: 'Work Test Data IVI', subtitle: 'Work Location Data.', date: '1993 - 1983'},
            {title: 'Work Test Data V', subtitle: 'Work Location Data.', date: '1899 - 1999'},
          ]
        },
      ],
    },
  },
  data: () => ({
    target: 0
  })
}
</script>