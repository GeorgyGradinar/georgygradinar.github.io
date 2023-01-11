<template>

  <scroll-bar></scroll-bar>

  <buttonScrollUp></buttonScrollUp>

  <div class="wrapper">

    <block_header @language="toggleLanguage"></block_header>

    <div class="first-show-wrapper">

      <main_picture :language="languageUk"></main_picture>

      <div class="about-me">

        <h1 class="title">Junior Front-end Developer</h1>
        <h5 class="text">{{ this.toggleLanguageText }}</h5>
      </div>

      <social></social>

    </div>

    <cv :language="languageUk"></cv>

    <skills :language="languageUk"></skills>

    <project :language="languageUk"></project>

    <p class="footer">© created by Gradinar Georgy</p>

  </div>
</template>

<script>
import block_header from './components/block-header'
import main_picture from './components/picture'
import skills from "@/components/skills";
import project from "@/components/project";
import cv from "@/components/download-cv";
import scrollBar from "@/components/scroll-bar";
import social from "@/components/social";
import buttonScrollUp from "@/components/button-scroll-up"
import {Translation} from '@/constants/change-language'

export default {
  name: 'App',
  components: {
    block_header,
    main_picture,
    skills,
    project,
    cv,
    scrollBar,
    social,
    buttonScrollUp,
  },

  data() {
    return {
      languageUk: true,
      toggleLanguageText: Translation.aboutMe.uk,
      scroll: false,
    }
  },

  methods: {
    toggleLanguage(language) {
      this.languageUk = language;
      this.toggleLanguageText = this.languageUk ? Translation.aboutMe.uk : Translation.aboutMe.ru;
    },
  }
}
</script>

<style>

:root {
  --background: #202124;
  --color: #CAD2C5;
  --hover: #84A98C;
  --box-shadow: 5px -5px 10px #131416, -5px 5px 10px #2d2e32;
  --box-shadow-hover: 3px -3px 9px #354f52, -3px 3px 9px #52796f;
  --scrollGradient: linear-gradient(180deg, rgba(32, 33, 36, 1) 0%, rgba(202, 210, 197, 0.3) 50%, rgba(32, 33, 36, 1) 100%);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Open Sans', sans-serif;
  cursor: default;

}

body {
  background-color: var(--background);
  color: var(--color);
  -ms-overflow-style: none;
}

body::-webkit-scrollbar {
  width: 0;
}

.wrapper,
.about-me,
.first-show-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.first-show-wrapper {
  height: calc(100vh - 70px);
  padding-bottom: 50px;
}

.about-me {
  margin-bottom: 50px;
}

.title,
.text {
  display: inline-block;
}

.title {
  font-weight: 700;
  font-size: 60px;
  line-height: 100px;
}

.text {
  display: flex;
  align-items: center;
  text-align: center;
  width: 600px;
  height: 250px;
  font-weight: 500;
  font-size: 25px;
  line-height: 40px;
}

.footer {
  margin-bottom: 50px;
}

@media screen and (max-width: 900px) {
  * {
    transition: all 1s;
  }

  .title {
    font-size: 25px;
  }

  .text {
    width: 300px;
    font-size: 15px;
  }
}

</style>
