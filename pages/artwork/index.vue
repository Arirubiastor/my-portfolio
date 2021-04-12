<template>
  <div>
    <MainCatalogue :images="projectsData" />
    <ArtworkCataloge :images="projectsData" />
  </div>
</template>

<script>
import ArtworkCataloge from "~/components/ArtworkCataloge.vue";

import Vue from "vue";
import { BootstrapVue, BootstrapVueIcons } from "bootstrap-vue";

Vue.use(BootstrapVue);
Vue.use(BootstrapVueIcons);

export default {
  layout: 'artwork',
  components: {
    ArtworkCataloge,
  },
  data() {
    return {
      projectsData: [
        {
          title: "Self-portrait",
          year: "2017",
          medium: "bordado sobre tela montado en bastidor de madera",
          measuresCm: "40cm x 60cm x 5cm",
          measuresIn: "15in x 27in x 1.5in",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/artwork-cataloge/IMG_6343.JPG",
          instaUrl: "https://www.instagram.com/ariana.rubii/",
        },
        {
          title: "Duality",
          year: "2018",
          medium: "bordado sobre tela montado en bastidor de madera",
          measuresCm: "40cm x 60cm x 5cm",
          measuresIn: "15in x 27in x 1.5in",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/artwork-cataloge/DSC_0175.JPG",
          instaUrl: "https://www.instagram.com/ariana.rubii/",
        },
        {
          title: "Saltponds",
          year: "2019",
           medium: "acrílico y tierra sobre tela montado en bastidor de madera",
          measuresCm: "70cm x 160cm x 5cm",
          measuresIn: "45in x 79in x 1.5in",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/artwork-cataloge/IMG_6590.JPG",
          instaUrl: "https://www.instagram.com/ariana.rubii/",
        },
      ],
    };
  },
  methods: {

  },

  async mounted() {
    // this.instagramMediaItem();
  },
};

// Actualizar token c/2 meses aquí: https://developers.facebook.com/docs/instagram-basic-display-api/guides/long-lived-access-tokens
</script>

<style lang="scss">
</style>


