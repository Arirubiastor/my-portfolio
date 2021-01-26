<template>
  <!-- <b-container class="container pagination"> -->
  <div
    v-if="repositoriesData && repositoriesData.length > 0"
    class="flex flex-wrap p-0"
  >
    <!-- <div
        v-for="repo in repositoriesData"
        :key="repo.id"
        class="w-full md:w-1/2 lg:w-1/3 md:pr-6 pb-4"
      >
        <GitHubReposItem
          :repository="repositoriesData"
          :bg-color="repo.language ? bgColorsData[repo.language].color : '#ffffff'"
          v-for="repo in repositoriesData"
        :key="repo.id"
        />
      </div> -->

    <!-- instead of pagination -->
    <!-- <b-card-group columns>
      <GitHubReposItem
        :repositories="repositoriesData"
        :bg-color="bgColorsData"
      />
      </b-card-group> -->

    <b-container fluid class="p-0">
      <b-row>
        <b-col
          cols="8"
          class="section__container d-flex flex-column p-0"
          :key="index"
          v-for="(repository, index) in repositoriesData.slice(
            (currentPage - 1) * perPage,
            (currentPage - 1) * perPage + perPage
          )"
        >
          <div class="empty-space-section-content p-0">
            <TheHeader />
          </div>
          <b-card class="repository__card align-self-center m-auto">
            <b-card-title>
              <svg viewBox="0 0 16 16" class="fill-current" aria-hidden="true">
                <path fill-rule="evenodd" :d="icon.book"></path>
              </svg>
              {{ repository.name }}
            </b-card-title>
            <b-card-text>
              {{ repository.description }}
            </b-card-text>
            <div v-if="repository.language">
              <b-card-text class="d-inline mr-2">
                <!-- <b-img class="language-color" alt="Language color"
              v-bind="mainProps"
              :blank-color=" repository.language ? bgColor : '' "
              rounded="circle"
            >
            </b-img> -->
                <b-img
                  class="language-color"
                  alt="Language color"
                  v-bind="mainProps"
                  :blank-color="bgColorsData.Vue.color"
                  rounded="circle"
                >
                </b-img>
                {{ repository.language }}
              </b-card-text>
              <b-card-text class="d-inline mr-2">
                <svg
                  class="fill-current mr-1"
                  aria-label="stars"
                  viewBox="0 0 16 16"
                  role="img"
                >
                  <path fill-rule="evenodd" :d="icon.star"></path>
                </svg>
                {{ repository.stargazers_count }}
              </b-card-text>
              <b-card-text class="d-inline mr-2">
                <svg
                  class="fill-current mr-1"
                  aria-label="fork"
                  viewBox="0 0 16 16"
                  role="img"
                >
                  <path fill-rule="evenodd" :d="icon.fork"></path>
                </svg>
                {{ repository.forks }}
              </b-card-text>
            </div>
          </b-card>

          <header class="mt-auto text-center">
            <h2 class="title__section text-lg mb-0">Github</h2>
          </header>
        </b-col>

        <!-- justify-content-center align-items-end border border-primary -->
        <b-col cols="4" class="pagination__container d-flex flex-column px-1 px-md-4 px-lg-5">
          <div class="empty-space p-0"></div>
          <!-- <b-card class="elements__pagination d-flex flex-row"> -->
          <div class="elements__pagination d-flex flex-row w-100 mx-auto">
            <h1
              v-if="currentPage < 10"
              class="current-page__pagination d-inline mr-auto nb-0"
            >
              0{{ currentPage }}
            </h1>
            <h1 v-else class="current-page__pagination d-inline mr-auto nb-0">
              0{{ currentPage }}
            </h1>
            <h5 class="d-inline align-self-end pb-4">
              /{{ repositoriesData.length }}
            </h5>
          </div>
          <!-- </b-card> -->

          <b-card
            class="elements__pagination card_description align-self-center m-auto p-0"
          >
            <h5 class="text-center text-uppercase mb-4">Section Descrption</h5>
            <p>
              Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit
              iusto a laboriosam nemo quo perferendis beatae autem. Facilis
              odio, ab commodi doloribus repudiandae maxime quod distinctio,
              velit quam non nulla?
            </p>
          </b-card>
          <b-pagination
            pills
            :total-rows="repositoriesData.length"
            :per-page="perPage"
            v-model="currentPage"
            class="align-self-center mt-auto my-0 mb-4"
          >
          </b-pagination>
        </b-col>
      </b-row>

      <!-- <b-row>
          <b-col md="6" class="my-1">
            <b-pagination
              :total-rows="repositoriesData.length"
              :per-page="perPage"
              v-model="currentPage"
              class="my-0"
            >
            </b-pagination>
          </b-col>
        </b-row> -->
    </b-container>
  </div>
  <!-- </b-container> -->
</template>

<script>
import GitHubReposItem from "~/components/GitHubReposItem.vue";

export default {
  name: "GitHubRepos",
  components: {
    GitHubReposItem,
  },
  props: {
    repositoriesData: {
      type: Array,
      required: true,
    },
    bgColorsData: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      loaded: false, // Prevent displaying component until data loaded

      items: this.repositoriesData,
      paginatedItems: this.repositoriesData,
      currentPage: 1,
      perPage: 1,
      // repositoriesList: [],
      icon: {
        book:
          "M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z",
        star:
          "M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25zm0 2.445L6.615 5.5a.75.75 0 01-.564.41l-3.097.45 2.24 2.184a.75.75 0 01.216.664l-.528 3.084 2.769-1.456a.75.75 0 01.698 0l2.77 1.456-.53-3.084a.75.75 0 01.216-.664l2.24-2.183-3.096-.45a.75.75 0 01-.564-.41L8 2.694v.001z",
        fork:
          "M5 3.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm0 2.122a2.25 2.25 0 10-1.5 0v.878A2.25 2.25 0 005.75 8.5h1.5v2.128a2.251 2.251 0 101.5 0V8.5h1.5a2.25 2.25 0 002.25-2.25v-.878a2.25 2.25 0 10-1.5 0v.878a.75.75 0 01-.75.75h-4.5A.75.75 0 015 6.25v-.878zm3.75 7.378a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm3-8.75a.75.75 0 100-1.5.75.75 0 000 1.5z",
      },
      mainProps: { blank: true, width: 75, height: 75, class: "m1" },
    };
  },
  // mounted() {
  //   this.repositoriesList = this.repositoriesData;
  // },
};
</script>

<style lang="scss">
.empty-space {
  height: 8rem;
  // border: solid 1px blue;
}

.empty-space-section-content {
  height: 8rem;
  border-bottom: 1.5px gray solid;
}

.repository__card,
.elements__pagination {
  max-width: 25rem;
}

.elements__pagination {
  .card-body {
    padding: 0;
  }
}

.card_description {
  border: none;
}

.pagination__container,
.section__container {
  height: calc(100vh - 0.6rem);
  // border: solid 1px blue;

  h1 {
    font-size: 8rem;
    font-weight: 900;
  }
}

.pagination__container {
  border-left: 1.5px gray solid;
  border-top: 1.5px gray solid;
}

.tab-pane {
  height: 100%;
}

.title__section {
  font-family: "Inter", "Source Sans Pro";
  // font-family: 'Bungee Hairline', 'Source Sans Pro';
  font-size: 8rem;
  // font-weight: 900;
  position: relative;
}

// Mobile first Responsive design
@media (min-width: 960px) {
  .title__section {
    font-size: 10rem;
  }
}
</style>