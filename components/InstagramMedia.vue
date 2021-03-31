<template>
  <b-container fluid class="p-0">
    <b-row>
      <b-col
        cols="8"
        class="section__container d-flex flex-column p-0"
        :key="index"
      >

        <!-- <div v-else>
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
        </div> -->
        
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
      // IGcollection: [],
      // IGembedList: [
      //   ""
      // ]
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
  // font-weight: 900;
  font-family: "Inter", "Source Sans Pro";
  // font-family: 'Bungee Hairline', 'Source Sans Pro';
}

.instagram-media {
  max-height: 35rem;
  .SocialProof {
  display: none;
}
}


</style>