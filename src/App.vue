<script>
import AppHeader from './components/AppHeader.vue';
import AppContent from "./components/AppContent.vue";
import AppFooter from "./components/AppFooter.vue";

  export default {
    components: {
    AppHeader,
    AppContent,
    AppFooter
    },
    data() {
      return {
      }
    }
  }
</script>

<template>
  
  <AppHeader />
  <AppContent />
  <AppFooter />

</template>

<style lang="scss">
  @use "./style/general.scss";

</style>
