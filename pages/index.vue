<template>
  <div style="background-color: #e9d6d6">
    <GitHubRepos :repositoriesData="repos" :bgColorsData="colors" />
    <MediumPosts :posts="mediumPosts" />
    {{ linkedInProfile }}
    <hr />
    <InstagramMedia :collection="igCollectionList" />
    <!-- {{ igCollectionList }} -->
    <br />
    <!-- {{ postsCategories }} -->
  </div>
</template>

<script>
import GitHubRepos from "~/components/GitHubRepos.vue";
import MediumPosts from "~/components/MediumPosts.vue";
import axios from "axios";

import Vue from "vue";
import { BootstrapVue, BootstrapVueIcons } from "bootstrap-vue";

Vue.use(BootstrapVue);
Vue.use(BootstrapVueIcons);

export default {
  data() {
    return {
      repos: [],
      colors: {},
      mediumPosts: [],
      posts: [],
      postsCategories: [],
      igCollectionList: this.igCollectionList,
      igMediaItem: {},
      igMediaList: this.igMediaList,
      testList: [],
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
      //   .get(
      //     "https://api.linkedin.com/v2/me?access_token=" + process.env.LINKEDIN_ACCESS_TOKEN
      //   )
      //   .then(res => this.linkedInProfile = res.data)
      //   .catch((error) => {
      //     this.errorMessage = error.message;
      //     console.log("There was an error with linkedin get request", error);
      //   });

      fetch(
        "https://api.linkedin.com/v2/me?access_token=" + process.env.LINKEDIN_ACCESS_TOKEN
      )
        .then((res) => res.json())
        .then((data) => {
          this.linkedInProfile = data;
        });
    },
    // Consulta el perímetro de elementos multimedia del usuario
    instagramMediaCollection() {
      const accessToken = process.env.IG_API_LONG_LIVED_ACCESS_TOKEN;
      axios
        .get(
          "https://graph.instagram.com/me/media?fields=id,caption,media_type,media_url&access_token=" +
            accessToken
        )
        .then((res) => (this.igCollectionList = res.data.data))
        // console.log(this.igCollectionList)
        .catch((error) => {
          this.errorMessage = error.message;
          console.log("There was an error with IG collection request", error);
        });
    },

    // Array of list of id's posts

    // instagramMediaList() {
    //   const userId = process.env.IG_API_USER_ID;
    //   axios
    //     .get(
    //       `https://graph.instagram.com/${userId}/media?access_token=` +
    //         process.env.IG_API_LONG_LIVED_ACCESS_TOKEN
    //     )
    //     .then(res => this.igMediaList = res.data.data)
    //     .catch((error) => {
    //       this.errorMessage = error.message;
    //       console.log("Error with Media List request", error);
    //     });
    // },
    instagramMediaItem() {
      const mediaTestId = 17890589443777752;
      axios
        .get(
          `https://graph.instagram.com/${mediaTestId}?fields=id,media_type,media_url,username,timestamp&access_token=` +
            process.env.IG_API_LONG_LIVED_ACCESS_TOKEN
        )
        .then((res) => (this.igMediaItem = res.data));
    },

    // Functions (2) to make multiple axios get requests from array result of instagramMediaList()

    // async testRequest() {
    //   const getList = [];
    //   const list = await this.instagramMediaList();
    //   console.log(this.instagramMediaList());
    //   console.log(this.igMediaList);
    //   console.log('LIST'+ list)
    //   for (let itemTest = 0; itemTest < list; itemTest++) {
    //     let testItem = axios.get(
    //       `https://graph.instagram.com/${itemTest}?fields=id,media_type,media_url,username,timestamp&access_token=` +
    //         process.env.IG_API_LONG_LIVED_ACCESS_TOKEN
    //     );
    //     getList.push(testItem);
    //     // console.log()
    //   }
    //   let res = await axios.all(getList);
    //   console.log("FUNCIONA:" + res);
    // },

    
    // get_test() {
    //   var lista = this.igMediaList;
    //   let i = 0;

    //   for (i = 0; i < lista.length; i++) {
    //     axios
    //       .get(
    //         `https://graph.instagram.com/${lista[i]}?fields=id,media_type,media_url,username,timestamp&access_token=` +
    //         process.env.IG_API_LONG_LIVED_ACCESS_TOKEN
    //       )
    //       .then((response) => {
    //         console.log(response.data[0].origin);
    //         this.get_response = response.data[0].origin;
    //       });
    //   }
    // }

  },

  async mounted() {
    await this.getColors();
    this.getRepos();
    this.getPosts();
    this.linkedInProfile();
    this.instagramMediaCollection();
    // await this.instagramMediaList();
    // this.testRequest();
    this.instagramMediaItem();
    // this.get_test();
  },
  // mounted: async function() {
  //   await this.instagramMediaList();
  //   this.instagramMediaItem();
  // }
};

// Actualizar token c/2 meses aquí: https://developers.facebook.com/docs/instagram-basic-display-api/guides/long-lived-access-tokens
</script>

<style lang="scss">
</style>


