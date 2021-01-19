<template>
  <div>
    <!-- <b-card-group columns> -->
      <a :href="post.link" target="blank" v-for="(post, index) in posts" :key="index">
        <!-- <b-card> -->
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
            <p v-html="post.description.substring(1, 1000)"></p>

            <div class="post-categories__container mt-2">
              <b-badge v-for="(categorie, index) in post.categories" :key="index" class="d-inline border border-light-gray mr-1">
              {{ categorie }}
              </b-badge>
            </div>
          </b-card-text>
        </b-card>
      </a>
    <!-- </b-card-group> -->
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
</style>