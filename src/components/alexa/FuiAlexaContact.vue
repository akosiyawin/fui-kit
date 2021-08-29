<template>
  <section class="contact section fui__alexa" id="contactMe">
    <h2 class="section__title"><slot name="title">{{title}}</slot></h2>
    <span class="section__subtitle"><slot name="subtitle">{{subTitle}}</slot></span>

    <div class="contact__container container grid">
      <div>
        <div class="contact__information">
          <i class="uil uil-phone contact__icon"></i>
          <div>
            <h3 class="contact__title">Call Me</h3>
            <span class="contact__subtitle"><slot name="contact">{{contact}}</slot></span>
          </div>
        </div>
        <div class="contact__information">
          <i class="uil uil-envelope contact__icon"></i>
          <div>
            <h3 class="contact__title">Email</h3>
            <span class="contact__subtitle"><slot name="email">{{email}}</slot></span>
          </div>
        </div>
        <div class="contact__information">
          <i class="uil uil-map-marker contact__icon"></i>
          <div>
            <h3 class="contact__title">Location</h3>
            <span class="contact__subtitle"><slot name="location">{{location}}</slot></span>
          </div>
        </div>
      </div>

      <form :action="'https://formsubmit.co/'+email" method="POST" class="contact__form grid">
        <div class="contact__inputs grid">
          <div class="contact__content">
            <label for="" class="contact__label">Name</label>
            <input name="name" type="text" class="contact__input" required>
          </div>
          <div class="contact__content">
            <label for="" class="contact__label">Email</label>
            <input name="email" type="email" class="contact__input" required>
          </div>
        </div>
        <div class="contact__content">
          <label for="" class="contact__label">Project</label>
          <input name="project" type="text" class="contact__input" required>
        </div>
        <div class="contact__content">
          <label for="" class="contact__label">Message</label>
          <textarea name="message" id="" cols="0" rows="7" class="contact__input" required></textarea>
        </div>
        <div>
          <button style="outline: none; border-width: 0; cursor:pointer; font-weight: 500; font-family: 'Poppins',serif" class="button button--flex">
            Send Message
            <i class="uil uil-message button__icon"></i>
          </button>
        </div>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: "FuiAlexaContact",
  props: {
    title: {
      type: String,
      default: 'contact me',
    },
    subTitle: {
      type: String,
      default: 'Get in touch',
    },
    contact: {
      type: String,
      default: '999-777-666',
    },
    email: {
      type: String,
      default: 'j.doe@email.com',
    },
    location: {
      type: String,
      default: 'Philippines - Imelda Samal, Bataan',
    },
  }
}
</script>