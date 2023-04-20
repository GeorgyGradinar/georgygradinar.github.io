<template>

  <section class="block-projects">
    <h1 class="title">{{ toggleLanguageTitle }}</h1>
    <div class="wrapper-projects">
      <div class="project circle-background" v-for="project in projects" :key="project.id">
        <h1>{{ language ? project.name.UK : project.name.RUS }}</h1>

        <article>
          {{ language ? project.description.UK : project.description.RUS }}
        </article>

        <div class="wrapper-stack">
          <span v-for="stack in project.stack" :key="stack.id">{{ stack }}</span>
        </div>

        <div class="wrapper-link">
          <img v-if="project.links.github" src="../assets/icon-github.svg" alt="github"
               @click="routerURL(project.links.github)">
          <img v-if="project.links.website" src="../assets/internet.svg" alt="web site"
               @click="routerURL(project.links.website)">
        </div>
      </div>
    </div>

  </section>
</template>

<script>
import {Translation} from "@/constants/change-language";
import {Projects} from "@/constants/projects";

export default {
  name: "NewProjects",

  props: ['language'],

  data() {
    return {
      projects: Projects,
      toggleLanguageTitle: Translation.project.uk,
    }
  },

  methods: {
    routerURL(url) {
      window.open(url, '_blank');
    }
  },

  updated() {
    this.$nextTick(function () {
      this.languageUk = this.language;
      this.toggleLanguageTitle = this.languageUk ? Translation.project.uk : Translation.project.ru;
    })
  },
}
</script>

<style scoped>

.block-projects {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 100px ;
}



.project {
  position: relative;
  width: 500px;
  height: 350px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: green;
  overflow: hidden;
  padding: 30px;
  border-radius: 10px;
  font-weight: 500;
  font-size: 15px;
  color: var(--color);
  background: var(--background);
  box-shadow: var(--box-shadow);
  z-index: 0;
}

.project::before,
.project::after {
  top: 0;
}

.project:hover::before {
  transform: translate3d(50%, 0, 0) scale(5);
}

.project:hover::after {
  transform: translate(50%, 0) scale(3);
}

.wrapper-projects{
  width: 80%;
  display: flex;
  flex-wrap: wrap;
  gap: 50px;
  justify-content: center;
  padding: 10px;
  margin: 30px 0;
}

.project h1 {
  font-size: 25px;
  text-transform: uppercase;
}

article {
  font-size: 15px;
  text-transform: uppercase;
}

.wrapper-stack,
.wrapper-link {
  display: flex;
  gap: 20px;
}

.wrapper-stack {
  flex-wrap: wrap;
  width: 100%;
}

.wrapper-stack span {
  padding: 5px 10px;
  text-transform: uppercase;
  border-radius: 10px;
  font-weight: 500;
  font-size: 15px;
  color: var(--color);
  background: var(--background);
  box-shadow: var(--box-shadow);
  transition: all 0.3s;
}

.wrapper-stack span:hover{
  box-shadow: var(--box-shadow-hover);
}

.wrapper-link img {
  cursor: pointer;
}

</style>
