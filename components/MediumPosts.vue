<template>
  <b-container>
    <header class="pt-4">
      <h2 class="font-bold text-lg md:text-2xl">Blog</h2>
    </header>
    <!-- <MediumPostsItem :posts="posts" v-for="post in posts" :key="post">
    </MediumPostsItem> -->

    <b-card-group columns class="pt-4">
      <MediumPostsItem :posts="posts"> </MediumPostsItem>
    </b-card-group>
  </b-container>
</template>

<script>
import MediumPostsItem from "~/components/MediumPostsItem.vue";

export default {
  name: "MediumPosts",
  componets: {
    MediumPostsItem,
  },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>
</style>