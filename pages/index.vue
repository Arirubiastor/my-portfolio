<template>
  <div>
    <TheHeader />
    <GitHubRepos :repositoriesData="repos" :bgColorsData="colors" />
    <MediumPosts :posts="mediumPosts" />
    <br />
    {{ postsCategories }}
  </div>
</template>

<script>
import GitHubRepos from "~/components/GitHubRepos.vue";
import MediumPosts from "~/components/MediumPosts.vue";
import axios from "axios";

export default {
  data() {
    return {
      repos: [],
      colors: {},
      mediumPosts: [],
      posts: [],
      postsCategories: [],
    };
  },
  components: {
    GitHubRepos,
    MediumPosts,
  },
//   mounted() {
//     console.log(process.env.TEST_VARIABLE)
// },
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
        "https://api.rss2json.com/v1/api.json?rss_url=https://medium.com/feed/@arianarubigo"
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
    console.log(process.env.TEST_VARIABLE)
  },
};
</script>

<style lang="scss">
</style>
