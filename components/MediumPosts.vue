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

      <div class="section-description__container">
        <p class="section-description__text">
          Supporting the Spanish-speaking community.
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Rem quo
          alias sit modi qui eveniet enim, corrupti vitae laudantium quidem
          eligendi ratione, repellendus quibusdam, illum quam mollitia
          necessitatibus ab dolorem.
        </p>
        <div class="section-description__white-space"></div>
      </div
      >
    <b-container fluid class="mt-0 mt-md-5">
      <b-card-group columns class="pt-0 mx-md-5">
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
$text-global-color: #343a40; // gray-800

.section-description__container {
  font-size: 0.9rem;
  border-radius: 0;
  // border-right: 2px solid $text-global-color;
  // border-bottom: 1px solid $text-global-color;
  padding-bottom: 1.5rem;
  margin-top: 2rem;
  margin-left: 1.5rem;
  margin-right: 1.5rem;
  padding-left: 0 !important;
  // max-width: 40rem;
  display: flex;

  .section-description__text {
  // margin-right: 35rem;
  // margin-right: 60vw;
  width: 35rem;
  // border-right: 2px solid $text-global-color;
}
}

@media (min-width: 768px) {
  .section-description__container {
    font-size: 1.1rem;
    margin-top: 4rem;
    margin-left: 3.5rem;
    margin-right: 3.5rem;
  }
}


</style>