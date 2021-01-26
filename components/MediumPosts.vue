<template>
  <!-- <MediumPostsItem :posts="posts" v-for="post in posts" :key="post">
    </MediumPostsItem> -->

  <!-- <b-card-group columns class="pt-4">
      <MediumPostsItem :posts="posts"> </MediumPostsItem>
    </b-card-group> -->

  <b-container fluid class="p-0">
    <b-row>
      <b-col
        cols="8"
        class="section__container d-flex flex-column p-0"
        :key="index"
        v-for="(post, index) in posts.slice(
          (currentPage - 1) * perPage,
          (currentPage - 1) * perPage + perPage
        )"
      >
        <div class="empty-space-section-content p-0">
            <TheHeader />
          </div>

        <a :href="post.link" target="blank" class="post__card align-self-center m-auto">
          <!-- <b-card> -->
          <b-card
            :img-src="post.thumbnail"
            img-alt="Post Image"
            img-top
          >
            <!-- <b-card-image :src="post.thumbnail"> </b-card-image> -->
            <b-card-title>
              {{ post.title }}
            </b-card-title>
            <b-card-sub-title class="mb-1">
              <!-- {{ post.author }} -->
              {{ post.pubDate }}
            </b-card-sub-title>
            <b-card-text>
              <!-- <p v-html="post.description" v-if="post.description.length > 50 ? post.description : post.description.substring(0, 50) + '...'"></p> -->
              <p v-html="post.description.substring(1, 500)"></p>

              <div class="post-categories__container mt-2">
                <b-badge
                  v-for="(categorie, index) in post.categories"
                  :key="index"
                  class="d-inline border border-light-gray mr-1"
                >
                  {{ categorie }}
                </b-badge>
              </div>
            </b-card-text>
          </b-card>
        </a>

        <header class="mt-auto text-center">
          <h2 class="medium-title__section font-effect-outline text-lg mb-0">Medium</h2>
        </header>
      </b-col>

      <!-- justify-content-center align-items-end border border-primary -->
      <b-col cols="4" class="pagination__container d-flex flex-column px-5">
        <div class="empty-space p-0"></div>
        <!-- <b-card class="elements__pagination d-flex flex-row"> -->
        <div class="elements__pagination d-flex flex-row w-100 mx-auto">
          <h1 v-if="currentPage < 10" class="current-page__pagination d-inline mr-auto nb-0">
            0{{ currentPage }}
          </h1>
          <h1 v-else class="current-page__pagination d-inline mr-auto nb-0">
            0{{ currentPage }}
          </h1>
          <h5 class="d-inline align-self-end pb-4">/{{ posts.length }}</h5>
        </div>
        <!-- </b-card> -->

        <b-card
          class="elements__pagination card_description align-self-center m-auto p-0"
        >
          <h5 class="text-center text-uppercase mb-4">Section Descrption</h5>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit iusto
            a laboriosam nemo quo perferendis beatae autem. Facilis odio, ab
            commodi doloribus repudiandae maxime quod distinctio, velit quam non
            nulla?
          </p>
        </b-card>
        <b-pagination
          pills
          :total-rows="posts.length"
          :per-page="perPage"
          v-model="currentPage"
          class="align-self-center mt-auto my-0 mb-4"
        >
        </b-pagination>
      </b-col>
    </b-row>

    <!-- <b-row>
          <b-col md="6" class="my-1">
            <b-pagination
              :total-rows="repositoriesData.length"
              :per-page="perPage"
              v-model="currentPage"
              class="my-0"
            >
            </b-pagination>
          </b-col>
        </b-row> -->
  </b-container>
</template>

<script>
import MediumPostsItem from "~/components/MediumPostsItem.vue";

export default {
  name: "MediumPosts",
  data() {
    return {
      items: this.posts,
      paginatedItems: this.posts,
      currentPage: 1,
      perPage: 1,
    };
  },
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

<style lang="scss">
$gray-800: #343a40 !default; // text

.post__card {
  width: 15rem;
  max-width: 40rem;
  color: $gray-800;
}
.post__card:hover {
  text-decoration: none;
  color: $gray-800;
}

.medium-title__section {
  font-size: 9rem;
  // font-weight: 900;
  font-family: 'Inter', 'Source Sans Pro';
  // font-family: 'Bungee Hairline', 'Source Sans Pro';
}
</style>