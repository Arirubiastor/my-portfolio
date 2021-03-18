<template>
  <div v-if="repositoriesData && repositoriesData.length > 0" class="mt-md-5">
    <!-- <div
        v-for="repo in repositoriesData"
        :key="repo.id"
        class="w-full md:w-1/2 lg:w-1/3 md:pr-6 pb-4"
      >
        <GitHubReposItem
          :repository="repositoriesData"
          :bg-color="repo.language ? bgColorsData[repo.language].color : '#ffffff'"
          v-for="repo in repositoriesData"
          :key="repo.id"
        />
      </div> -->

    <div class="marquee">
      <ul class="marquee__content">
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>

        <!--  Repeated marquee items -->
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
        <li class="marquee__item">&nbsp;{{ sectionTitle }} &bull;</li>
      </ul>
    </div>

    <b-container class="mt-md-5">
      <b-card-group columns class="">
        <GitHubReposItem
          :repositories="repositoriesData"
          :bg-color="bgColorsData"
        />
      </b-card-group>
    </b-container>
  </div>
</template>

<script>
import GitHubReposItem from "~/components/GitHubReposItem.vue";

export default {
  name: "GitHubRepos",
  components: {
    GitHubReposItem,
  },
  props: {
    repositoriesData: {
      type: Array,
      required: true,
    },
    bgColorsData: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      loaded: false, // Prevent displaying component until data loaded

      items: this.repositoriesData,
      sectionTitle: 'github repositories',
    };
  },
};
</script>

<style lang="scss">
$text-global-color: #343a40; // gray-800

// .repository__card,
// .elements__pagination {
//   max-width: 25rem;
// }

// .card_description {
//   border: none;
// }

// // Mobile first Responsive design
// @media (min-width: 960px) {
//   .title__section {
//     font-size: 10rem;
//   }
// }

.marquee {
  width: 100%;
  height: 80px;
  border-top: 3px solid $text-global-color;
  border-bottom: 3px solid $text-global-color;
  overflow: hidden;
}

.marquee li {
  font-size: 3rem;
  text-transform: uppercase;
}

.marquee__content {
  display: flex;
  list-style: none;
  animation: scrolling 15s linear infinite;
}

.marquee__item {
/*   height: 30px;
  width: 60px; */
  flex-shrink: 0;
}

@keyframes scrolling {
  0% { transform: translateX(0) }
  100% { transform: translateX(-100%) }
}
</style>