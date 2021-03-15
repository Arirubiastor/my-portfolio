<template>
  <div
    v-if="repositoriesData && repositoriesData.length > 0"
    class="mt-md-5">
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
      
    <b-container>
      <b-card-group columns class="">
        <GitHubReposItem
          :repositories="repositoriesData"
          :bg-color="bgColorsData"
        />
      </b-card-group>
    </b-container>
  </div>
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
    };
  },
};
</script>

<style lang="scss">

// .repository__card,
// .elements__pagination {
//   max-width: 25rem;
// }

// .card_description {
//   border: none;
// }

// // Mobile first Responsive design
// @media (min-width: 960px) {
//   .title__section {
//     font-size: 10rem;
//   }
// }
</style>