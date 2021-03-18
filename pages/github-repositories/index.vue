<template>
  <div>
    <GitHubRepos :repositoriesData="repos" :bgColorsData="colors" />
  </div>
</template>

<script>
import GitHubRepos from "~/components/GitHubRepos.vue";

import axios from "axios";

export default {
  components: {
    GitHubRepos,
  },
  data() {
    return {
      repos: [],
      colors: {},
    };
  },
  methods: {
    getColors() {
      axios
        .get(
          "https://raw.githubusercontent.com/ozh/github-colors/master/colors.json"
        )
        .then((res) => (this.colors = res.data));
    },
    getRepos() {
      axios
        .get("https://api.github.com/users/Arirubiastor/repos")
        .then((res) => {
          this.repos = res.data
            .filter((repo) => !repo.fork)
            .sort(
              (repo1, repo2) => repo2.stargazers_count - repo1.stargazers_count
            )
            .slice(0, 6);
        });
    },
  },
  async mounted() {
    await this.getColors();
    this.getRepos();
  },
};
</script>

<style>
</style>