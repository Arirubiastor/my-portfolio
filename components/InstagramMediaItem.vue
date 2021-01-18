<template>
  <div>
    <b-card-group columns>
      <b-card v-for="collectionItem in collection" :key="collectionItem.id">
        {{ collectionItem.id }}<br />{{ collectionItem.caption }}
      </b-card>
    </b-card-group>
    <!-- {{ collection }} -->
  </div>
</template>

<script>
export default {
  props: {
    collection: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>
</style>