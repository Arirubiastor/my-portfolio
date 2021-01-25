<template>
  <b-container fluid class="p-0">
    <b-row>
      <b-col
        cols="8"
        class="section__container d-flex flex-column p-0"
        :key="index"
        v-for="(IGpost, index) in collection.slice(
          (currentPage - 1) * perPage,
          (currentPage - 1) * perPage + perPage
        )"
      >
        <div class="empty-space-section-content p-0">
            <TheHeader />
        </div>

        <b-card v-if="collection && collection.length > 0"
          class="instagram__card align-self-center m-auto"
          :img-src="IGpost.media_url"
          img-alt="Instagram image"
          img-top
        >
          {{ IGpost.caption }}
        </b-card>

        <div v-else>
          <b-card
          class="instagram__card align-self-center m-auto"
          :img-src="IGpost.media_url"
          img-alt="Instagram image"
          img-top
        >
          Instagram post
        </b-card>
        <b-card
          class="instagram__card align-self-center m-auto"
          :img-src="IGpost.media_url"
          img-alt="Instagram image"
          img-top
        >
          Instagram post
        </b-card>
        <b-card
          class="instagram__card align-self-center m-auto"
          :img-src="IGpost.media_url"
          img-alt="Instagram image"
          img-top
        >
          Instagram post
        </b-card>
        </div>
        

        <header class="mt-auto text-center">
          <h2 class="ig-title__section font-effect-outline text-lg mb-0">
            Instagram
          </h2>
        </header>
      </b-col>
      <b-col cols="4" class="pagination__container d-flex flex-column px-5">
        <div class="empty-space p-0"></div>
        <div class="elements__pagination d-flex flex-row w-100 mx-auto">
          <h1
            v-if="currentPage < 10"
            class="current-page__pagination d-inline mr-auto nb-0"
          >
            0{{ currentPage }}
          </h1>
          <h1 v-else class="current-page__pagination d-inline mr-auto nb-0">
            {{ currentPage }}
          </h1>
          <h5 class="d-inline align-self-end pb-4">/{{ collection.length }}</h5>
        </div>

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
          :total-rows="collection.length"
          :per-page="perPage"
          v-model="currentPage"
          class="align-self-center mt-auto my-0 mb-4"
        >
        </b-pagination>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import InstagramMediaItem from "~/components/InstagramMediaItem.vue";
export default {
  components: {
    InstagramMediaItem,
  },
  props: {
    collection: {
      // type: Array,
      // required: true,
      collection: [],
    },
  },
  data() {
    return {
      items: this.collection,
      paginatedItems: this.collection,
      currentPage: 1,
      perPage: 1,
      // IGcollection: [],
    };
  },
  // mounted() {
  //   this.IGcollection = this.collection;
  // },
};
</script>

<style lang="scss">
.instagram__card {
  max-width: 25rem;
}
.ig-title__section {
  font-size: 7rem;
  font-weight: 900;
}
</style>