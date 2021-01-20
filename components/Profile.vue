<template>
  <b-container>
    <b-row>
      <!-- <b-col cols="12" sm="4" class="my-1" :key="index" v-for="(item, index) in paginatedItems"> -->
        <b-col cols="12" sm="4" class="my-1" :key="index" v-for="(item, index) in repositoriesData.slice((currentPage-1)*perPage,(currentPage-1)*perPage+perPage)">
        <b-card
          :header="item.name"
          class="text-center"
        >
          <p class="card-text">{{item.description}}</p>
        </b-card>
      </b-col>
    </b-row>

    <b-row>
      <b-col md="6" class="my-1">
        <!-- <b-pagination
          @change="onPageChanged"
          :total-rows="totalRows"
          :per-page="perPage"
          v-model="currentPage"
          class="my-0"
          >
        </b-pagination> -->
        <b-pagination
          :total-rows="repositoriesData.length"
          :per-page="perPage"
          v-model="currentPage"
          class="my-0"
          >
        </b-pagination>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>

export default {
  props: {
    repositoriesData: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      loaded: false,

      items: this.repositoriesData,
      paginatedItems: this.repositoriesData,
      currentPage: 1,
      perPage: 1,
      // totalRows: this.repositoriesData.length,
      repositoriesList: [],
    };
  },
  computed: {},
  // methods: {
  //   paginate(page_size, page_number) {
  //     let itemsToParse = this.repositoriesData;
  //     this.paginatedItems = itemsToParse.slice(
  //       page_number * page_size,
  //       (page_number + 1) * page_size
  //     );
  //   },
  //   onPageChanged(page) {
  //     this.paginate(this.perPage, page - 1);
  //   }
  // },
  mounted() {
    // this.paginate(this.perPage, 0);
    this.repositoriesList = this.repositoriesData;
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
