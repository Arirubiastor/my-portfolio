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
              <b-button class="artwork-sidebar__close-button mr-4" v-b-toggle.sidebar-backdrop-1 variant="white">
                <b-icon icon="x" class="mb-1"></b-icon>
              </b-button>
              <h5>statement</h5>
            </div>
            <div class="artwork-sidebar__text-conatiner">
              <p>
              Cras mattis consectetur purus sit amet fermentum. Cras justo odio,
              dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta
              ac consectetur ac, vestibulum at eros. Cras mattis consectetur
              purus sit amet fermentum. Cras justo odio, dapibus ac facilisis
              in, egestas eget quam. Morbi leo risus, porta ac consectetur ac,
              vestibulum at eros. Cras mattis consectetur purus sit amet
              fermentum. Cras justo odio, dapibus ac facilisis in, egestas eget
              quam. Morbi leo risus, porta ac consectetur ac, vestibulum at
              eros. Cras mattis consectetur purus sit amet fermentum. Cras justo
              odio, dapibus ac facilisis in, egestas eget quam. Morbi leo risus,
              porta ac consectetur ac, vestibulum at eros. Cras mattis
              consectetur purus sit amet fermentum. Cras justo odio, dapibus ac
              facilisis in, egestas eget quam. Morbi leo risus, porta ac
              consectetur ac, vestibulum at eros. Cras mattis consectetur purus
              sit amet fermentum. Cras justo odio, dapibus ac facilisis in,
              egestas eget quam. Morbi leo risus, porta ac consectetur ac,
              vestibulum at eros.
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
        font-size: .9rem;
      }
    }
  }
}
</style>