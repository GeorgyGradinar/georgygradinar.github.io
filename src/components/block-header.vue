<template>
  <header>
    <button class="button" @click="navFunction(1000)">{{ this.toggleLanguageButtonSkill }}</button>
    <button class="button" @click="navFunction(1900)">{{ this.toggleLanguageButtonProject }}</button>
    <div class="wrap-change-theme">
      <svg class="change-theme" v-if="!this.blackTheme" @click="toggleTheme" xmlns="http://www.w3.org/2000/svg"
           height="24" width="24">
        <path
            d="M12 21.2q-3.85 0-6.525-2.675Q2.8 15.85 2.8 12q0-3.825 2.675-6.525T12 2.775q.3 0 .613.012.312.013.612.063-.85.8-1.375 1.875t-.525 2.325q0 2.35 1.65 4T17 12.7q1.225 0 2.3-.525 1.075-.525 1.85-1.375.05.3.063.587.012.288.012.588 0 3.85-2.7 6.537Q15.825 21.2 12 21.2Z"/>
      </svg>
      <svg class="change-theme" v-if="this.blackTheme" @click="toggleTheme" xmlns="http://www.w3.org/2000/svg"
           height="24" width="24">
        <path
            d="M12 17q-2.075 0-3.537-1.463Q7 14.075 7 12t1.463-3.538Q9.925 7 12 7t3.538 1.462Q17 9.925 17 12q0 2.075-1.462 3.537Q14.075 17 12 17ZM2 13.325q-.55 0-.938-.387Q.675 12.55.675 12q0-.55.387-.938.388-.387.938-.387h2q.55 0 .938.387.387.388.387.938 0 .55-.387.938-.388.387-.938.387Zm18 0q-.55 0-.938-.387-.387-.388-.387-.938 0-.55.387-.938.388-.387.938-.387h2q.55 0 .938.387.387.388.387.938 0 .55-.387.938-.388.387-.938.387Zm-8-8q-.55 0-.938-.388-.387-.387-.387-.937V2q0-.55.387-.938.388-.387.938-.387.55 0 .938.387.387.388.387.938v2q0 .55-.387.937-.388.388-.938.388Zm0 18q-.55 0-.938-.387-.387-.388-.387-.938v-2q0-.55.387-.938.388-.387.938-.387.55 0 .938.387.387.388.387.938v2q0 .55-.387.938-.388.387-.938.387ZM5.425 7.3 4.35 6.25q-.4-.375-.387-.938.012-.562.387-.962.375-.4.938-.4.562 0 .937.4L7.3 5.425q.375.375.363.913-.013.537-.363.937-.375.4-.925.4t-.95-.375Zm12.35 12.35L16.7 18.575q-.375-.375-.375-.925t.375-.925q.375-.4.925-.388.55.013.95.388l1.075 1.025q.4.375.388.938-.013.562-.388.962-.375.4-.937.4-.563 0-.938-.4ZM16.725 7.3q-.4-.375-.388-.925.013-.55.388-.95L17.75 4.35q.375-.4.938-.388.562.013.962.388.4.375.4.937 0 .563-.4.938L18.575 7.3q-.375.375-.912.362-.538-.012-.938-.362ZM4.35 19.65q-.4-.375-.4-.938 0-.562.4-.937L5.425 16.7q.375-.375.925-.375t.925.375q.4.375.388.925-.013.55-.388.95L6.25 19.65q-.375.4-.938.388-.562-.013-.962-.388Z"/>
      </svg>
      <svg class="change-language" @click="toggleLanguage" height="24" width="24">
        <path
            d="M12 22q-2.05 0-3.875-.788-1.825-.787-3.187-2.15-1.363-1.362-2.15-3.187Q2 14.05 2 12q0-2.075.788-3.887.787-1.813 2.15-3.175Q6.3 3.575 8.125 2.787 9.95 2 12 2q2.075 0 3.887.787 1.813.788 3.175 2.151 1.363 1.362 2.15 3.175Q22 9.925 22 12q0 2.05-.788 3.875-.787 1.825-2.15 3.187-1.362 1.363-3.175 2.15Q14.075 22 12 22Zm0-2.05q.65-.9 1.125-1.875T13.9 16h-3.8q.3 1.1.775 2.075.475.975 1.125 1.875Zm-2.6-.4q-.45-.825-.787-1.713Q8.275 16.95 8.05 16H5.1q.725 1.25 1.812 2.175Q8 19.1 9.4 19.55Zm5.2 0q1.4-.45 2.487-1.375Q18.175 17.25 18.9 16h-2.95q-.225.95-.562 1.837-.338.888-.788 1.713ZM4.25 14h3.4q-.075-.5-.113-.988Q7.5 12.525 7.5 12t.037-1.012q.038-.488.113-.988h-3.4q-.125.5-.188.988Q4 11.475 4 12t.062 1.012q.063.488.188.988Zm5.4 0h4.7q.075-.5.113-.988.037-.487.037-1.012t-.037-1.012q-.038-.488-.113-.988h-4.7q-.075.5-.112.988Q9.5 11.475 9.5 12t.038 1.012q.037.488.112.988Zm6.7 0h3.4q.125-.5.188-.988Q20 12.525 20 12t-.062-1.012q-.063-.488-.188-.988h-3.4q.075.5.112.988.038.487.038 1.012t-.038 1.012q-.037.488-.112.988Zm-.4-6h2.95q-.725-1.25-1.813-2.175Q16 4.9 14.6 4.45q.45.825.788 1.712.337.888.562 1.838ZM10.1 8h3.8q-.3-1.1-.775-2.075Q12.65 4.95 12 4.05q-.65.9-1.125 1.875T10.1 8Zm-5 0h2.95q.225-.95.563-1.838.337-.887.787-1.712Q8 4.9 6.912 5.825 5.825 6.75 5.1 8Z"/>
      </svg>
      <div class="wrap-language">
        <p v-if="languageUk">UK</p>
        <p v-if="!languageUk">RUS</p>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "block-header",

  data() {
    return {
      blackTheme: true,
      languageUk: true,
      toggleLanguageButtonSkill: 'Skills',
      toggleLanguageButtonProject: 'Project',
    }
  },

  methods: {
    toggleTheme() {
      this.blackTheme = !this.blackTheme;
      let style = document.documentElement.style
      if (this.blackTheme) {
        style.setProperty('--background', '#202124');
        style.setProperty('--color', '#CAD2C5');
        style.setProperty('--hover', '#84A98C');
        style.setProperty('--box-shadow', '5px -5px 10px #131416, -5px 5px 10px #2d2e32');
        style.setProperty('--box-shadow-hover', '3px -3px 9px #354f52, -3px 3px 9px #52796f');
        style.setProperty('--box-shadow-active', '6px -6px 15px #354f52, -6px 6px 15px #52796f');
        style.setProperty('--scrollGradient', 'linear-gradient(180deg, rgba(32,33,36,1) 0%, rgba(202,210,197,0.3) 50%, rgba(32,33,36,1) 100%)')
      } else {
        style.setProperty('--background', '#F1FAEE');
        style.setProperty('--color', '#457B9D');
        style.setProperty('--box-shadow', '2px 2px 7px #457b9d80');
        style.setProperty('--box-shadow-hover', '0px 2px 10px #457b9d80, 2px 2px 10px #457b9d80');
        style.setProperty('--scrollGradient','linear-gradient(0deg, rgba(69,123,157,0.8) 0%, rgba(69,123,157,1) 50%, rgba(69,123,157,0.8) 100%)')
      }
    },

    toggleLanguage() {
      this.languageUk = !this.languageUk;
      this.toggleLanguageButtonSkill = this.languageUk ? 'Skills' : 'Навыки';
      this.toggleLanguageButtonProject = this.languageUk ? 'Project' : 'Проекты';
      this.$emit('language', this.languageUk);
    },

    navFunction(px) {
      window.scrollTo({
        top: px, behavior: "smooth"
      })
    },
  }
}
</script>

<style scoped>

header {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  padding: 20px 100px;
  width: 100%;
  height: 70px;
  background-color: var(--background);
  margin-bottom: 50px;
}

.button {
  width: 120px;
  padding: 10px 20px;
  border: none;
  border-radius: 10px;
  font-weight: 500;
  font-size: 15px;
  text-transform: uppercase;
  color: var(--color);
  background: var(--background);
  box-shadow: var(--box-shadow);
  transition: all 0.3s;
}

.button:hover {
  box-shadow: var(--box-shadow-hover);
}

.button:active {
  transform: scale(0.95);
}

.wrap-change-theme {
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.change-theme,
.change-language,
button {
  margin-right: 20px;
  transition: all 0.2s;
  color: var(--color);
  fill: var(--color);
  cursor: pointer;
}

.change-theme path,
.change-language path {
  cursor: pointer;
}

.change-theme:hover,
.change-language:hover {
  transform: scale(1.2);
}

.change-theme:active,
.change-language:active {
  margin-bottom: 5px;
}

.wrap-language {
  width: 35px;
}

@media screen and (max-width: 600px) {
  *{
    transition: all 1s;
  }
  header {
    padding: 20px 20px;
  }

  .button{
    font-size: 10px;
  }
}

</style>
