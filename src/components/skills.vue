<template>
  <h1 class="title">{{ this.toggleLanguageTitle }}</h1>
  <div class="wrap-skills">

    <div class="wrap" v-for="skill in this.skills" :key="skill.id">
      <p>{{ skill }}</p>
    </div>

  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "skills",

  props: ['language'],

  data() {
    return {
      languageUk: true,
      toggleLanguageTitle: 'SKILLS',
      skills: [
        'HTML5', 'CSS', 'SCSS, Stylus', 'JavaScript', 'TypeScript', 'Angular 9+', 'Vue 3', 'Git, GitHub', 'Bootsrap, Angular Material', 'D3, Chart.js', 'RxJs', 'Figma', 'Npm, Yarn', 'Firebase']
    }
  },

  updated() {
    this.$nextTick(function () {
      this.languageUk = this.language
      this.toggleLanguageTitle = this.languageUk ? 'SKILLS' : 'Навыки'
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
  padding: 50px 0;
  margin-bottom: 50px;
}

.wrap {
  position: relative;
  padding: 10px 20px;
  margin: 0 15px 20px 0;
  text-transform: uppercase;
  border-radius: 10px;
  font-weight: 500;
  font-size: 15px;
  overflow: hidden;
  transition: all 0.3s cubic-bezier(0.02, 0.01, 0.47, 1);
  color: var(--color);
  background: var(--background);
  box-shadow: var(--box-shadow);
}

.wrap p {
  background: transparent;
}

.wrap:hover {
  animation: sh0 0.5s ease-in-out both;
  box-shadow: var(--box-shadow-hover);
}

@keyframes sh0 {
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

.wrap:hover p {
  animation: storm 0.7s ease-in-out both;
  animation-delay: 0.06s;
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

</style>
