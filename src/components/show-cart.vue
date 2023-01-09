<template>

  <div id="top" @mousemove="mousemove">
    <div class="perspective">
      <div class="card" id="card" ref="card">
        <img class="thumb" src="../../src/assets/photo.jpg" alt="photo">
        <span v-if="this.languageUk">I'm Georgy</span>
        <span v-if="!this.languageUk">Я Георгий</span>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: "show-card",

  props: ['language'],

  data() {
    return {
      languageUk: true,
    }
  },

  updated() {
    this.$nextTick(function () {
      this.languageUk = this.language
    })
  },

  methods:{

    mousemove(){
      let card = this.$refs.card;
      document.addEventListener("mousemove", function (t) {
          if (document.documentElement.scrollTop < 600){
            let e = -(window.innerWidth / 2 - t.pageX) / 45,
                n = (window.innerHeight / 2 - t.pageY) / 15;
            card.style.cssText = "transform: rotateY(" + e + "deg) rotateX(" + n + "deg);-webkit-transform:" +
                " rotateY(" + e + "deg) rotateX(" + n + "deg);-moz-transform: rotateY(" + e + "deg) rotateX(" + n + "deg)"
          }
      })
    },
  }
}

</script>

<style scoped>

.perspective {
  width: 100%;
  perspective: 1000px;
  margin-bottom: 50px;
}


#top {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto;
}

.card {
  width: 270px;
  margin: auto;
  box-shadow:  0 0 20px #354f52,
  0 0 20px #52796f;
  transform-style: preserve-3d;
  transition: transform 0.05s linear;
  border-radius: 15px;
}

.card .thumb {
  background-size: cover;
  height: 85%;
  width: 100%;
  border-radius: 15px;
}

.card .thumb:after {
  background: inherit;
  content: "";
  display: block;
  position: absolute;
  left: -60px;
  top: 40px;
  width: 100%;
  height: 108%;
  z-index: -1;
  filter: blur(55px);
}
.card h2 {
  position: absolute;
  top: 0;
  left: -60px;
  font-size: 40px;
  font-weight: 100;
  transform: translateZ(80px);
  background: transparent;
}

.card span {
  position: absolute;
  bottom: 40px;
  right: -50px;
  font-size: 40px;
  font-weight: 600;
  transform: translateZ(35px);
  background: transparent;
}

img {
  margin: auto;
  display: block;

}

@media screen and (max-width: 900px) {
  *{
    transition: all 1s;
  }

  .card{
    width: 200px;
  }

  .card span {
    font-size: 30px;
  }
}

</style>
