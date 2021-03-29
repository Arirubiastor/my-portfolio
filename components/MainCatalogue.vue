<template>
  <b-container fluid class="p-0">
    <!-- <b-row v-for="image in images" :key="image"> -->
      <b-row>
      <!-- <b-col>
        <b-img :src="image.imageUrl"></b-img>
      </b-col> -->
      <b-col>
        <!-- <Pagination :images="images" /> -->
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Vue from "vue";
import { BootstrapVue, BootstrapVueIcons } from "bootstrap-vue";

Vue.use(BootstrapVue);
Vue.use(BootstrapVueIcons);

export default {
  props: {
    images: {
      type: Array,
      required: true,
    }
  },
};
</script>

<style lang="scss">
.index-tabs {
  height: calc(100vh - 80px);
  // border-top: 1.5px gray solid;
}

.border-top {
  border-top: 1.5px gray solid !important;
}

// .tab-content {
//   border-right: 1.5px gray solid;
// }

.tab-title {
  border-top: 1.5px gray solid;
  border-bottom: 1.5px gray solid;
}

.col-auto {
  width: 12rem;
  // max-width: 100%;

  .card-header {
    padding: 0;
  }

  li {
    height: 20%;

    .nav-link {
      height: 100%;
      display: flex;
      justify-content: center;
      // align-items: center;
      border-radius: 0;
      padding: 0;
    }
    // .nav-link.active {
    //   color: #343a40; // gray-800
    // }
  }
}
// Mobile first Responsive design
@media (min-width: 960px) {
  .col-auto {
    width: 15rem;
  }
}
@media (min-width: 1140px) {
  .col-auto {
    width: 20rem;
  }
}
</style>