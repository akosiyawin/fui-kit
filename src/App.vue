<template>
  <div id="app">
    <fui-alexa-footer></fui-alexa-footer>
<!--    <fui-alexa></fui-alexa>-->
  </div>
</template>

<script>
import FuiAlexa from "./examples/FuiAlexa";
import {FuiAlexaFooter} from "../index";
export default {
  name: "App",
  components: {
    FuiAlexa,
    FuiAlexaFooter
  },
};
</script>
