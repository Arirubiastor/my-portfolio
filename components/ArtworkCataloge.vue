<template>
  <b-container fluid class="cataloge__container">
    <b-row
        :key="image"
        v-for="image in images.slice(
          (currentPage - 1) * perPage,
          (currentPage - 1) * perPage + perPage
        )"
        class="cataloge__flex-conatiner"
      >
        <b-col class="cataloge__image-container" >
          <b-img
            fluid
            class="catalogue__image"
            id="my-table"
            :items="items"
            :per-page="perPage"
            :current-page="currentPage"
            :src="image.imageUrl"
            small
          ></b-img>
        </b-col>
        <b-col
          class="cataloge__pagination-container d-flex flex-column justify-content-around align-items-center p-5 col-4 col-md-4 col-lg-3 "
        >
          <div class="cataloge__index-container">
            <p class="cataloge__index-numerator">0{{ currentPage }}</p>
            <p class="cataloge__index-denominator">/0{{ images.length }}</p>
          </div>
          <div>
            <ul>
              <li>Título, año</li>
              <li>Material</li>
              <li>Medidas en inches</li>
              <li>Medidas en cm</li>
            </ul>
          </div>
          <b-pagination
            limit="1"
            pills
            size="lg"
            :total-rows="images.length"
            :per-page="perPage"
            v-model="currentPage"
            aria-controls="my-table"
            class="my-0 mt-5"
          >
          </b-pagination>
        </b-col>
      </b-row>


      <!-- <div
        :key="image"
        v-for="image in images.slice(
          (currentPage - 1) * perPage,
          (currentPage - 1) * perPage + perPage
        )"
        class="cataloge__flex-conatiner"
      >
        <div class="cataloge__image-container" >
          <b-img
            fluid
            class="catalogue__image"
            id="my-table"
            :items="items"
            :per-page="perPage"
            :current-page="currentPage"
            :src="image.imageUrl"
            small
          ></b-img>
        </div>
        <div
          class="cataloge__pagination-container"
        >
          <div class="cataloge__index-container">
            <p class="cataloge__index-numerator">0{{ currentPage }}</p>
            <p class="cataloge__index-denominator">/0{{ images.length }}</p>
          </div>
          <div>
            <ul>
              <li>Título, año</li>
              <li>Material</li>
              <li>Medidas en inches</li>
              <li>Medidas en cm</li>
            </ul>
          </div>
          <b-pagination
            limit="1"
            pills
            size="lg"
            :total-rows="images.length"
            :per-page="perPage"
            v-model="currentPage"
            aria-controls="my-table"
            class="my-0 mt-5"
          >
          </b-pagination>
        </div>
      </div> -->
  </b-container>
</template>

<script>
export default {
  props: {
    images: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      loaded: false, // Prevent displaying component until data loaded

      items: this.images,
      paginatedItems: this.images,
      currentPage: 1,
      perPage: 1,
    };
  },
  mounted() {},
};
</script>

<style lang="scss">
$gray-800: #343a40 !default; // text

.cataloge__container {
  margin-top: 82px;
    .cataloge__flex-conatiner {
      // vanilla flex
      // display: flex;
      // justify-content: center;
      // align-items: center;
      // 
      height: calc(100vh - 82px);
    }
    .cataloge__image-container {
      height: 100%;
      // border: 2px solid aqua;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      .catalogue__image {
        width: 1000px;
      }
    }
    .cataloge__pagination-container {
      // border: 2px solid brown;
      width: 10rem;
      height: inherit;
      border-left: 1px solid $gray-800;
      margin-bottom: 80px;
      .cataloge__index-container {
        display: flex;
        width: 100%;
        justify-content: space-between;
        align-items: flex-end;
        .cataloge__index-numerator {
          font-size: 7rem;
          font-weight: 800;
        }
        .cataloge__index-denominator {
          font-size: 1.5rem;
          margin-bottom: 52px;
        }
      }
      ul {
        list-style: none;
        padding-left: 0;
      }
    }
}
</style>
