<script>
import { store } from "./store";
// COMPONENTS
import AppHeader from "./components/AppHeader.vue";
import Jumbotron from "./components/Jumbotron.vue";
import AboutUs from "./components/AboutUs.vue";
export default {
  components: {
    AppHeader,
    Jumbotron,
    AboutUs,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <AppHeader></AppHeader>
  <Jumbotron></Jumbotron>
  <AboutUs></AboutUs>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
