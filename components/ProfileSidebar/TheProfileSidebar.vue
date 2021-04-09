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
    <b-sidebar
      class="profile-sidebar"
      sidebar-class="border-right border-dark"
      id="sidebar-backdrop"
      shadow
      width="30rem"
      title=""
      :backdrop-variant="variant"
      backdrop
      no-header="true"
    >
      <!-- <b-sidebar class="profile-sidebar" id="sidebar-backdrop" shadow title="" :backdrop-variant="variant" backdrop sidebar-class="border-right border-dark"> -->
      <div class="test px-4 py-2 mt-2">
        <div class="close-button__container">
          <b-button
            class="profile-sidebar__close-button mr-4"
            v-b-toggle.sidebar-backdrop
            variant="white"
          >
            <b-icon icon="x" class="mb-1"></b-icon>
          </b-button>
        </div>

        <b-tabs
          content-class="mt-3 mt-md-4 px-1"
          active-nav-item-class="font-weight-bold"
        >
          <b-tab title="biography" active class="tab__item">
            <Profile />
          </b-tab>
          <b-tab title="skills" class="tab__item">
            <Skills />
          </b-tab>
          <b-tab title="contact" class="tab__item">
            <Contact />
          </b-tab>
        </b-tabs>
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
      variant: "transparent",
    };
  },
};
</script>

<style lang="scss" scoope>
.profile-sidebar__button {
  background-color: transparent !important;
  border: none;
  font-size: 1.1rem;
  // box-shadow: 0 0 0 0.2rem rgb(210 210 211 / 50%);
  box-shadow: none !important;
  font-family: "Roboto Mono", monospace;
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

.close-button__container {
  width: 100%;
  .profile-sidebar__close-button {
    position: absolute;
    margin-left: calc(100vw - 100px);
    margin-top: 2px;
  }
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
  li {
    a {
      padding-left: 0.5rem;
      padding-right: 0.5rem;
    }
  }
}

@media (min-width: 350px) {
.nav-tabs {
  li {
    a {
      padding-left: 0.8rem;
      padding-right: 0.8rem;
    }
  }
}
}

@media (min-width: 495px) {
  .profile-sidebar__close-button {
    margin-left: 390px !important;
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
