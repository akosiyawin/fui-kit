<script>
import Vue from 'vue';
import FlamentoUiKitSample from "../src/lib-components/flamento-ui-kit-sample";
// Uncomment import and local "components" registration if library is not registered globally.
// import { FlamentoUiKitSample } from '@/entry.esm';

export default Vue.extend({
  name: 'ServeDev',
  components: {FlamentoUiKitSample},
  // components: {
  //  FlamentoUiKitSample,
  // }
});
</script>

<template>
  <div id="app">
    <flamento-ui-kit-sample />
  </div>
</template>
