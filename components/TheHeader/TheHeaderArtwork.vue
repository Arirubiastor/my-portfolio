<template>
  <div class="the-header border d-flex flex-column justify-content-center">
    <b-navbar
      fixed="top"
      toggleable="lg"
      variant="transparent"
      class="navbar-global px-1 px-sm-2 px-md-5"
    >
      <TheProfileSidebar />

      <div class="d-flex">
        <b-button v-b-toggle.sidebar-backdrop-1 class="artwork-sidebar__button">
          <b-icon icon="three-dots" variant="dark"></b-icon>
        </b-button>
        <b-sidebar
          class="artwork-sidebar"
          sidebar-class="border-left border-dark"
          id="sidebar-backdrop-1"
          right
          shadow
          width="30rem"
          title="Statememt"
          :backdrop-variant="variant"
          backdrop
          no-header="true"
        >
          <div class="artwork-sidebar__content px-3 py-2">
            <div class="artwork-sidebar__header-conatiner">
              <b-button
                class="artwork-sidebar__close-button mr-4"
                v-b-toggle.sidebar-backdrop-1
                variant="white"
              >
                <b-icon icon="x" class="mb-1"></b-icon>
              </b-button>
              <h5>statement</h5>
            </div>
            <div class="artwork-sidebar__text-conatiner">
              <p>
                Through the selection, transformation and manipulation of
                textile and pictorial materials, my work explores the
                fundamental components of the Universe, energy, matter and
                space-time; delving into the analysis of the behavior and
                properties of light and its interactions with matter.
              </p>
              <p>
                By experimenting with these concepts I compile works that encompass
                different formats, colors, and textures, while combining
                different techniques such as: hand embroidery, machine
                embroidery, photographic transfer on fabric, textile
                pigmentation, and watercolor.
              </p>
              <p>
                As a result of long and detailed production processes, my works manage to transform themselves
                depending on the distance from where they are observed, up close
                it is possible to distinguish the sharpness and detail of
                stitches, colors and textures, and as the view moves away, these
                merge and combine in conclusive forms. In this way I have
                managed to create textile pieces that explore my interest in the
                study of physics, nature and optics; and that in turn activate a
                conscious dialogue towards the understanding of the
                possibilities of reality and our perception of it.
              </p>
            </div>

            <!-- <b-img
              src="https://picsum.photos/500/500/?image=54"
              fluid
              thumbnail
            ></b-img> -->
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
    return {
      variant: "transparent",
    };
  },
};
</script>

<style lang="scss" scoped>
$text-global-color: #343a40;

// #b-sidebar-backdrop-1 {
//   .b-sidebar-header {
//     position: static !important;
//     width: 40px;
//     // margin-left: 380px;
//     margin-left: 29px;
//   }
// }

.artwork-sidebar__button {
  background-color: transparent !important;
  border: none;
  font-size: 1.3rem;
  box-shadow: none !important;
}

.artwork-sidebar__button,
.artwork-sidebar__close-button {
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

.artwork-sidebar {
  background-color: white;
  .artwork-sidebar__content {
    padding-left: 2rem !important;
    padding-right: 2rem !important;
    .artwork-sidebar__header-conatiner {
      height: 62.78px;
      border-bottom: 1px solid gray;
      display: flex;
      justify-content: left;
      align-items: center;
      h5 {
        color: $text-global-color;
        font-weight: 400;
      }
    }
    .artwork-sidebar__text-conatiner {
      margin-top: 1.8rem;
      p {
        line-height: 2;
        font-size: 0.9rem;
      }
    }
  }
}

.navbar-global {
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid $text-global-color;
}

//md
@media (min-width: 768px) {
  .navbar-global {
    padding-top: 1.25rem;
    padding-bottom: 1.25rem;
  }
}
</style>