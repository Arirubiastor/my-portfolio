<template>
  <b-container fluid class="p-0">
    <b-card style="border: none" no-body>
      <b-tabs class="index-tabs" pills card vertical end>
        <b-tab class="pt-0 pb-0">
          <template #title>
            <div class="border-top d-flex flex-column align-items-center w-100">
              <b-icon
                icon="github"
                variant="gray-800"
                font-scale="3"
                class="my-auto"
              >
              </b-icon>
              <div class="w-100 mt-auto">
                <h5 class="tab-title mt-auto text-center m-0">
                  Github Repositories
                </h5>
              </div>
              <!-- <p>test</p> -->
            </div>
          </template>

          <!-- <b-card-text>git</b-card-text> -->
          <!-- <Pagination :repositoriesData="repositoriesData" :bgColorsData="bgColorsData" /> -->
          <GitHubRepos
            :repositoriesData="repositoriesData"
            :bgColorsData="bgColorsData"
          />
        </b-tab>
        <b-tab>
          <template #title>
            <div class="d-flex flex-column align-items-center w-100">
              <b-icon
                icon="grip-horizontal"
                variant="gray-800"
                font-scale="3"
                class="my-auto"
              >
              </b-icon>
              <div class="w-100 mt-auto">
                <h5 class="tab-title mt-auto text-center m-0">Projects</h5>
              </div>
            </div>
          </template>
          <!-- <b-card-text>Instagram posts</b-card-text> -->
          <Profile
            :repositoriesData="repositoriesData"
            :bgColorsData="bgColorsData"
          />
        </b-tab>
        <b-tab>
          <template #title>
            <div class="d-flex flex-column align-items-center w-100">
              <b-icon
                icon="journal-bookmark"
                variant="gray-800"
                font-scale="3"
                class="my-auto"
              >
              </b-icon>
              <div class="w-100 mt-auto">
                <h5 class="tab-title mt-auto text-center m-0">Blog</h5>
              </div>
            </div>
          </template>
          <!-- <b-card-text>Instagram posts</b-card-text> -->
          <MediumPosts :posts="posts" />
        </b-tab>
        <b-tab class="overflow-hidden">
          <template #title>
            <div class="d-flex flex-column align-items-center w-100">
              <b-icon
                icon="instagram"
                variant="gray-800"
                font-scale="3"
                class="my-auto"
              >
              </b-icon>
              <div class="w-100 mt-auto">
                <h5 class="tab-title mt-auto text-center m-0">
                  Instagram posts
                </h5>
              </div>
            </div>
          </template>
          <!-- <b-card-text>Instagram posts</b-card-text> -->
          <InstagramMedia :collection="collectionList" />
        </b-tab>
        <b-tab>
          <template #title>
            <div class="d-flex flex-column align-items-center w-100">
              <b-icon
                icon="linkedin"
                variant="gray-800"
                font-scale="3"
                class="my-auto"
              >
              </b-icon>
              <div class="w-100 mt-auto">
                <h5 class="tab-title mt-auto text-center m-0">Profile</h5>
              </div>
            </div>
          </template>
          <!-- <b-card-text>Instagram posts</b-card-text> -->
          <Profile
            :repositoriesData="repositoriesData"
            :bgColorsData="bgColorsData"
          />
        </b-tab>
      </b-tabs>
    </b-card>
  </b-container>
</template>

<script>
import Vue from "vue";
import { BootstrapVue, BootstrapVueIcons } from "bootstrap-vue";

Vue.use(BootstrapVue);
Vue.use(BootstrapVueIcons);

export default {
  props: {
    collectionList: {
      type: Array,
      required: true,
    },
    repositoriesData: {
      type: Array,
      required: true,
    },
    bgColorsData: {
      type: Object,
      required: true,
    },
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.index-tabs {
  height: calc(100vh - 80px);
  // border-top: 1.5px gray solid;
}

.border-top {
  border-top: 1.5px gray solid !important;
}

.tab-content {
  border-right: 1.5px gray solid;
}

.tab-title {
  border-top: 1.5px gray solid;
  border-bottom: 1.5px gray solid;
}

.col-auto {
  width: 20rem;
  // max-width: 100%;

  .card-header {
    padding: 0;
  }

  li {
    height: 20%;

    .nav-link {
      height: 100%;
      display: flex;
      justify-content: center;
      // align-items: center;
      border-radius: 0;
      padding: 0;
    }
    .nav-link.active {
      color: #343a40; // gray-800
    }
  }
}
</style>