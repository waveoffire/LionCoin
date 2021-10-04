<template>
  <header id="topbar" class="topbar">
    <section class="section flex row space-between align-center">
      <div class="logo flex row center">
        <img
          class="logo-img__small"
          src="assets/svg/lion.svg"
          alt="Lion Space  logo"
        />
        <h4 class="logo-title__small">Lion Space Token</h4>
      </div>
      <nav class="nav">
        <ul v-if="!mobile" class="nav-list">
          <li><a class="nav-item" href="#tokenomics">Tokenomics</a></li>
          <li><a class="nav-item" href="#how-to">How To Buy</a></li>
          <li><a class="nav-item" href="#roadmap">Roadmap</a></li>
          <li><a class="nav-item" href="#team">Team</a></li>
          <li><a class="nav-item" href="#contact">Contact</a></li>
        </ul>
        <div v-else @click="menuToggle()">
          <i class="fa fa-bars fa-2x" aria-hidden="true"></i>
        </div>
      </nav>
    </section>
    <transition name="fade">
      <ul
        v-if="toggle && mobile"
        style="display: block; text-align: right"
        class="nav-list mobilemenu"
      >
        <li>
          <a @click="menuToggle()" class="nav-item" href="#tokenomics"
            >Tokenomics</a
          >
        </li>
        <li>
          <a @click="menuToggle()" class="nav-item" href="#how-to"
            >How To Buy</a
          >
        </li>
        <li>
          <a @click="menuToggle()" class="nav-item" href="#roadmap">Roadmap</a>
        </li>
        <li>
          <a @click="menuToggle()" class="nav-item" href="#token-info"
            >Token Info</a
          >
        </li>

        <li>
          <a @click="menuToggle()" class="nav-item" href="#contact">Contact</a>
        </li>
      </ul>
    </transition>
  </header>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "Header",
  components: {},
  data() {
    return {
      toggle: false,
      mobile: false,
    };
  },
  methods: {
    changeMobile() {
      var w = window.innerWidth;
      if (w < 900) {
        this.mobile = true;
      } else {
        this.mobile = false;
      }
    },
    menuToggle() {
      this.toggle = !this.toggle;
    },
  },
  created() {
    this.changeMobile();
    window.addEventListener("resize", this.changeMobile);
  },
  destroyed() {
    window.removeEventListener("resize", this.changeMobile);
  },
});
</script>

<style lang="scss" scoped>
.logo-img__small {
  width: 60px;
}

.logo-title__small {
  font-size: 1.5rem;
  margin: 0;
  font-weight: 400;
  margin-left: 10px;
  margin-bottom: 15px;
}
.mobilemenu {
  font-size: 1.2rem;
}
.fade {
  opacity: 1;
}
.fade-enter-active,
.fade-leave-active {
  transition: all 0.8s ease;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  transform: translateX(150px);
  opacity: 0;
}

.topbar {
  position: fixed;
  z-index: 15;
  width: 100%;
  top: 0;
  background: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 1),
    rgba(0, 0, 0, 0.3),
    rgba(0, 0, 0, 0)
  );
}

.nav {
  --br: 5px;
}

.nav-list {
  display: flex;
  flex-direction: row;
  gap: 1rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-item {
  padding: 0.5rem;
  border-radius: var(--br);
  font-family: kanit, sans-serif;
  color: var(--type-light);
  position: relative;
  display: inline-block;

  --radius: 10px;
  --cmid: rgb(var(--c2));
  --cleft: rgb(var(--c1));
  --cright: rgb(var(--c4));

  transition: color 0.1s ease-out;

  &:hover:first-letter {
    color: var(--cleft);
  }

  &:after,
  &:before {
    --alpha: 0;
    --spread: 0;

    position: absolute;
    bottom: 0;
    left: 50%;

    width: 0;
    height: 2px;
    content: "";

    transition-property: width;
    transition-duration: 0.1s;
    transition-timing-function: ease-out;
    box-shadow: -5px -5px var(--spread) rgba(var(--c1), var(--alpha)),
      5px 5px var(--spread) rgba(var(--c1), var(--alpha)),
      -5px 5px var(--spread) rgba(var(--c4), var(--alpha));
  }

  &:before {
    border-top-left-radius: var(--radius);
    border-bottom-left-radius: var(--radius);
    background-image: linear-gradient(to left, var(--cmid), var(--cleft));

    transform: translateX(-98%);
  }

  &:after {
    border-top-right-radius: var(--radius);
    border-bottom-right-radius: var(--radius);
    left: 48%;
    background: linear-gradient(to right, var(--cmid), var(--cright));
  }

  &:hover:after,
  &:hover:before {
    --alpha: 0.4;
    --spread: 7px;
    width: 50%;
  }
}
</style>