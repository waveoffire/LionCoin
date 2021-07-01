<template>
  <div id="app">
    <main class="app">
      <header id="topbar" class="topbar">
        <section class="section flex row space-between align-center">
          <div class="logo flex row center">
            <img
              class="logo-img__small"
              src="assets/svg/lion.svg"
              alt="space lion logo"
            />
            <h4 class="logo-title__small">SpaceLion Token</h4>
          </div>
          <nav class="nav">
            <ul v-if="!mobile" class="nav-list">
              <li><a class="nav-item" href="#tokenomics">Tokenomics</a></li>
              <li><a class="nav-item" href="#how-to">How To Buy</a></li>
              <li><a class="nav-item" href="#token-info">Token Info</a></li>
              <li><a class="nav-item" href="#team">Team</a></li>
              <li><a class="nav-item" href="#contact">Contact</a></li>
            </ul>
            <div v-else @click="menuToggle()">
              <i class="fa fa-bars fa-2x" aria-hidden="true"></i>
              <ul v-if="toggle" class="nav-list">
                <li><a class="nav-item" href="#tokenomics">Tokenomics</a></li>
                <li><a class="nav-item" href="#how-to">How To Buy</a></li>
                <li><a class="nav-item" href="#token-info">Token Info</a></li>
                <li><a class="nav-item" href="#team">Team</a></li>
                <li><a class="nav-item" href="#contact">Contact</a></li>
              </ul>
            </div>
          </nav>
        </section>
      </header>
      <div class="hero">
        <div id="particles-js"></div>
        <div class="overlay"></div>
        <section id="hero" class="hero-content section flex column center">
          <img
            class="logo-img"
            src="/assets/svg/lion.svg"
            alt="space lion logo"
          />
          <h1 class="logo-title">SpaceLion</h1>
          <span class="logo-sub">The King of The Crypto Jungle</span>
          <a
            href="#"
            class="btn btn-grad"
            target="_blank"
            rel="noopener noreferrer"
            >Buy on Pancakeswap V2</a
          >
          <a
            href="#"
            class="btn btn-grad"
            target="_blank"
            rel="noopener noreferrer"
            >Live charts</a
          >
        </section>
      </div>
      <section id="tokenomics" class="section tokenomics">tokenomics</section>
      <section id="how-to" class="section how-to">how-to</section>
      <section id="token-info" class="section token-info">token-info</section>
      <section id="team" class="section team">team</section>
    </main>
    <footer id="contact" class="section">
      <section>footer</section>
    </footer>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "App",
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

<style lang="scss">
</style>