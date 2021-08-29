<script>
import {
  FuiAlexaFooter,
  FuiAlexaContact,
  FuiAlexaTestimonial,
  FuiAlexaProject,
  FuiAlexaPortfolio,
  FuiAlexaServices,
  FuiAlexaQualification,
  FuiAlexaSkills,
  FuiAlexaAbout,
  FuiAlexaHome,
  FuiAlexaNavbar,
  FuiAlexaApp
} from "../index.js";
import FuiAlexaScrollbarTheme from "../components/alexa/FuiAlexaScrollbarTheme";
import FuiAlexaTheme from "../components/alexa/FuiAlexaTheme";
export default {
  name: "FuiAlexa",
  components: {
    FuiAlexaTheme,
    FuiAlexaScrollbarTheme,
    FuiAlexaFooter,
    FuiAlexaContact,
    FuiAlexaTestimonial,
    FuiAlexaProject,
    FuiAlexaPortfolio,
    FuiAlexaServices,
    FuiAlexaQualification,
    FuiAlexaSkills,
    FuiAlexaAbout,
    FuiAlexaHome,
    FuiAlexaNavbar,
    FuiAlexaApp},
}
</script>
<template>
  <div id="app">
    <fui-alexa-app>
      <fui-alexa-navbar></fui-alexa-navbar>
      <fui-alexa-home></fui-alexa-home>
      <fui-alexa-about></fui-alexa-about>
      <fui-alexa-skills></fui-alexa-skills>
      <fui-alexa-qualification></fui-alexa-qualification>
      <fui-alexa-services></fui-alexa-services>
      <fui-alexa-portfolio></fui-alexa-portfolio>
      <fui-alexa-project></fui-alexa-project>
      <fui-alexa-testimonial></fui-alexa-testimonial>
      <fui-alexa-contact></fui-alexa-contact>
      <fui-alexa-footer></fui-alexa-footer>
      <fui-alexa-scrollbar-theme></fui-alexa-scrollbar-theme>
      <fui-alexa-theme></fui-alexa-theme>
    </fui-alexa-app>
  </div>
</template>
