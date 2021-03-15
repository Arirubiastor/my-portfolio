<template>
  <div>
    <b-button
      class="profile-sidebar__plus-button h5 mr-3 mb-0"
      v-b-toggle.sidebar-1
      variant="light"
    >
      <b-icon icon="plus"></b-icon>
    </b-button>
    <b-sidebar class="profile-sidebar" id="sidebar-1" shadow width="30rem">
      <div class="test px-4 py-2 mt-2">
        <b-tabs content-class="mt-3 mt-md-4 px-1">
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
};
</script>

<style lang="scss">
.profile-sidebar__plus-button {
  background-color: white;
  border: none;
}

.profile-sidebar__plus-button {
  background-color: white;
  border: none;
  &:hover {
    background-color: white;
    border: none;
  }
  &:active {
    background-color: white;
    border: none;
  }
  &:focus {
    background-color: white;
    border: none;
  }
  &:visited {
    background-color: white;
    border: none;
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
}
</style>