<template>
  <div class="container">
    <h2>Instagram posts</h2>
    <InstagramMediaItem :collection="collection" />
  </div>
</template>

<script>
import InstagramMediaItem from "~/components/InstagramMediaItem.vue";
export default {
  props: {
    collection: {
      type: Array,
      required: true,
    },
  },
  components: {
    InstagramMediaItem,
  },
};
</script>

<style lang="scss">
</style>