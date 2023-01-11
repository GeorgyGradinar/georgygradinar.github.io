<template>
  <div class="arrow" v-if="this.scroll" @click="topScrollTo"></div>
</template>

<script>
export default {
  name: "button-scroll-up",

  data() {
    return {
      scroll: false,
    }
  },

  mounted() {
    document.addEventListener('scroll', () => {
      this.scrollFunction()
    })
  },

  methods:{
    scrollFunction() {
      this.scroll = document.body.scrollTop > 100 || document.documentElement.scrollTop > 100;
    },

    topScrollTo() {
      window.scrollTo({
        top: 0, behavior: "smooth"
      })
    },
  }
}
</script>

<style scoped>

.arrow,
.arrow:before {
  position: fixed;
  top: 90%;
  right: 10%;
}

.arrow {
  width: 30px;
  height: 30px;
  margin: 20px 0 0 20px;
  -webkit-transform: rotate(225deg);
  border-left: none;
  border-top: none;
  border-right: 2px var(--color) solid;
  border-bottom: 2px var(--color) solid;
  cursor: pointer;
}

.arrow:before {
  content: "";
  width: 20px;
  height: 20px;
  top: 50%;
  margin: -10px 0 0 0;
  border-left: none;
  border-top: none;
  border-right: 1px var(--color) solid;
  border-bottom: 1px var(--color) solid;
  animation-duration: 3s;
  animation-iteration-count: infinite;
  animation-name: arrow;
}

@keyframes arrow {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
    transform: translate(20px, 20px);
  }
}

</style>
