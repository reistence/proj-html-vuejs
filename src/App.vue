<script>
import { store } from "./store";
// COMPONENTS
import AppHeader from "./components/AppHeader.vue";
import Jumbotron from "./components/Jumbotron.vue";
import AboutUs from "./components/AboutUs.vue";
import BannerCountDown from "./components/BannerCountDown.vue";
import SpeakersSlider from "./components/SpeakersSlider.vue";

export default {
  components: {
    AppHeader,
    Jumbotron,
    AboutUs,
    BannerCountDown,
    SpeakersSlider,
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
  <BannerCountDown></BannerCountDown>
  <SpeakersSlider></SpeakersSlider>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
