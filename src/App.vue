<template>
  <div id="app">
    <main class="app">
      <header-app />
      <hero-app />
      <div class="desc">
        <span class="particles-gif" alt="this slowpoke moves" />
        <tokenomics-app />
        <how-to-app />
        <roadmap-app />
        <team-app />
      </div>
      <footer-app />
    </main>
  </div>
</template>

<script lang="ts">
import FooterApp from "./modules/Footer.vue";
import TokenomicsApp from "./modules/Tokenomics.vue";
import HowToApp from "./modules/How-to.vue";
import HeaderApp from "./modules/Header_menu.vue";
import HeroApp from "./modules/Hero.vue";
import RoadmapApp from "./modules/Roadmap.vue";
import TeamApp from "./modules/Team.vue";
import Vue from "vue";
import AOS from "aos";
export default Vue.extend({
  name: "App",
  components: {
    FooterApp,
    TokenomicsApp,
    HowToApp,
    HeaderApp,
    HeroApp,
    RoadmapApp,
    TeamApp,
  },
  created() {
    AOS.init();
  },
});
</script>

<style lang="scss">
* {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

html,
body {
  font-family: "Roboto", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  color: var(--type-light);
  overflow-x: hidden;
}

body {
  background-color: var(--bg-dark);
}

a {
  text-decoration: none;
  color: var(--accent);
}

main {
  width: 100%;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: kanit, sans-serif;
  font-weight: 300;
  font-style: normal;
}

h1 {
  font-size: 5rem;
  font-weight: 500;
}
.section {
  z-index: 2;
  max-width: 1100px;
  width: 100%;
  // min-height: 800px;
  padding: 2rem 1rem;
  margin: 0 auto;
  text-align: center;
}

// flex

.flex {
  display: flex;
}

.row {
  flex-direction: row;
}

.column {
  flex-direction: column;
}

.center {
  justify-content: center;
  align-items: center;
}

.space-between {
  justify-content: space-between;
}

.align-center {
  align-items: center;
}
.particles-gif {
  position: absolute;
  z-index: 4;
  opacity: 0.3;
  width: 100%;
  height: 100%;
  background-image: url("/assets/bg-gif.gif");

  background-repeat: repeat;
  background-size: cover;
  background-size: 33% auto;
}
@media only screen and (max-width: 768px) {
  .particles-gif {
    background-size: 100% auto;
  }
}
@keyframes rotate {
  to {
    --angle: 360deg;
  }
}
@property --angle {
  syntax: "<angle>";
  initial-value: 0deg;
  inherits: false;
}
:root {
  --bg-dark: rgb(35, 35, 35);
  --c1: 20, 255, 161;
  --c2: 0, 151, 191;
  --c3: 68, 112, 210;
  --c4: 146, 67, 232;
  --c5: 227, 21, 255;
  --bg: var(--bg-dark);
  --type-dark: rgba(0, 0, 0, 0.9);
  --type-light: rgba(255, 255, 255, 0.9);
  --accent: rgb(var(--c2));
  scroll-behavior: smooth;
}
.header-2 {
  font-size: 2rem;
  font-weight: 400;
}

.desc {
  position: relative;
  z-index: 3;
  background: linear-gradient(
    to bottom,
    #1b2137,
    #1b2137 25%,
    #1b2137 50%,
    #1b2137 75%
  );
}
</style>