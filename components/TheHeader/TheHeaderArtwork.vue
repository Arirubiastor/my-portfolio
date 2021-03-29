<template>
  <div class="the-header border d-flex flex-column justify-content-center">
    <b-navbar
      fixed="top"
      toggleable="lg"
      variant="transparent"
      class="px-3 px-md-5"
    >
      <TheProfileSidebar />

      <div class="d-flex">
        <b-button v-b-toggle.sidebar-right>
          <b-icon icon="three-dots-vertical" variant="success"></b-icon>
        </b-button>
        <b-sidebar id="sidebar-right" title="Sidebar" right shadow>
          <div class="px-3 py-2">
            <p>
              Cras mattis consectetur purus sit amet fermentum. Cras justo odio,
              dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta
              ac consectetur ac, vestibulum at eros.
            </p>
            <b-img
              src="https://picsum.photos/500/500/?image=54"
              fluid
              thumbnail
            ></b-img>
          </div>
        </b-sidebar>

        <b-nav class="d-flex flex-row justify-content-between">
          <!-- <b-navbar-brand>ariana rubí</b-navbar-brand> -->
          <b-nav-item to="/" class="mr-0">menu</b-nav-item>
        </b-nav>
      </div>
    </b-navbar>
  </div>
</template>

<script>
import TheProfileSidebar from "~/components/ProfileSidebar/TheProfileSidebar.vue";

export default {
  components: {
    TheProfileSidebar,
  },
  data() {
    return {};
  },
};
</script>