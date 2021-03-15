<template>
  <div>
    <b-card-group deck :key="id" v-for="(skill, id) in skills" class="px-2">
      <b-card no-body class="border-0 m-2 mb-3">
        <b-card-title>
          {{ skill.name }}
        </b-card-title>
        <b-card-text>
          <b-badge
            variant="white"
            :key="badgeId"
            v-for="(item, badgeId) in skill.details"
            class="p-2 m-2"
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
.badge {
  font-weight: 500;
  border: 0.5px solid gray;
  border-radius: 40px;
}
</style>