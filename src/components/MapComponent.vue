<template>
  <div>
    <div id="map"></div>
  </div>
</template>

<script>
import L from "leaflet";
export default {
  name: "MapComponent",
  data: () => ({
    map: null,
    tileLayer: null,
    layers: [
      {
        id: 0,
        name: "Restaurante",
        active: false,
        features: [],
      },
    ],
  }),
  mounted() {
    this.initMap();
    // this.initLayers();
  },
  methods: {
    initMap() {
      this.map = L.map("map").setView([-25.46033726712044, -49.29804536309487], 13);
      this.tileLayer = L.tileLayer('https://{s}.tile.openstreetmap.fr/hot/{z}/{x}/{y}.png', {
        maxZoom: 18,
        attribution:
          '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, Tiles style by <a href="https://www.hotosm.org/" target="_blank">Humanitarian OpenStreetMap Team</a> hosted by <a href="https://openstreetmap.fr/" target="_blank">OpenStreetMap France</a>',
      });
      this.tileLayer.addTo(this.map);
    },
  },
};
</script>

<style scoped>
#map {
  width: 80vw;
  height: 100vh;
}
</style>
