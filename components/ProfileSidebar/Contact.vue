<template>
  <div>
    <div class="contact__list d-flex flex-column">
      <!-- <a :href="contact.email" target="blank" class="inline-block">e-mail</a> -->
      <a href="mailto:arianarubigo@gmail.com" target="blank" class="inline-block">e-mail</a>
      <a :href="contact.linkedinUrl" target="blank" class="d-inline"
        >linkedin</a
      >
      <a :href="contact.instagramUrl" target="blank" class="d-inline"
        >instagram</a
      >
      <a :href="contact.githubUrl" target="blank" class="d-inline">github</a>
      <a :href="contact.mediumUrl" target="blank" class="d-inline">medium</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
  data() {
    return {
      contact: {
        phone: "+49 152 52652146",
        email: "arianarubigo@gmail.com",
        linkedinUser: "/in/ariana-rubi",
        linkedinUrl: "https://www.linkedin.com/in/ariana-rubi/",
        instagramUser: "/ariana.rubii/",
        instagramUrl: "https://www.instagram.com/ariana.rubii/",
        githubUser: "/arirubiastor",
        githubUrl: "https://github.com/arirubiastor",
        mediumUser: "arianarubi.medium.com",
        mediumUrl: "https://arianarubi.medium.com/",
      },
    };
  },
};
</script>

<style lang="scss">
.contact__list {
  text-decoration: none;
  a {
    font-size: 3.3rem;
  }
}

@media (min-width: 768px) {
  .contact__list {
    a {
      font-size: 5rem;
    }
  }
}
</style>