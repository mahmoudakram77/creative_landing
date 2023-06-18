<template>
  <div class="container container-fluid position-relative">
    <h1 class="text-center mb-5">contact</h1>
    <div class="row">
      <div class="col-lg-6 col-sm-12 map">
        <GoogleMap
          class="map"
          api-key="AIzaSyAFFimCzkGv0IIksWPhsKIpjbIAIFeLJlw"
          :center="center"
          :zoom="15"
        >
          <Marker :options="{ region: 'PS' }" />
        </GoogleMap>
      </div>
      <div class="col-lg-6 col-sm-12 content">
        <h1>contact details</h1>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam, at.
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import { GoogleMap, Marker } from "vue3-google-map";

export default defineComponent({
  components: { GoogleMap, Marker },
  setup() {
    const center = { lat: 31.5017, lng: 34.4669 };

    return { center };
  },
});
</script>

<style scoped>
.map {
  width: 650px;
  height: 500px;
}
.container {
}
.content {
  width: 650px;
  height: 500px;
  text-align: center;
  margin: 0 auto;
}
.map {
  margin: 0 auto;
}
@media screen and (max-width: 576px) {
  .map {
    width: 400px;
    height: 400px;
    margin: 0 auto;
  }
}
@media screen and (max-width: 400px) {
  .map {
    width: 350px;
    height: 350px;
    margin: 0 auto;
  }
}
@media screen and (max-width: 361px) {
  .map {
    width: 300px;
    height: 300px;
    margin: 0 auto;
  }
}
@media screen and (max-width: 361px) {
  .map {
    width: 300px;
    height: 300px;
    margin: 0 auto;
  }
}
@media screen and (max-width: 312px) {
  .map {
    width: 270px;
    height: 270px;
    margin: 0 auto;
  }
}
</style>
576 312
