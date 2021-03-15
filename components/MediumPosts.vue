<template>
  <div v-if="posts && posts.length > 0"
    class="mt-md-5">
    <b-container>
      <b-card-group columns class="pt-4">
        <MediumPostsItem :posts="posts"> </MediumPostsItem>
      </b-card-group>
    </b-container>
  </div>
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
  data() {
    return {
      items: this.posts,
      paginatedItems: this.posts,
    };
  },
};
</script>

<style lang="scss">
</style>