<template>
  <div id="fp-nav" class="fp-right">
    <ul>
      <li><a class=""><span class="fp-sr-only">home</span>
        <span
            @click="scrollTo(0)"
            v-bind:class="{ active: isHome }"
        ></span></a></li>

      <li><a class="active"><span class="fp-sr-only">mission</span><span
          @click="scrollTo(1000)"
          v-bind:class="{ active: isSkills }"
      ></span></a></li>

      <li><a class=""><span class="fp-sr-only">aibots</span><span
          @click="scrollTo(1900)"
          v-bind:class="{ active: isProject }"
      ></span></a></li>

    </ul>
  </div>
</template>

<script>
export default {
  name: "scrollBar",

  mounted() {
    document.addEventListener('scroll', () => {

      this.isHome = document.documentElement.scrollTop < 600;
      this.isSkills = document.documentElement.scrollTop > 600 && document.documentElement.scrollTop < 1400;
      this.isProject = document.documentElement.scrollTop >= 1400;

    })
  },

  data() {
    return {
      isHome: true,
      isSkills: false,
      isProject: false,
    }
  },

  methods: {

    scrollTo(scroll) {
      window.scrollTo({
        top: scroll, behavior: "smooth"
      })
    },
  }
}


</script>

<style scoped>

#fp-nav, #fp-nav ul {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

#fp-nav ul li a span, .fp-slidesNav ul li a span {
  background: #fffbfb;
  opacity: .24;
}

#fp-nav ul li a span:hover {
  transform: scale(2);
  cursor: pointer;
}

#fp-nav ul li a span, .fp-slidesNav ul li a span {
  border-radius: 50%;
  position: absolute;
  z-index: 1;
  height: 8px;
  width: 8px;
  border: 0;
  background: #efecec;
  left: 40%;
  top: 50%;
  margin: -2px 0 0 -2px;
  -webkit-transition: all .1s ease-in-out;
  transition: all .1s ease-in-out;
}

.fp-sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

#fp-nav ul {
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
}

#fp-nav ul li, .fp-slidesNav ul li {
  display: block;
  width: 14px;
  height: 13px;
  margin: 7px;
  position: relative;
}

#fp-nav.fp-right {
  right: 17px;
}

#fp-nav {
  background-image: var(--scrollGradient);
  height: 13rem;
  width: 1.2rem;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  border-radius: 1rem;
}

#fp-nav {
  position: fixed;
  z-index: 100;
  top: 50%;
  opacity: 1;
  transform: translateY(-50%);
  -ms-transform: translateY(-50%);
  -webkit-transform: translate3d(0, -50%, 0);
}

*, :after, :before {
  outline: none;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

.active {
  transform: scale(2);
}
</style>
