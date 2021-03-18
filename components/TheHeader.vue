<template>
  <div class="the-header border d-flex flex-column justify-content-center">
    <b-navbar toggleable="lg" variant="transparent">
      <TheProfileSidebar />

      <b-navbar-brand to="/">ariana rubí</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

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

        <!-- <b-navbar-nav class="ml-auto">
          <b-nav-form>
            <b-form-input
              size="sm"
              class="mr-sm-2"
              placeholder="Search"
            ></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit"
              >Search</b-button
            >
          </b-nav-form>
        </b-navbar-nav> -->
      </b-collapse>
    </b-navbar>
    <!-- <b-navbar-brand>Ariana Rubí</b-navbar-brand>
    <h5>Frontend Developer &amp; Visual Artist</h5> -->
  </div>
</template>

<script>
import TheProfileSidebar from "~/components/ProfileSidebar/TheProfileSidebar.vue";

export default {
  components: {
    TheProfileSidebar,
  }

};
</script>

<style lang="scss">
.the-header {
  height: 100%;
  margin-top: auto;
  h5 {
    font-size: 1rem;
    font-weight: 100;
  }
}
</style>