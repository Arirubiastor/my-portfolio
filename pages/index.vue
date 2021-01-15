<template>
  <div style="background-color: #e9d6d6;">
    <TheHeader />
    <GitHubRepos :repositoriesData="repos" :bgColorsData="colors" />
    <MediumPosts :posts="mediumPosts" />
    <!-- {{ linkedInProfile }}<hr> -->
    <InstagramMedia />
    {{ instagramCollectionList }}
    {{ instagramMediaItem }}
    <b-img :src="instagramMediaItem.media_url"></b-img>
    <br />
    {{ postsCategories }}

    <script type="text/javascript" src="https://platform.linkedin.com/badges/js/profile.js" async defer></script>
    <div class="LI-profile-badge"  data-version="v1" data-size="medium" data-locale="es_ES" data-type="vertical" data-theme="light" data-vanity="ariana-rubi"><a class="LI-simple-link" href='https://de.linkedin.com/in/ariana-rubi?trk=profile-badge'>Ariana Rubí</a></div>
  </div>
</template>

<script>
import GitHubRepos from "~/components/GitHubRepos.vue";
import MediumPosts from "~/components/MediumPosts.vue";
import axios from "axios";

import Vue from 'vue'
import { BootstrapVue, BootstrapVueIcons } from 'bootstrap-vue'

Vue.use(BootstrapVue)
Vue.use(BootstrapVueIcons)


export default {
  data() {
    return {
      repos: [],
      colors: {},
      mediumPosts: [],
      posts: [],
      postsCategories: [],
      // instagramCollectionList: [],
    };
  },
  components: {
    GitHubRepos,
    MediumPosts,
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
        "https://api.rss2json.com/v1/api.json?rss_url=https://medium.com/feed/@arianarubigo"
      )
        .then((res) => res.json())
        .then((data) => {
          this.mediumPosts = data.items; // Array with the content, without feed and details info
          // console.log(data);
          
          // this.posts = res.filter(item => item.categories.length > 0)
        });
    },
    linkedInProfile() {
      // axios
      //   .get("https://api.linkedin.com/v2/me?access_token=LINKEDIN_ACCESS_TOKEN")
      //   .then((res) => (this.linkedInProfile = res.data));

      // fetch(
      //   "https://api.linkedin.com/v2/me?access_token=LINKEDIN_ACCESS_TOKEN"
      // )
      //   .then((res) => res.json())
      //   .then((data) => {
      //     this.linkedInProfile = data;
      //   });
    },
    // Consulta el perímetro de elementos multimedia del usuario
    instagramMediaCollection() {
      const accessToken = process.env.INSTAGRAM_DISPLAY_API_ACCESS_TOKEN;
      axios
        .get("https://graph.instagram.com/me/media?fields=id,caption&access_token=" + accessToken)
        .then((res) => (this.instagramCollectionList = res.data));
    },
    instagramMediaItem() {
      const mediaTestId = 17890589443777752;
      // ${mediaTestId}
      axios
        .get(`https://graph.instagram.com/17890589443777752?fields=id,media_type,media_url,username,timestamp&access_token=` + process.env.INSTAGRAM_DISPLAY_API_ACCESS_TOKEN)
        .then((res) => (this.instagramMediaItem = res.data));
    }
  },

  async mounted() {
    await this.getColors();
    this.getRepos();
    this.getPosts();
    // this.linkedInProfile();
    this.instagramMediaCollection();
    this.instagramMediaItem();
  },
};
</script>

<style lang="scss">
</style>
