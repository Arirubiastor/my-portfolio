<template>
  <div>
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

    <b-container fluid>
      <div
        cols="8"
        class="section__container d-flex flex-column p-0"
        :key="index"
        v-for="(project, index) in ProjectsData"
      >
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
      </div>
    </b-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: this.ProjectsData,
      sectionTitle: 'digital projects',
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
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/exikhan-desktop.JPG",
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
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/outscape-desktop.JPG",
          siteUrl: "https://outscape-community.herokuapp.com/",
        },
        {
          name: "Customer Dashboard",
          description: "Head of the FrontEnd development and Web Design",
          technologies: [
            "Vue.js",
            "Nuxt.js",
            "Storyblok",
            "Leaflet",
            "CSS/SASS",
            "AWS",
          ],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/customer-dashboard-desktop.JPG",
          siteUrl:
            "https://development.dd12vh11stjdb.amplifyapp.com/booking-details",
        },
        {
          name: "Newsletter",
          description: "Head of the FrontEnd development and Web Design",
          technologies: ["Javasript", "Vanilla CSS", "Amazon S3"],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/newsletter-desktop.png",
          siteUrl: "https://tms.schryver.com/",
        },
        {
          name: "My Portfolio",
          description: "Head of the FrontEnd development and Web Design",
          technologies: [
            "Nuxt",
            "REST APIs",
            "Bootstrap/SASS",
            "Amazon S3",
            "AWS",
          ],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/my-portfolio-desktop.JPG",
          siteUrl: "https://www.arianarubi.com/",
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
