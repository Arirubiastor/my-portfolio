<template>
  <b-container fluid class="p-0">
    <b-row>
      <b-col
        cols="8"
        class="section__container d-flex flex-column p-0"
        :key="index"
        v-for="(profile, index) in profileData.slice(
          (currentPage - 1) * perPage,
          (currentPage - 1) * perPage + perPage
        )"
      >
        <div class="empty-space-section-content p-0">
          <TheHeader />
        </div>

        <!-- <b-card>
          <b-card-title v-if="profile.itemTitle = 'Main Data'">
            {{ profile.itemTitle }}
          </b-card-title>
          <b-card-text>
            <div :key="id" v-for="(contentDetails, id) in profile.itemContent.personalData">
              <b-img :src="contentDetails.photoUrl"></b-img>
              {{contentDetails.languages }}
            </div>
          </b-card-text>
        </b-card> -->

        <b-card class="profile__card align-self-center m-auto">
          <b-card-title class="text-center">
            {{ profile.itemTitle }}
          </b-card-title>
          <b-card-text>
            <!-- {{ profile.itemContent }} -->
            <div
              :key="id"
              v-for="(contentDetails, id) in profile.itemContent.personalData"
            >
              <b-img :src="contentDetails.photoUrl"></b-img>
              <!-- {{ contentDetails.name }} -->
            </div>

            <div>
              <b-card-group
                deck
                :key="id"
                v-for="(contentDetails, id) in profile.itemContent.skills"
              >
                <b-card class="m-2">
                  <b-card-title>
                    {{ contentDetails.name }}
                  </b-card-title>
                  <b-card-text>
                    <b-badge
                      :key="badgeId"
                      v-for="(item, badgeId) in contentDetails.details"
                      class="m-2"
                      >{{ item }}</b-badge
                    >
                  </b-card-text>
                </b-card>
              </b-card-group>
            </div>

            <!-- <div>
                <b-icon
                icon="linkedin"
                variant="gray-800"
                font-scale="1"
                class="d-inline"
              >
              </b-icon>
                <b-icon
                icon="linkedin"
                variant="gray-800"
                font-scale="1"
                class="d-inline"
              >
              </b-icon>
                <b-icon
                icon="linkedin"
                variant="gray-800"
                font-scale="1"
                class="d-inline"
              >
              </b-icon>
            </div> -->

            <div
              class="single-section__profile"
              :key="id"
              v-for="(contentDetails, id) in profile.itemContent.contact"
            >
              <!-- <h5 class="d-inline">{{ contentDetails.phone }}</h5> -->

              <h5 class="d-inline">{{ contentDetails.email }}</h5>
              <!-- <a :href="contentDetails.linkedinUrl">{{ contentDetails.linkedinUser }}</a> -->
              <h5 class="d-inline">{{ contentDetails.linkedinUrl }}</h5>
              <h5 class="d-inline">{{ contentDetails.instagramUrl }}</h5>
              <h5 class="d-inline">{{ contentDetails.githubUrl }}</h5>
              <h5 class="d-inline">{{ contentDetails.mediumUrl }}</h5>
            </div>

            <div
              class="single-section__profile"
              :key="id"
              v-for="(contentDetails, id) in profile.itemContent.education"
            >
              <a :href="contentDetails.siteUrl" target="blank">
                <h5 class="d-inline">{{ contentDetails.school }}</h5>
              </a>
              <h5 class="d-inline">{{ contentDetails.degree }}</h5>
              <h5 class="d-inline">{{ contentDetails.date }}</h5>
            </div>

            <div
              :key="id"
              v-for="(contentDetails, id) in profile.itemContent.experience"
            >
              {{ contentDetails }}
            </div>
          </b-card-text>
        </b-card>

        <header class="mt-auto text-center">
          <h2 class="title__section font-effect-outline text-lg mb-0">
            Profile
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
            /{{ profileData.length }}
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
          :total-rows="profileData.length"
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
  // props: {
  //   repositoriesData: {
  //     type: Array,
  //     required: true,
  //   },
  // },
  data() {
    return {
      items: this.profileData,
      paginatedItems: this.profileData,
      currentPage: 1,
      perPage: 1,
      profileData: [
        {
          // itemTitle: 'Main Data',
          itemTitle: "Me",
          itemContent: {
            personalData: [
              { name: "Ariana Rubí" },
              {
                photoUrl:
                  "https://my-portfolio-storage-space.s3.amazonaws.com/ari-300px.jpg",
              },
              { title: "Frontend Developer & Visual Artist" },
              { about: "about..." },
              { languages: ["English", "German", "Spanish (Mothertongue)"] },
            ],
          },
        },
        {
          itemTitle: "Skills",
          itemContent: {
            skills: [
              {
                name: "Technologies",
                details: ["HTML", "CSS/SASS", "JavaScript", "Node.js"],
              },
              { name: "Frameworks", details: ["Vue.js", "Nuxt.js"] },
              {
                name: "More",
                details: [
                  "JAMstack",
                  "Content Management Systems (CMS)",
                  "Storyblok",
                  "WordPress",
                  "Bootstrap",
                  "REST APIs",
                  "Instagram API",
                  "Heroku",
                  "Amazon Web Services (AWS)",
                  "Amazon S3",
                  "Firebase Authentication",
                  "Leaflet",
                  "Git",
                  "GitHub",
                  "GitLab",
                  "Adobe Photoshop",
                  "Adobe Illustrator",
                ],
              },
            ],
          },
        },
        {
          itemTitle: "Contact",
          itemContent: {
            contact: [
              { phone: "+49 152 52652146" },
              { email: "arianarubigo@gmail.com" },
              { linkedinUser: "/in/ariana-rubi" },
              { linkedinUrl: "https://www.linkedin.com/in/ariana-rubi/" },
              { instagramUser: "/ariana.rubii/" },
              { instagramUrl: "https://www.instagram.com/ariana.rubii/" },
              { githubUser: "/arirubiastor" },
              { githubUrl: "https://github.com/arirubiastor" },
              { mediumUser: "arianarubi.medium.com" },
              { mediumUrl: "https://arianarubi.medium.com/" },
            ],
          },
        },
        {
          itemTitle: "Education",
          itemContent: {
            education: [
              { school: "Universidad de las Américas Puebla" },
              { degree: "Bachelor of Fine Arts" },
              { date: "2012-2016" },
              { siteUrl: "https://www.udlap.mx/web/" },
            ],
          },
        },
        // {
        //   itemTitle: 'Experience',
        //   itemContent: {
        //     experience: [
        //       { title: '' },
        //       { employmentType: '' },
        //       { company: '' },
        //       { Location: '' },
        //       { date: '' },
        //       { headline: '' },
        //       { description: '' },
        //     ],
        //   },
        // },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.single-section__profile {
  margin: 0.5rem;
  h5 {
    font-size: 1.5rem;
    font-weight: 100;
  }
}
</style>
