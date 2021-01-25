<template>
  <div>
    <b-card-group columns>
      <b-card v-for="collectionItem in collection" :key="collectionItem.id" :img-src="collectionItem.media_url" img-alt="Instagram image" img-top>
        <b-img></b-img>
        {{ collectionItem.id }}<br />{{ collectionItem.caption }}
      </b-card>
    </b-card-group>
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