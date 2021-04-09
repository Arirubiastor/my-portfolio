<template>
  <div class="the-header border d-flex flex-column justify-content-center">
    <b-navbar fixed="top" toggleable="lg" variant="transparent" class="navbar-global px-2 pr-sm-3 px-md-5">
      <TheProfileSidebar />

      <b-nav class="d-flex flex-row justify-content-between">
        <!-- <b-navbar-brand>ariana rubí</b-navbar-brand> -->
        <b-nav-item to="/" class="mr-0">menu</b-nav-item>
      </b-nav>

      <!-- <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item to="/digital-products">
            digital products
          </b-nav-item>
          <b-nav-item>blog</b-nav-item>
          <b-nav-item to="/artwork">artwork</b-nav-item>
            <b-icon
              icon="grip-horizontal"
              variant="dark"
              style="width: 18px; height: 18px"
              class="d-inline"
            >
            </b-icon>
        </b-navbar-nav>
      </b-collapse> -->
    </b-navbar>
  </div>
</template>

<script>
import TheProfileSidebar from "~/components/ProfileSidebar/TheProfileSidebar.vue";

export default {
  components: {
    TheProfileSidebar,
  },
};
</script>

<style lang="scss">
$text-global-color: #343a40; // gray-800

.the-header {
  height: 100%;
  margin-top: auto;
  // border-bottom: 1px solid $text-global-color !important;
  border-bottom: none !important;
  border-top: none !important;
  border-right: none !important;
  border-left: none !important;

  h5 {
    font-size: 1rem;
    font-weight: 100;
  }
}

.navbar-expand-lg {
    flex-flow: row nowrap;
    justify-content: space-between;
}

.navbar-global {
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
  padding-left: 1.2rem !important;
  // border-bottom: 1px solid red;
}

//md
@media (min-width: 768px) {
  .navbar-global {
    padding-top: 1.25rem;
    padding-bottom: 1.25rem;
    padding-left: 2.5rem !important;
}
}
</style>
