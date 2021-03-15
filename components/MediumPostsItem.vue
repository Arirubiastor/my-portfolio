<template>
  <div>
    <a :href="post.link" target="blank" v-for="(post, index) in posts" :key="index" class="post__card align-self-center m-auto">
      <b-card :img-src="post.thumbnail" img-alt="Post Image" img-top>
        <!-- <b-card-image :src="post.thumbnail"> </b-card-image> -->
        <b-card-title>
          {{ post.title }}
        </b-card-title>
        <b-card-sub-title>
          <!-- {{ post.author }} -->
          {{ post.pubDate }}
        </b-card-sub-title>
        <b-card-text>
          <!-- <p v-html="post.description" v-if="post.description.length > 50 ? post.description : post.description.substring(0, 50) + '...'"></p> -->
          <p v-html="post.description.substring(1, 500)"></p>
          <div class="post-categories__container mt-2">
            <b-badge v-for="(categorie, index) in post.categories" :key="index" class="d-inline border border-light-gray mr-1">
              {{ categorie }}
            </b-badge>
          </div>
        </b-card-text>
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
};
</script>

<style lang="scss">
figcaption,
figure {
  display: none;
}

$gray-800: #343a40 !default; // text

.post__card {
  width: 15rem;
  max-width: 40rem;
  color: $gray-800;
}
.post__card:hover {
  text-decoration: none;
  color: $gray-800;
}

.medium-title__section {
  font-size: 9rem;
  // font-weight: 900;
  font-family: 'Inter', 'Source Sans Pro';
  // font-family: 'Bungee Hairline', 'Source Sans Pro';
}
</style>