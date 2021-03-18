<template>
  <div class="the-header__menu border d-flex flex-column justify-content-center mx-4">
    <b-navbar toggleable="lg" variant="transparent">
      <TheProfileSidebar />

      <b-nav class="d-flex flex-row justify-content-between">
        <!-- <b-navbar-brand>ariana rubí</b-navbar-brand> -->
        <h6>Visual Artist and Frontend Developer</h6>
      </b-nav>
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

.the-header__menu {
  height: 100%;
  margin-top: auto;
  border-bottom: 1px solid $text-global-color !important;
  border-top: none !important;
  border-right: none !important;
  border-left: none !important;

  h5 {
    font-size: 1rem;
    font-weight: 100;
  }
  h6 {
      font-size: 1rem;
      margin-bottom: 0;
      text-transform: uppercase;
        font-style: italic;
        font-weight: 400;
  }
}

.navbar-expand-lg {
    flex-flow: row nowrap;
    justify-content: space-between;
}
</style>