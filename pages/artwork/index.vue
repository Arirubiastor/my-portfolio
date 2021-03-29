<template>
  <div>
    <MainCatalogue :images="projectsData" />
    <Pagination :images="projectsData" />
    
    <!-- <GitHubRepos :repositoriesData="repos" :bgColorsData="colors" /> -->
    <!-- {{ projectsData }} -->
  </div>
</template>

<script>
import MainCatalogue from "~/components/MainCatalogue.vue";

import Vue from "vue";
import { BootstrapVue, BootstrapVueIcons } from "bootstrap-vue";

Vue.use(BootstrapVue);
Vue.use(BootstrapVueIcons);

export default {
  layout: 'artwork',
  components: {
    MainCatalogue,
  },
  data() {
    return {
      projectsData: [
        {
          name: "Mertraco Company's Website Redesign",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/mertraco-desktop.JPG",
          siteUrl: "https://www.mertraco.com/",
        },
        {
          name: "Exikhan Company's Website",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/exikhan-desktop.JPG",
          siteUrl: "https://www.exikhan.com/",
        },
        {
          name: "Outscape Map Collaboration Web Application",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/outscape-desktop.JPG",
          siteUrl: "https://outscape-community.herokuapp.com/",
        },
        {
          name: "Track and Trace Web application",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/customer-dashboard-desktop.JPG",
          siteUrl:
            "https://development.dd12vh11stjdb.amplifyapp.com/booking-details",
        },
        {
          name: "Newsletter for an ERP",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/newsletter-desktop.png",
          siteUrl: "https://tms.schryver.com/",
        },
        {
          name: "My Portfolio Web Site",
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/my-portfolio-desktop.JPG",
          siteUrl: "https://www.arianarubi.com/",
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


