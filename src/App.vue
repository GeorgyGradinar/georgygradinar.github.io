<template>

  <scroll-bar></scroll-bar>
  <ButtonScrollUp></ButtonScrollUp>

  <div class="wrapper">
    <BlockHeader @language="toggleLanguage"></BlockHeader>

    <section class="block--about-me">
      <Avatar :language="languageUk"></Avatar>
      <div class="about-me">
        <h1 class="title">Front-end Developer</h1>
      </div>
      <Social></Social>
    </section>

    <CV :language="languageUk"></CV>
    <Skills :language="languageUk"></Skills>
    <Projects :language="languageUk"></Projects>

    <p class="footer">© created by Gradinar Georgy</p>
  </div>

</template>

<script>
import BlockHeader from './components/BlockHeader'
import Avatar from './components/Avatar'
import Skills from "@/components/Skills";
import CV from "@/components/DownloadCV";
import ScrollBar from "@/components/ScrollBar";
import Social from "@/components/Social";
import ButtonScrollUp from "@/components/ButtonScrollUp"
import Projects from "@/components/Projects";

export default {
  name: 'App',
  components: {
    BlockHeader,
    Avatar,
    Skills,
    CV,
    ScrollBar,
    Social,
    ButtonScrollUp,
    Projects
  },

  data() {
    return {
      languageUk: true,
      scroll: false,
    }
  },

  methods: {
    toggleLanguage(language) {
      this.languageUk = language;
    },
  }
}
</script>

<style>
@import "../src/style/index.css";
@import "../src/style/shered-style.css";
@import "../src/style/variables.css";
@import "../src/style/circle-background-hover.css";

.wrapper,
.about-me,
.block--about-me {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 50px;
}

.block--about-me {
  height: calc(100vh - 70px);
  padding-bottom: 50px;
}

.about-me {
  margin-bottom: 50px;
}

.footer {
  margin-bottom: 50px;
}

</style>
