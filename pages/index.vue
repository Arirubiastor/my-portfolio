<template>
  <div>
    <TheHeader />
    <GitHubRepos :repositoriesData="repos" :bgColorsData="colors" />
    <MediumPosts  :posts="mediumPosts" />
    <Projects />
  </div>
</template>

<script>
import GitHubRepos from "~/components/GitHubRepos.vue";
import MediumPosts from "~/components/MediumPosts.vue";
import Projects from "~/components/Projects.vue";
import axios from "axios";

import Vue from "vue";
import { BootstrapVue, BootstrapVueIcons } from "bootstrap-vue";

Vue.use(BootstrapVue);
Vue.use(BootstrapVueIcons);

export default {
  components: {
    GitHubRepos,
    MediumPosts,
    Projects,
  },
  data() {
    return {
      repos: [],
      colors: {},
      mediumPosts: [],
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
    getPosts() {
      fetch(
        "https://api.rss2json.com/v1/api.json?rss_url=https://medium.com/feed/@arianarubi"
      )
        .then((res) => res.json())
        .then((data) => {
          this.mediumPosts = data.items; // Array with the content, without feed and details info
          // console.log(data);

          // this.posts = res.filter(item => item.categories.length > 0)
        });
    },
  },

  async mounted() {
    await this.getColors();
    this.getRepos();
    this.getPosts();
  },
};
</script>

<style lang="scss">



</style>