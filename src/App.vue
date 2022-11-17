<script>
import { store } from "./store";
// COMPONENTS
import AppHeader from "./components/AppHeader.vue";
import Jumbotron from "./components/Jumbotron.vue";
import AboutUs from "./components/AboutUs.vue";
import BannerCountDown from "./components/BannerCountDown.vue";
import SpeakersSlider from "./components/SpeakersSlider.vue";
import EventsJournal from "./components/EventsJournal.vue";
import AppFooter from "./components/AppFooter.vue";

export default {
  components: {
    AppHeader,
    Jumbotron,
    AboutUs,
    BannerCountDown,
    SpeakersSlider,
    EventsJournal,
    AppFooter,
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
  <EventsJournal></EventsJournal>
  <AppFooter></AppFooter>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
