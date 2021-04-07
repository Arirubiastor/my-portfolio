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
      <div class="section-description__text">
        <h6>Supporting the Spanish-speaking community</h6>
        <p class="">
          Did you know that the language you speak directly affects your
          internet experience? Well, I learned it little by little, after
          realizing that much of the information I was looking for on the
          internet in my native language, Spanish, did not exist. Soon I had to
          move my search methodology to English, only to realize that this time
          I was able to solve my doubts more frequently on the web.
        </p>
        <p>
          Here are the hard facts: The highest percentage of internet users in
          the world is in English language with 25.9%, while the percentage in
          Spanish is 7.9%. What does this mean, that if I only speak Spanish I
          have access to only 7.9% of the information on the Internet? And the
          answer is basically yes.
        </p>
        <p>
          This is why I write my articles and tutorials in Spanish, because I
          want to support the Spanish speaking community, and this way I can be
          sure that at least in the area of technology in which I am writing
          (Fontend development), the Spanish speaking community will be able to
          find some of the information they are looking for, at least those doubts that I once had and couldn't find
          in my language.
        </p>
      </div>
      <div class="section-description__white-space"></div>
    </div>
    <b-container fluid class="mt-0 mt-md-5">
      <b-card-group columns class="pt-0 mx-md-5">
        <MediumPostsItem :posts="posts"> </MediumPostsItem>
      </b-card-group>
      <!-- <b-row>
        <b-col v-for="(post, index) in posts" :key="index" cols="1" md="3">
          <MediumPostsItem :posts="posts"> </MediumPostsItem>
        </b-col>
      </b-row> -->
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
  font-size: 0.8rem;
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

  h6 {
    margin-bottom: 1rem;
  }

  .section-description__text {
    // margin-right: 35rem;
    // margin-right: 60vw;
    width: 35rem;
    // border-right: 2px solid $text-global-color;
  }

  .section-description__white-space {
    // border: 1px solid red;
  }
}

.card-columns {
  -webkit-column-count: 1;
  -moz-column-count: 1;
  column-count: 1;
}

@media (min-width: 660px) {
  .card-columns {
    -webkit-column-count: 2;
    -moz-column-count: 2;
    column-count: 2;
  }
}

@media (min-width: 768px) {
  .section-description__container {
    font-size: 0.9rem;
    margin-top: 4rem;
    margin-left: 3.5rem;
    margin-right: 3.5rem;
    .section-description__text {
    width: 45rem;
  }
  }

  .card-columns {
    -webkit-column-count: 2;
    -moz-column-count: 2;
    column-count: 2;
  }
}

// lg
@media (min-width: 992px) {
  .section-description__container {
    font-size: 1rem;
    margin-top: 4rem;
    margin-left: 3.5rem;
    margin-right: 3.5rem;
    .section-description__text {
    width: 55rem;
  }
  }
  // .card-columns {
  //   -webkit-column-count: 3;
  //   -moz-column-count: 3;
  //   column-count: 3;
  // }
}

// xl
@media (min-width: 1140px) {
  .card-columns {
    -webkit-column-count: 3;
    -moz-column-count: 3;
    column-count: 3;
  }
  .section-description__text {
    width: 65rem;
  }
}

@media (min-width: 1370px) {
  .card-columns {
    -webkit-column-count: 4;
    -moz-column-count: 4;
    column-count: 4;
  }
}
</style>