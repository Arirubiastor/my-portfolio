<template>
  <b-container fluid class="p-0">
    <div class="profile__description">
      <p>
        I'm a Frontend Developer and a Visual Artist with a strong emphasis on
        creating digital products that combine art and technology. My strengths
        lie mainly in creativity, which I have built throughout my career as an
        artist and developer. I have a strong ability to create visual concepts
        and turn new and imaginative ideas into reality. I also have the faculty
        to make connections to find hidden patterns, as well as excellent
        analytical and problem-solving skills.
        <!-- I'm a Frontend Developer and a Visual Artist with a strong emphasis on
        creating digital products that combine art and technology. My strengths
        lie mainly in creativity, which I have built throughout my career as an
        artist and developer. I have a strong ability to create visual concepts
        and turn new and imaginative ideas into reality. I also have the faculty
        to make connections to find hidden patterns,as well as excellent
        analytical and problem-solving skills. -->
      </p>
    </div>

    <div class="profile__education">
      <a :href="education.siteUrl" target="blank">
        <h6>
          {{ education.title }}
        </h6>
        <ul>
          <li>{{ education.school }}</li>
          <li>{{ education.degree }}</li>
          <li>{{ education.date }}</li>
        </ul>
      </a>
    </div>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      education: {
        title: "Education",
        school: "Universidad de las Américas Puebla",
        degree: "Bachelor of Fine Arts",
        date: "2012-2016",
        siteUrl:
          "https://www.linkedin.com/school/fundaci%C3%B3n-universidad-de-las-am%C3%A9ricas-puebla/",
      },
      personalData: {
        name: "Ariana Rubí",
        photoUrl:
          "https://my-portfolio-storage-space.s3.amazonaws.com/ari-300px.jpg",
        title: "Frontend Developer & Visual Artist",
        about: "about...",
        languages: ["English", "German", "Spanish (Mothertongue)"],
      },
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.profile__description {
  border-bottom: 1px gray solid;
  p {
    line-height: 30px;
  }
}

.profile__education {
  margin-top: 2rem;
  line-height: 30px;
  a {
    text-decoration: none;
  }
  h6 {
    font-weight: 500;
    color: black !important;
  }
  ul {
    padding-left: 0;
    li {
      list-style: none;
    }
  }
}
</style>
