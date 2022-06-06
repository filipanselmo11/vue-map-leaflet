<template>
  <v-app>
    <v-main>
      <map-component></map-component>
    </v-main>
  </v-app>
</template>

<script>
import MapComponent from "./components/MapComponent.vue";

export default {
  name: "App",

  components: {
    MapComponent,
  },

  data: () => ({
    //
  }),
};
</script>
