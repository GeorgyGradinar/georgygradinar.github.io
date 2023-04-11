<template>
  <h1 class="title">{{ this.toggleLanguageTitle }}</h1>

  <div class="wrap-skills" v-for="block in Object.keys(skills)" :key="block.id">
    <h1 class="header-skills">{{ block }}</h1>
    <div class="wrap" v-for="skill in skills[block]" :key="skill.id">
      {{ skill }}
    </div>
  </div>

</template>

<script>

import {Translation} from '@/constants/change-language'

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "skills",

  props: ['language'],

  data() {
    return {
      languageUk: true,
      toggleLanguageTitle: Translation.skill.uk,
      skills: {
        Main: ['HTML5', 'CSS', 'Sass, Stylus', 'JavaScript', 'TypeScript', 'npm', 'yarn', 'Git', 'GitHub'],
        Angular: ['Angular 9+', 'RxJs', 'Routing', 'Lazy-loading', 'Angular Material'],
        Vue: ['Vue 3', 'Nuxt 3', 'Vue-router', 'Vuetify', 'pinia', 'vuex', 'Composition API', 'Option'],
        Other: ['Bootstrap', 'D3.js', 'Chart.js', 'Figma', 'Firebase', 'Flex', 'Grid', 'Rest API'],
      }
    }
  },

  updated() {
    this.$nextTick(function () {
      this.languageUk = this.language;
      this.toggleLanguageTitle = this.languageUk ? Translation.skill.uk : Translation.skill.ru;
    })
  },
}
</script>

<style scoped>

.wrap-skills {
  width: 600px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
  padding: 50px 0 25px;
}

.header-skills {
  width: 100%;
}

.wrap {
  position: relative;
  padding: 10px 20px;
  text-transform: uppercase;
  border-radius: 10px;
  font-weight: 500;
  font-size: 15px;
  overflow: hidden;
  cursor: pointer;
  transition: all 0.3s cubic-bezier(0.02, 0.01, 0.47, 1);
  color: var(--color);
  background: var(--background);
  box-shadow: var(--box-shadow);
}

.wrap:hover {
  animation: shake 0.5s ease-in-out both;
  box-shadow: var(--box-shadow-hover);
}

@keyframes shake {
  0% {
    transform: rotate(0deg) translate3d(0, 0, 0);
  }

  25% {
    transform: rotate(7deg) translate3d(0, 0, 0);
  }

  50% {
    transform: rotate(-7deg) translate3d(0, 0, 0);
  }

  75% {
    transform: rotate(1deg) translate3d(0, 0, 0);
  }

  100% {
    transform: rotate(0deg) translate3d(0, 0, 0);
  }
}

.wrap::before,
.wrap::after {
  content: '';
  position: absolute;
  right: 0;
  bottom: 0;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background: #457b9d80;
  opacity: 0;
  transition: transform 0.15s cubic-bezier(0.02, 0.01, 0.47, 1), opacity 0.15s cubic-bezier(0.02, 0.01, 0.47, 1);
  z-index: -1;
  transform: translate(100%, -25%) translate3d(0, 0, 0);
}

.wrap:hover::before,
.wrap:hover::after {
  opacity: 0.15;
  transition: transform 0.2s cubic-bezier(0.02, 0.01, 0.47, 1), opacity 0.2s cubic-bezier(0.02, 0.01, 0.47, 1);
}

.wrap:hover::before {
  transform: translate3d(50%, 0, 0) scale(0.9);
}

.wrap:hover::after {
  transform: translate(50%, 0) scale(1.1);
}

@media screen and (max-width: 900px) {
  .wrap-skills {
    width: 300px;
  }

  .wrap {
    font-size: 10px;
  }
}

</style>
