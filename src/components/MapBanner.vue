<script>
import { defineComponent } from "vue";
import { GoogleMap, Marker } from "vue3-google-map";

export default defineComponent({
  components: { GoogleMap, Marker },
  setup() {
    const center = { lat: 51.50821928236727, lng: -0.12815008330849517 };

    return { center };
  },
});
</script>
<template>
  <div class="container-fluid">
    <GoogleMap
      api-key="AIzaSyC3p3OkGqxXpXnrH1zdQE6H0CvtuRU1ceU
      "
      style="width: 100%; height: 400px"
      :center="center"
      :zoom="14"
    >
      <Marker :options="{ position: center }" />
    </GoogleMap>
  </div>
</template>

<style lang="scss" scoped></style>
