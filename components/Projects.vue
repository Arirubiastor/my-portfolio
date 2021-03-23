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

    <b-container fluid class="mt-4 mt-md-5 px-4">
      <div
        class="projects__section-container d-flex flex-column p-0"
        :key="index"
        v-for="(project, index) in ProjectsData"
      >
        <div class="projects__header-container">
          <h1 class="projects__index">0{{ index + 1 }}</h1>
          <div class="projects__title-conatiner">
            <h3 class="projects__title">{{ project.name }}</h3>
            <p class="projects__subtitle">{{ project.description }}</p>
          </div>
        </div>

        <div class="projects__tech-container">
          <ol
            :key="id"
            v-for="(technology, id) in project.technologies"
            class="projects__tech-list"
          >
            <li>{{ technology }}</li>
          </ol>
        </div>
        <a
          :href="project.siteUrl"
          target="blank"
          class="projects__image-container py-md-5 m-auto"
        >
          <b-img
            :src="project.imageUrl"
            fluid
            class="projects__image"
          ></b-img>
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
      sectionTitle: "digital projects",
      ProjectsData: [
        {
          name: "Mertraco Company's Website Redesign",
          description: "Head of the FrontEnd development",
          technologies: [
            "Vue.js",
            "Nuxt.js",
            "Javascript",
            "Storyblok",
            "CSS/SASS",
            "AWS Amplify",
          ],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/mertraco-desktop.JPG",
          siteUrl: "https://www.mertraco.com/",
        },
        {
          name: "Exikhan Company's Website",
          description: "Collaborated FrontEnd development",
          technologies: [
            "Vue.js",
            "Nuxt.js",
            "Storyblok",
            "CSS/SASS",
            "Bootstrap",
            "AWS Amplify",
          ],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/exikhan-desktop.JPG",
          siteUrl: "https://www.exikhan.com/",
        },
        {
          name: "Outscape Map Collaboration Web Application",
          description: "Head of the FrontEnd development",
          technologies: [
            "Vue.js",
            "Vanilla CSS",
            "Leaflet.js",
            "Firebase Authentication",
            "Heroku",
          ],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/outscape-desktop.JPG",
          siteUrl: "https://outscape-community.herokuapp.com/",
        },
        {
          name: "Track and Trace Web application",
          description: "Head of the FrontEnd development and Web Design",
          technologies: [
            "Vue.js",
            "Nuxt.js",
            "Storyblok",
            "Leaflet.js",
            "Bootstrap/SASS",
            "AWS Amplify",
            "AWS S3",
          ],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/customer-dashboard-desktop.JPG",
          siteUrl:
            "https://development.dd12vh11stjdb.amplifyapp.com/booking-details",
        },
        {
          name: "Newsletter for an ERP",
          description: "Head of the FrontEnd development and Web Design",
          technologies: ["Javasript", "Vanilla CSS", "Amazon S3"],
          imageUrl:
            "https://my-portfolio-storage-space.s3.amazonaws.com/newsletter-desktop.png",
          siteUrl: "https://tms.schryver.com/",
        },
        {
          name: "My Portfolio Web Site",
          description: "Head of the FrontEnd development and Web Design",
          technologies: [
            "Vue.js",
            "Nuxt.js",
            "REST APIs",
            "Bootstrap/SASS",
            "Amazon S3",
            "AWS Amplify",
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
.projects__section-container {
  padding-top: 0;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 5rem;
  // border: 2px solid red;
  border-bottom: 2px solid gray;
  padding: 0 2rem;

  .projects__image-container {
    // border: 5px solid black;
    width: 100%;
    .projects__image {
      // max-width: 80rem;
      margin-top: 1.5rem;
    }
  }
}

.projects__tech-container {
  // margin-left: auto;
  // text-align: right;
  margin-bottom: 2rem;
  margin-top: 13rem;
  .projects__tech-list {
    margin-bottom: 0;
    padding-left: 0;
    li {
      font-size: 2rem;
      font-weight: 700;
      list-style: none;
    }
  }
}

.projects__header-container {
  display: flex;
  align-items: center;
  position: absolute;
  margin-left: -78px;
  margin-right: 2rem;
  
  .projects__index {
    font-size: 10rem;
    // color: gray;
  }

  .projects__title-conatiner {
    margin-left: 2rem;

    .projects__title {
      font-size: 1.2rem;
    }

    .projects__subtitle {
    font-size: 1rem;
  }
  }

  
}

// sm
// @media (min-width: 576px) {
//   .projects__header-container {
//     margin-left: 0;
//   .projects__index {
//     font-size: 8rem;
//     // color: gray;
//   }

//   .projects__subtitle {
//     margin-left: 2rem;
//   }
// }
// }

// md
@media (min-width: 768px) {
  .projects__section-container {
    margin-left: 3.5rem;
    margin-right: 3.5rem;
    margin-bottom: 5rem;
    // border: 2px solid red;
    border-bottom: 2px solid gray;
    padding: 0 2rem;

    .projects__imgae-container {
      // border: 5px solid black;
      .projects__image {
        // max-width: 80rem;
        margin-top: 6rem;
      }
    }
  }

  .projects__tech-container {
  // margin-left: auto;
  // text-align: right;
  margin-bottom: 2rem;
  margin-top: 0;
  .projects__tech-list {
    margin-bottom: 0;
    padding-left: 0;
    li {
      font-size: 2rem;
      font-weight: 700;
      list-style: none;
    }
  }
}

  .projects__header-container {
  position: static;
  margin-left: -160px;

  .projects__index {
    font-size: 15rem;
    // color: gray;
  }

  .projects__title-conatiner {
    margin-left: 2rem;

    .projects__title {
      font-size: 2rem;
    }

    .projects__subtitle {
    font-size: 1rem;
  }
  }
}
}

// xl
@media (min-width: 1200px) {
  .projects__header-container {
  position: static;
  margin-left: -210px;

  .projects__index {
    font-size: 25rem;
    font-weight: 600;
  }

  .projects__title-conatiner {
    margin-left: 2rem;

    .projects__title {
      font-size: 2rem;
    }

    .projects__subtitle {
    font-size: 1rem;
  }
  }
}
}
</style>
