<template>
  <b-container fluid class="cataloge__container">
    <b-row
      :key="index"
      v-for="(image, index) in images.slice(
        (currentPage - 1) * perPage,
        (currentPage - 1) * perPage + perPage
      )"
      class="cataloge__flex-conatiner"
    >
      <b-col class="cataloge__image-container">
          <b-spinner type="grow" label="Loading..." v-show="loadingVisible"></b-spinner>
          <b-img-lazy
            fluid
            class="catalogue__image"
            id="my-table"
            :items="items"
            :per-page="perPage"
            :current-page="currentPage"
            :src="image.imageUrl"
            small
            v-show="!loadingVisible"
          ></b-img-lazy>
      </b-col>
      <!-- <div class="catalogue__mobile-div w-100"></div> -->

      <!-- md -->
      <b-col
        class="cataloge__pagination-container d-none p-5 col-4 col-md-4 col-lg-3"
      >
        <div
          class="cataloge__data-conatiner d-flex flex-column justify-content-between align-items-center"
        >
          <div class="cataloge__index-container">
            <p class="cataloge__index-numerator">0{{ currentPage }}</p>
            <p class="cataloge__index-denominator">/0{{ images.length }}</p>
          </div>
          <div class="cataloge__data-sheet">
            <ul>
              <li>{{ image.title }}, {{ image.year }}</li>
              <li>{{ image.medium }}</li>
              <li>{{ image.measuresCm }}</li>
              <li>{{ image.measuresIn }}</li>
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
            class="mt-5 mb-1"
          >
          </b-pagination>
        </div>
      </b-col>
      <!-- ---------- md ----------- -->

      <!-- Mobile-first responsive -->
      <b-col
        class="cataloge__pagination-container-mobile d-flex flex-column align-items-center px-3 py-1 col-12"
      >
        <b-pagination
          limit="1"
          pills
          size="lg"
          :total-rows="images.length"
          :per-page="perPage"
          v-model="currentPage"
          aria-controls="my-table"
          class="cataloge__mobile-pagination p-0 mt-1"
        >
        </b-pagination>
        <!-- <div class="cataloge__index-container">
          <p class="cataloge__index-numerator">0{{ currentPage }}</p>
          <p class="cataloge__index-denominator">/0{{ images.length }}</p>
        </div> -->
        <!-- <div class="cataloge__data-sheet" v-for="(image, index) in images" :key="index"> -->
        <div class="cataloge__data-sheet">
          <ul>
            <li>{{ image.title }}, {{ image.year }}</li>
            <!-- Título, año -->
            <li>{{ image.medium }}</li>
            <!-- Material -->
            <li>{{ image.measuresCm }}</li>
            <!-- Medidas en cm -->
            <li>{{ image.measuresIn }}</li>
            <!-- Medidas en pulgadas -->
          </ul>
        </div>
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
      loadingVisible: true,
    };
  },
  created() {
    setTimeout(() => this.loadingVisible = false, 2000)
  },
};
</script>

<style lang="scss">
$gray-800: #343a40; // text
$gray-500: #adb5bd;

.cataloge__container {
  margin-top: 60px;
  // height: calc(100vh - 180px);
  .cataloge__flex-conatiner {
    // border: 2px solid red;
    display: flex;

    // height: calc(100vh - 120px);
    height: calc(100vh - 60px);
  }
  .cataloge__image-container {
    // border: 2px solid aqua;
    height: calc(100vh - 286px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .catalogue__image {
      max-height: calc(100vh - 312px);
      background: $gray-500;
    }
  }
  .cataloge__pagination-container {
    .cataloge__data-conatiner {
      // height: inherit;
      height: inherit;
    }
    width: 10rem;
    height: 100%;
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
  }
}

.cataloge__index-container {
  flex-direction: row !important;
}

.cataloge__pagination-container-mobile {
  // border: 2px solid darkorange;
  height: 14rem;
  justify-content: flex-end;
  .cataloge__mobile-pagination {
    // border: 2px solid fuchsia;
  }
  .cataloge__data-sheet {
    // border: 2px solid blue;
    width: 100%;
    border-top: 1px solid $gray-800;
    padding-top: 1rem;
    // padding-bottom: 1rem;
    font-size: 0.8rem;
    ul {
      list-style: none;
      padding-left: 0;
      li {
        margin-bottom: 5px;
      }
    }
  }
}

//sm
@media (min-width: 576px) {
}

// md 768px
@media (min-width: 769px) {
  .cataloge__container {
    margin-top: 82px;
  }

  .cataloge__flex-conatiner {
    height: calc(100vh - 84px) !important;
  }
  .catalogue__mobile-div {
    display: none;
  }

  .cataloge__image-container {
    height: 100% !important;
    .cataloge__image {
      max-height: calc(100vh - 85px) !important;
    }
  }

  .cataloge__pagination-container {
    display: block !important;
  }

  .cataloge__pagination-container-mobile {
    display: none !important;
    .cataloge__index-container {
      display: none !important;
    }
  }
  .cataloge__data-sheet {
    border-top: none;
    padding-top: 0;
    font-size: 1rem !important;
    ul {
      list-style: none;
      padding-left: 0;
      li {
        margin-bottom: 6px;
      }
    }
  }
}
</style>
