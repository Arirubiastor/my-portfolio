<template>
  <div>
    <b-card-group deck :key="id" v-for="(skill, id) in skills" class="skills__container px-0 px-md-2">
      <b-card no-body class="border-0 m-2 mb-3">
        <b-card-title class="skills__title">
          {{ skill.name }}
        </b-card-title>
        <b-card-text>
          <b-badge
            variant="white"
            :key="badgeId"
            v-for="(item, badgeId) in skill.details"
            class="skills__badge p-2 mr-2 mb-2 mr-md-3 mb-md-3"
            >{{ item }}</b-badge
          >
        </b-card-text>
      </b-card>
    </b-card-group>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      skills: [
        {
          name: "Technologies",
          details: ["HTML", "CSS/SASS", "JavaScript", "Node.js"],
        },
        { name: "Frameworks", details: ["Vue.js", "Nuxt.js"] },
        {
          name: "UI",
          details: [
            "Adobe Photoshop",
            "Adobe Illustrator",
            "Miro",
            "InVision",
            "Responsive Design",
            "Mobile-first Design",
          ],
        },
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
            "AWS Amplify",
            "Firebase Authentication",
            "Leaflet.js",
            "Git",
            "GitHub",
            "GitLab",
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss">
$text-global-color: #343a40;

.badge {
  font-weight: 500;
  border: 0.5px solid gray;
  border-radius: 40px;
}

.skills__title {
  font-size: 1rem;
}

.skills__badge:hover {
  background-color: $text-global-color;
  color: white;
  border-color: $text-global-color;
  padding: 5rem;
}

@media (min-width: 768px) {
.skills__title {
  font-size: 1.2rem; // 24px
}
}
</style>