<template>
  <div class="container">
    <!-- Header title -->
    <header class="pt-4">
      <h2 class="font-bold text-lg md:text-2xl">Github Repositories</h2>
    </header>
    <!-- Grid mobile: 1, tablet: 2, desktop: 3 columns -->
    <div
      v-if="repositoriesData && repositoriesData.length > 0"
      class="flex flex-wrap pt-4 md:-mr-6"
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
      <b-card-group columns>
      <GitHubReposItem
        :repositories="repositoriesData"
        :bg-color="bgColorsData"
      />
      </b-card-group>
    </div>
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
};
</script>

<style>
</style>