<template>
  <div>
    <MediumPosts  :posts="mediumPosts" />
  </div>
</template>

<script>
import MediumPosts from "~/components/MediumPosts.vue";

// import axios from "axios";

import Vue from "vue";
import { BootstrapVue, BootstrapVueIcons } from "bootstrap-vue";

Vue.use(BootstrapVue);
Vue.use(BootstrapVueIcons);

export default {
  components: {
    MediumPosts,
  },
  data() {
    return {
      mediumPosts: [],
    };
  },
  methods: {
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
    this.getPosts();
  },
};
</script>

<style lang="scss">