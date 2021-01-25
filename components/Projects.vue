<template>
  <b-container fluid class="p-0">
    <b-row>
      <b-col
        cols="8"
        class="section__container d-flex flex-column p-0"
        :key="index"
        v-for="(project, index) in ProjectsData.slice(
          (currentPage - 1) * perPage,
          (currentPage - 1) * perPage + perPage
        )"
      >
        <div class="empty-space-section-content p-0">
          <TheHeader />
        </div>

        <a
          :href="project.siteUrl"
          target="blank"
          class="align-self-center m-auto"
        >
          <b-card :img-src="project.imageUrl" class="projects__card m-4">
            <b-card-title class="text-center">
              {{ project.name }}
            </b-card-title>
            <p>{{ project.description }}</p>
            <b-badge
              :key="id"
              v-for="(technology, id) in project.technologies"
              class="m-2"
            >
              {{ technology }}
            </b-badge>
            <b-card-text> </b-card-text>
          </b-card>
        </a>

        <header class="mt-auto text-center">
          <h2 class="title__section font-effect-outline text-lg mb-0">
            Projects
          </h2>
        </header>
      </b-col>

      <b-col cols="4" class="pagination__container d-flex flex-column px-5">
        <div class="empty-space p-0"></div>
        <div class="elements__pagination d-flex flex-row w-100 mx-auto">
          <h1
            v-if="currentPage < 10"
            class="current-page__pagination d-inline mr-auto nb-0"
          >
            0{{ currentPage }}
          </h1>
          <h1 v-else class="current-page__pagination d-inline mr-auto nb-0">
            0{{ currentPage }}
          </h1>
          <h5 class="d-inline align-self-end pb-4">
            /{{ ProjectsData.length }}
          </h5>
        </div>

        <b-card
          class="elements__pagination card_description align-self-center m-auto p-0"
        >
          <h5 class="text-center text-uppercase mb-4">Section Descrption</h5>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit iusto
            a laboriosam nemo quo perferendis beatae autem. Facilis odio, ab
            commodi doloribus repudiandae maxime quod distinctio, velit quam non
            nulla?
          </p>
        </b-card>
        <b-pagination
          pills
          :total-rows="ProjectsData.length"
          :per-page="perPage"
          v-model="currentPage"
          class="align-self-center mt-auto my-0 mb-4"
        >
        </b-pagination>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      items: this.ProjectsData,
      paginatedItems: this.ProjectsData,
      currentPage: 1,
      perPage: 1,
      ProjectsData: [
        {
          name: "Mertraco",
          description: "Head of the FrontEnd development",
          technologies: [
            "Vue.js",
            "Nuxt.js",
            "Javascript",
            "Storyblok",
            "CSS/SASS",
            "AWS",
          ],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/mertraco-desktop.JPG",
          siteUrl: "https://www.mertraco.com/",
        },
        {
          name: "Exikhan",
          description: "Collaborated FrontEnd development",
          technologies: [
            "Vue.js",
            "Nuxt.js",
            "Storyblok",
            "CSS/SASS",
            "Bootstrap",
            "AWS",
          ],
          imageUrl: "https://my-portfolio-storage-space.s3.amazonaws.com/exikhan-desktop.JPG",
          siteUrl: "https://www.exikhan.com/",
        },
        {
          name: "Outscape Map",
          description: "Head of the FrontEnd development",
          technologies: [
            "Vue.js",
            "Vanilla CSS",
            "Leaflet",
            "Firebase",
            "Heroku",
          ],
          imageUrl: "https://my-portfolio-storage-space.s3.amazonaws.com/outscape-desktop.JPG",
          siteUrl: "https://outscape-community.herokuapp.com/",
        },
        {
          name: "Customer Dashboard",
          description: "Head of the FrontEnd development",
          technologies: ["Vue.js", "Nuxt.js", "Storyblok", "CSS/SASS", "AWS"],
          imageUrl: "",
          siteUrl: "",
        },
        {
          name: "Newsletter",
          description: "Head of the FrontEnd development",
          technologies: ["Javasript", "Vanilla CSS", "Amazon S3"],
          imageUrl: "https://my-portfolio-storage-space.s3.amazonaws.com/newsletter-desktop.png",
          siteUrl: "https://tms.schryver.com/",
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.projects__card {
  max-width: 50rem;
}
</style>
