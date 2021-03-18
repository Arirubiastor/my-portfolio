<template>
  <div v-if="posts && posts.length > 0" class="mt-0">

    <div class="marquee">
      <ul class="marquee__content">
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>

        <!--  Repeated marquee items -->
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
      </ul>
    </div>

    <b-container class="mt-md-5">
      <b-card class="section-description pl-0"
        >Supporting the Spanish-speaking community.</b-card
      >
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
      sectionTitle: "medium posts",
    };
  },
};
</script>

<style lang="scss">
.section-description {
  font-size: 2rem;
  border-radius: 0;
  border-right: 1px solid gray;
  border-top: none;
  // max-width: 40rem;
}
</style>