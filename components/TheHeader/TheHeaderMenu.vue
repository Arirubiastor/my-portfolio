<template>
  <div
    class="the-header__menu border d-flex flex-column justify-content-center mx-4"
  >
    <b-navbar toggleable="lg" variant="transparent" class="pl-0 py-2">
      <TheProfileSidebar />

      <!-- <b-nav class="d-flex flex-row justify-content-between">
        <b-navbar-brand class="my-name">ariana rubí</b-navbar-brand>
      </b-nav> -->
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
    return {
    };
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

  .my-name {
    font-size: 1.1rem;
    font-family: 'Roboto Mono', monospace;
  }
}

.navbar-expand-lg {
  flex-flow: row nowrap;
  justify-content: space-between;
}

// sm
@media (min-width: 576px) {
  .my-name {
    font-size: 1.3rem !important;
  }
}
</style>