<template>
  <div>
    <a :href="post.link" target="blank" v-for="(post, index) in posts" :key="index" class="post__card-link align-self-center m-auto">
      <b-card class="post__card" :img-src="post.thumbnail" img-alt="Post Image" img-top no-body>
        <b-card-body class="post__card-body p-3 p-md-4">
          <!-- <b-card-image :src="post.thumbnail"> </b-card-image> -->
        <b-card-sub-title class="post__date mt-1">
          <!-- {{ post.author }} -->
          {{ post.pubDate.split(' ')[0] }}
        </b-card-sub-title>
        <b-card-title class="post__title mt-3">
          {{ post.title }}
        </b-card-title>
        <b-card-text class="mt-3">
          <!-- <p v-html="post.description" v-if="post.description.length > 50 ? post.description : post.description.substring(0, 50) + '...'"></p> -->
          <p v-html="post.description.substring(1, 500)" class="post__description"></p>
          <div class="post__categories-container mt-2">
            <b-badge v-for="(categorie, index) in post.categories" :key="index" class="post__categorie d-inline border border-light-gray mr-1 px-2">
              {{ categorie }}
            </b-badge>
          </div>
        </b-card-text>
        </b-card-body>
      </b-card>
    </a>
  </div>
</template>

<script>
export default {
  name: "MediumPostsItem",
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
  // computed: {
  //   simpleDate() {
  //     return this.post.pubDate.split(' ')[0];
  //   }
  // }
};
</script>

<style lang="scss">
figcaption,
figure {
  display: none;
}

$gray-800: #343a40 !default; // text
.post__card-body {

}

.post__card-link {
  width: 15rem;
  max-width: 40rem;
  color: $gray-800;
}
.post__card-link:hover {
  text-decoration: none;
  color: $gray-800;
}

.medium-title__section {
  font-size: 9rem;
  // font-weight: 900;
  font-family: 'Inter', 'Source Sans Pro';
  // font-family: 'Bungee Hairline', 'Source Sans Pro';
}

.post__card {
  min-width: 290px;
}

.post__date {
  font-size: .75rem;
}

.post__title {
  font-size: 1.25rem;
}

.post__description {
  font-size: .85rem;
}

.post__categorie {
  background-color: white;
  font-size: 0.65rem;
}

@media (min-width: 576px) {
  .post__categorie {
    font-size: 0.75rem;
  }
  .card-columns {
    -webkit-column-count: 4;
    -moz-column-count: 4;
    column-count: 4;
    }
}
</style>