<script>
import { store } from "./store";

// COMPONENTS
import AppHeader from "./components/AppHeader.vue";
import Jumbotron from "./components/Jumbotron.vue";
import AboutUs from "./components/AboutUs.vue";
import BannerCountDown from "./components/BannerCountDown.vue";
import SpeakersSlider from "./components/SpeakersSlider.vue";
import EventsJournal from "./components/EventsJournal.vue";
import LocationBanner from "./components/LocationBanner.vue";
import NewsSection from "./components/NewsSection.vue";
import Tickets from "./components/Tickets.vue";
import PromoSection from "./components/PromoSection.vue";
import Sponsors from "./components/Sponsors.vue";
import AppFooter from "./components/AppFooter.vue";
import MapBanner from "./components/MapBanner.vue";

export default {
  components: {
    AppHeader,
    Jumbotron,
    AboutUs,
    BannerCountDown,
    SpeakersSlider,
    EventsJournal,
    MapBanner,
    LocationBanner,
    NewsSection,
    Tickets,
    PromoSection,
    Sponsors,
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
  <main>
    <Jumbotron></Jumbotron>
    <AboutUs></AboutUs>
    <BannerCountDown></BannerCountDown>
    <SpeakersSlider></SpeakersSlider>
    <EventsJournal></EventsJournal>
    <MapBanner></MapBanner>
    <LocationBanner></LocationBanner>
    <NewsSection></NewsSection>
    <Tickets></Tickets>
    <PromoSection></PromoSection>
    <Sponsors></Sponsors>
  </main>
  <AppFooter></AppFooter>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
