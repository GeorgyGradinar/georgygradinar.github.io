<template>
  <h1 class="title">{{ this.toggleLanguageTitle }}</h1>
  <div class="wrap-projects">

    <div id="project" class="project-first">
      <h2>Todo list</h2>
      <p class="textProject">{{ this.toggleLenguageText[0] }}</p>

      <svg class="icon" viewBox="0 0 30 30" @click="routerURL('https://github.com/GeorgyGradinar/todo.git')">
        <path
            d="M15,3C8.373,3,3,8.373,3,15c0,5.623,3.872,10.328,9.092,11.63C12.036,26.468,12,26.28,12,26.047v-2.051 c-0.487,0-1.303,0-1.508,0c-0.821,0-1.551-0.353-1.905-1.009c-0.393-0.729-0.461-1.844-1.435-2.526 c-0.289-0.227-0.069-0.486,0.264-0.451c0.615,0.174,1.125,0.596,1.605,1.222c0.478,0.627,0.703,0.769,1.596,0.769 c0.433,0,1.081-0.025,1.691-0.121c0.328-0.833,0.895-1.6,1.588-1.962c-3.996-0.411-5.903-2.399-5.903-5.098 c0-1.162,0.495-2.286,1.336-3.233C9.053,10.647,8.706,8.73,9.435,8c1.798,0,2.885,1.166,3.146,1.481C13.477,9.174,14.461,9,15.495,9 c1.036,0,2.024,0.174,2.922,0.483C18.675,9.17,19.763,8,21.565,8c0.732,0.731,0.381,2.656,0.102,3.594 c0.836,0.945,1.328,2.066,1.328,3.226c0,2.697-1.904,4.684-5.894,5.097C18.199,20.49,19,22.1,19,23.313v2.734 c0,0.104-0.023,0.179-0.035,0.268C23.641,24.676,27,20.236,27,15C27,8.373,21.627,3,15,3z"/>
      </svg>
      <div class="technology">
        <p>Angular +14</p>
        <p>TypeScript</p>
        <p>scss</p>
        <p>D3.js</p>
        <p>Chart.js</p>
        <p>Angular Material</p>
      </div>
    </div>

    <div id="project" class="project-second">
      <h2>POSTS</h2>
      <p class="textProject">{{ this.toggleLenguageText[1] }}</p>
      <svg class="icon" viewBox="0 0 30 30" @click="routerURL('https://github.com/GeorgyGradinar')">
        <path
            d="M15,3C8.373,3,3,8.373,3,15c0,5.623,3.872,10.328,9.092,11.63C12.036,26.468,12,26.28,12,26.047v-2.051 c-0.487,0-1.303,0-1.508,0c-0.821,0-1.551-0.353-1.905-1.009c-0.393-0.729-0.461-1.844-1.435-2.526 c-0.289-0.227-0.069-0.486,0.264-0.451c0.615,0.174,1.125,0.596,1.605,1.222c0.478,0.627,0.703,0.769,1.596,0.769 c0.433,0,1.081-0.025,1.691-0.121c0.328-0.833,0.895-1.6,1.588-1.962c-3.996-0.411-5.903-2.399-5.903-5.098 c0-1.162,0.495-2.286,1.336-3.233C9.053,10.647,8.706,8.73,9.435,8c1.798,0,2.885,1.166,3.146,1.481C13.477,9.174,14.461,9,15.495,9 c1.036,0,2.024,0.174,2.922,0.483C18.675,9.17,19.763,8,21.565,8c0.732,0.731,0.381,2.656,0.102,3.594 c0.836,0.945,1.328,2.066,1.328,3.226c0,2.697-1.904,4.684-5.894,5.097C18.199,20.49,19,22.1,19,23.313v2.734 c0,0.104-0.023,0.179-0.035,0.268C23.641,24.676,27,20.236,27,15C27,8.373,21.627,3,15,3z"/>
      </svg>
      <div class="technology">
        <p>Vue 3</p>
        <p>JavaScript</p>
        <p>CSS</p>
      </div>
    </div>

  </div>
</template>

<script>

import {Translation} from '@/constants/change-language'

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "project",

  props: ['language'],

  updated() {
    this.$nextTick(function () {
      this.languageUk = this.language;
      this.toggleLanguageTitle = this.languageUk ? Translation.project.uk : Translation.project.ru;
      this.toggleLenguageText[0] = this.languageUk ? Translation.aboutProject.todo.uk : Translation.aboutProject.todo.ru;
      this.toggleLenguageText[1] = this.languageUk ? Translation.aboutProject.post.uk: Translation.aboutProject.post.ru;
    })
  },

  data() {
    return {
      toggleLanguageTitle: 'Project',
      toggleLenguageText: [Translation.aboutProject.todo.uk , Translation.aboutProject.post.uk]
    }
  },

  methods: {
    routerURL(url) {
      window.open(url, '_blank');
    }
  }
}
</script>

<style scoped>

.wrap-projects {
  width: 800px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  margin-bottom: 150px;
  padding-top: 50px;
  gap: 70px;
}

#project {
  display: flex;
  flex-direction: column;
  justify-content: end;
  align-items: center;
  width: 350px;
  height: 450px;
  padding: 30px 20px;
  text-transform: uppercase;
  border-radius: 10px;
  color: #CAD2C5 !important;
  background-size: cover;
  box-shadow: var(--box-shadow);
}

.project-first {
  background: linear-gradient(0deg, rgba(0, 0, 0, 1) 0%, rgba(0, 0, 0, 0.9136029411764706) 22%, rgba(0, 0, 0, 0.773546918767507) 45%, rgba(0, 0, 0, 0.6755077030812324) 56%,
  rgba(0, 0, 0, 0.6082808123249299) 66%, rgba(0, 0, 0, 0.5214460784313726) 79%, rgba(0, 0, 0, 0.32816876750700286) 90%, rgba(0, 0, 0, 0.04245448179271705) 100%),
  url('../assets/todoBackground.jpg'), no-repeat;
}

.project-second {
  background: linear-gradient(0deg, rgba(0, 0, 0, 1) 0%, rgba(0, 0, 0, 0.8575805322128851) 22%, rgba(0, 0, 0, 0.7343312324929971) 45%, rgba(0, 0, 0, 0.6362920168067228) 56%,
  rgba(0, 0, 0, 0.5382528011204482) 66%, rgba(0, 0, 0, 0.40940126050420167) 79%, rgba(0, 0, 0, 0.2665441176470589) 90%, rgba(0, 0, 0, 0.04245448179271705) 100%),
  url('../assets/articleBackground.jpg'), no-repeat;
}

.technology {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
}

.technology p {
  display: inline-block;
  padding: 5px;
  border-radius: 5px;
  color: #CAD2C5;
  background-color: #202124;

}

#project h2 {
  margin-bottom: 10px;
}

.textProject {
  align-items: center;
  text-align: center;
  margin-bottom: 10px;
}

.icon {
  fill: #CAD2C5;
  width: 40px;
  height: 40px;
  margin-bottom: 10px;
  transition: all 0.1s;
  cursor: pointer;
}

.icon path {
  cursor: pointer;
}

.icon:hover {
  transform: scale(1.2);
}

@media screen and (max-width: 900px) {

  .wrap-projects {
    width: 650px;
  }
}

</style>
