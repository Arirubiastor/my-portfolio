<template>
  <div>
    <b-button
      class="profile-sidebar__button h5 mr-3 mb-0 pl-1"
      v-b-toggle.sidebar-backdrop
      variant="white"
    >
      <!-- <b-icon icon="plus"></b-icon> -->
      ariana rubí
    </b-button>
    <b-sidebar class="profile-sidebar" id="sidebar-backdrop" shadow width="30rem" title="" :backdrop-variant="variant" backdrop sidebar-class="border-right border-dark">
      <div class="test px-4 py-2 mt-2">
        <b-tabs
          content-class="mt-3 mt-md-4 px-1"
          active-nav-item-class="font-weight-bold">
          <b-tab title="biography" active>
            <Profile />
          </b-tab>
          <b-tab title="skills">
            <Skills />
          </b-tab>
          <b-tab title="contact">
            <Contact />
          </b-tab>
        </b-tabs>
        <!-- <b-img src="https://picsum.photos/500/500/?image=54" fluid thumbnail></b-img> -->
      </div>
    </b-sidebar>
  </div>
</template>

<script>
import Profile from "~/components/ProfileSidebar/Profile.vue";
import Contact from "~/components/ProfileSidebar/Contact.vue";
import Skills from "~/components/ProfileSidebar/Skills.vue";

export default {
  name: "TheProfileSidebar",
  components: {
    Profile,
    Contact,
    Skills,
  },
  data() {
    return {
      variant: 'transparent',
    }
  }
};
</script>

<style lang="scss" scoope>
.profile-sidebar__button {
  background-color: transparent !important;
  border: none;
  font-size: 1.1rem;
  // box-shadow: 0 0 0 0.2rem rgb(210 210 211 / 50%);
  box-shadow: none !important;
  font-family: 'Roboto Mono', monospace;
  // margin-left: 0 !important;
}

.profile-sidebar__button {
  background-color: white;
  border: none;
  &:hover {
    background-color: white;
    border: none;
  }
  &:active {
    background-color: white;
    border: none;
    box-shadow: none !important;
  }
  &:focus {
    background-color: white;
    border: none;
    box-shadow: none !important;
  }
  &:visited {
    background-color: white;
    border: none;
    box-shadow: none !important;
  }
}

.profile-sidebar {
  width: 100% !important;
}

.bg-light {
  background-color: white !important;
}

.b-sidebar-header {
  position: absolute;
  width: 40px;
  // margin-left: 380px;
  margin-left: 295px;
}

.close {
  padding-top: 6px;
  box-shadow: none !important;
}

.shadow {
  box-shadow: none !important;
}

.nav-tabs {
  border-bottom: 1px solid gray;
  padding-bottom: 8px;
  .nav-link {
    border: none;
  }
}

@media (min-width: 768px) {
  .b-sidebar-header {
  margin-left: 380px;
}

.profile-sidebar__button {
  font-size: 1.2rem;
}
}
</style>
