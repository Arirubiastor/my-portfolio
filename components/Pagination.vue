<template>
  <b-container>
    <b-row>
      <b-col
        cols="12"
        sm="4"
        class="my-1"
        :key="index"
        v-for="(item, index) in repositoriesData.slice(
          (currentPage - 1) * perPage,
          (currentPage - 1) * perPage + perPage
        )"
      >
        <b-card :header="item.name" class="text-center">
          <p class="card-text">{{ item.description }}</p>
        </b-card>
      </b-col>
    </b-row>

    <b-row>
      <b-col md="6" class="my-1">
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
      loaded: false, // Prevent displaying component until data loaded

      items: this.repositoriesData,
      paginatedItems: this.repositoriesData,
      currentPage: 1,
      perPage: 1,
      repositoriesList: [],
    };
  },
  mounted() {
    this.repositoriesList = this.repositoriesData;
  },
};
</script>

<style lang="scss">
</style>
