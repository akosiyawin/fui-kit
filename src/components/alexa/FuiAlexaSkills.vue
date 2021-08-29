<template>
  <!-- Skills -->
  <section class="skill section fui__alexa" id="skills">
    <h2 class="section__title">
      <slot name="title">{{ title }}</slot>
    </h2>
    <span class="section__subtitle"><slot name="subtitle">{{ subTitle }}</slot></span>
    <div class="skills__container container grid">
      <!-- SKills -->
      <div
          v-for="(skill, idx) in skills"
          :key="skill.title"
          class="skills__content"
          :class="{ skills__open: selectedSkill === idx }"
      >
        <div class="skills__header" @click="handleToggle(idx)">
          <i class="uil skills__icon" :class="skill.prefixIcon"> </i>
          <div>
            <h1 class="skills__titles">{{ skill.title }}</h1>
            <span class="skills__subtitle">{{ skill.subTitle }}</span>
          </div>
          <i class="uil uil-angle-down skills__arrow"> </i>
        </div>
        <div class="skills__list grid">
          <div
              v-for="(set, idx) in skill.sets"
              :key="skill.title + idx"
              class="skills__data"
          >
            <div class="skills__titles">
              <h3 class="skills__name">{{ set.title }}</h3>
              <span class="skills__number">{{ set.percentage }}</span>
            </div>
            <div class="skills__bar">
                <span
                    class="skills__percentage"
                    :style="{ width: set.percentage }"
                ></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FuiAlexaSkills",
  props: {
    title: {
      type: String,
      default: 'skills',
    },
    subTitle: {
      type: String,
      default: 'My technical level',
    },
    skills: {
      type: Array,
      default: () => [
        {
          title: "Frontend developer",
          subTitle: "More than 4 years",
          prefixIcon: "uil uil-brackets-curly",
          sets: [
            {title: "HTML", percentage: "100%"},
            {title: "CSS", percentage: "80%"},
            {title: "Javascript", percentage: "90%"},
            {title: "Vue", percentage: "90%"},
          ],
        },
        {
          title: "Backend developer",
          subTitle: "More than 4 years",
          prefixIcon: "uil uil-server-connection",
          sets: [
            {title: "HTML", percentage: "100%"},
            {title: "CSS", percentage: "80%"},
            {title: "Javascript", percentage: "90%"},
            {title: "Vue", percentage: "90%"},
          ],
        },
        {
          title: "Designer",
          subTitle: "More than 2 years",
          prefixIcon: "uil uil-swatchbook",
          sets: [
            {title: "HTML", percentage: "100%"},
            {title: "CSS", percentage: "80%"},
            {title: "Javascript", percentage: "90%"},
            {title: "Vue", percentage: "90%"},
          ],
        },
      ],
    },
  },
  data: () => ({
    selectedSkill: "",
  }),
  methods: {
    handleToggle(idx) {
      if (this.selectedSkill === idx) {
        this.selectedSkill = "";
      } else {
        this.selectedSkill = idx;
      }
    },
  },
};
</script>