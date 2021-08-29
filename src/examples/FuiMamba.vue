<template>
  <fui-mamba-app>
    <fui-mamba-navbar></fui-mamba-navbar>
    <fui-mamba-home></fui-mamba-home>
    <fui-mamba-sponsor></fui-mamba-sponsor>
    <fui-mamba-specs></fui-mamba-specs>
    <fui-mamba-case></fui-mamba-case>
    <fui-mamba-discount></fui-mamba-discount>
    <fui-mamba-products></fui-mamba-products>
    <fui-mamba-footer></fui-mamba-footer>
    <fui-mamba-scroll-up></fui-mamba-scroll-up>
    <fui-mamba-scroll-reveal></fui-mamba-scroll-reveal>
    <fui-mamba-scrollbar-theme></fui-mamba-scrollbar-theme>
    <fui-mamba-theme></fui-mamba-theme>

  </fui-mamba-app>
</template>

<script>
import FuiMambaApp from "../components/mamba/FuiMambaApp";
import FuiMambaNavbar from "../components/mamba/FuiMambaNavbar";
import FuiMambaHome from "../components/mamba/FuiMambaHome";
import FuiMambaSponsor from "../components/mamba/FuiMambaSponsor";
import FuiMambaSpecs from "../components/mamba/FuiMambaSpecs";
import FuiMambaCase from "../components/mamba/FuiMambaCase";
import FuiMambaDiscount from "../components/mamba/FuiMambaDiscount";
import FuiMambaProducts from "../components/mamba/FuiMambaProducts";
import FuiMambaFooter from "../components/mamba/FuiMambaFooter";
import FuiMambaScrollUp from "../components/mamba/FuiMambaScrollUp";
import FuiMambaScrollReveal from "../components/mamba/FuiMambaScrollReveal";
import FuiMambaScrollbarTheme from "../components/mamba/FuiMambaScrollbarTheme";
import FuiMambaTheme from "../components/mamba/FuiMambaTheme";
export default {
  name: "FuiMamba",
  components: {
    FuiMambaTheme,
    FuiMambaScrollbarTheme,
    FuiMambaScrollReveal,
    FuiMambaScrollUp,
    FuiMambaFooter,
    FuiMambaProducts,
    FuiMambaDiscount,
    FuiMambaCase,
    FuiMambaSpecs,
    FuiMambaSponsor,
    FuiMambaHome,
    FuiMambaNavbar,
    FuiMambaApp
  }
}
</script>

<style scoped>

</style>