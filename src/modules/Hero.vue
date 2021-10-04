<template>
  <div class="hero">
    <span class="particles-gif" alt="this slowpoke moves" />
    <section id="hero" class="hero-content section flex column center">
      <img class="logo-img" src="/assets/svg/lion.svg" alt="Lion Space logo" />
      <h1 class="logo-title liontext">Lion Space</h1>
      <div v-if="timerenable" class="timer">{{ countdown }}</div>
      <div class="wallet" v-else>
        link do czekos tam wallet chyba wiec dlugie
      </div>
      <span class="logo-sub"
        >Lion Space is an ecosystem driven by the belief that talented people
        should be supported. Our main mission is to digitize art and make it
        available to a wider community of investors. The future of independent
        art is NFT and we strongly believe in it. Join us and be the future
        today.</span
      >
      <a href="#" class="btn btn-grad" target="_blank" rel="noopener noreferrer"
        >Buy on dxsale.app</a
      >
      <a href="#" class="btn btn-grad" target="_blank" rel="noopener noreferrer"
        >Live charts</a
      >
    </section>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "Hero",
  components: {},
  data() {
    return {
      countdown: "",
      timerenable: true,
      final: 0,
    };
  },

  methods: {
    timer() {
      var today = new Date();
      var final = this.final;

      var toFinal = (final - today) / 1000;

      var hours = Math.floor(toFinal / 60 / 60);

      var minutes = Math.floor((toFinal - hours * 60 * 60) / 60);
      var seconds = Math.floor(toFinal - hours * 60 * 60 - minutes * 60);
      if (hours < 10) {
        hours = "0" + hours;
      }
      if (minutes < 10) {
        minutes = "0" + minutes;
      }
      if (seconds < 10) {
        seconds = "0" + seconds;
      }
      this.countdown = hours + ":" + minutes + ":" + seconds;
      if (toFinal <= 0) {
        this.timerenable = false;
      }
    },
  },
  beforeMount() {
    var today = new Date();
    this.final = new Date().setTime(today.getTime() + 40000);
    this.timer();
    setInterval(() => {
      this.timer();
    }, 1000);
  },
});
</script>

<style lang="scss" scoped>
// buttons

.btn {
  --color: var(--accent);
  font-family: kanit;
  font-weight: 500;
  border-style: solid;
  border-radius: 25px;
  // border-width: 3px;
  border-color: var(--accent);
  padding: 1.3rem;
  margin: 1rem;
}

.btn-grad {
  --alpha: 0.1;
  --spread: 20px;
  --g1: var(--c1);
  --g2: var(--c2);
  --g3: var(--c4);
  --border: 5px;

  display: flex;
  align-items: center;
  position: relative;
  transition-duration: 0.2s;
  transition-property: box-shadow;

  color: #fff;
  background: rgba(0, 0, 0, 0.7);
  background-clip: padding-box;
  /* !importanté */
  border: solid var(--border) transparent;
  /* !importanté */
  border-radius: 30px;
  box-shadow: -5px -5px var(--spread) rgba(var(--c1), var(--alpha)),
    5px 5px var(--spread) rgba(var(--c1), var(--alpha)),
    -5px 5px var(--spread) rgba(var(--c4), var(--alpha)),
    inset 0 0 10px rgba(0, 0, 0, 0.8);

  &:before {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;
    margin: calc(var(--border) * -1);
    /* !importanté */
    border-radius: inherit;
    /* !importanté */
    background: linear-gradient(
      to right,
      rgba(var(--g1), 1),
      rgba(var(--g2), 1),
      rgba(var(--g3), 1)
    );
  }

  &:hover {
    --alpha: 0.3;
    --spread: 30px;
  }
}

.hero {
  height: 110vh;
  width: 100%;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: hidden;
  background: linear-gradient(
    to bottom,
    #00000000 0%,
    #00000000 80%,
    #00000000 100%
  );
  background: linear-gradient(
    to bottom,
    #00000091 0%,
    #00000091 80%,
    #1b2137 100%
  );
}

#app {
  background: linear-gradient(
    to bottom,
    #00000000 0%,
    #1b2137 80%,
    #1b2137 100%
  );
}
.hero-content {
  position: absolute;
  z-index: 14;
  width: 100%;
  height: 100%;
  left: 50%;
  transform: translateX(-50%);
  padding-top: 10vh;
}

.logo-img {
  width: auto;
  height: 30vh;
}

.logo-title {
  font-size: 12vh;
  margin: 1rem;
}

.logo-sub {
  font-size: 0.9rem;
  margin-bottom: 2.5rem;
}
.timer {
  font-size: 80px;
  font-family: Fira Code, Menlo, Monaco, Consolas, Liberation Mono, Courier New,
    monospace;
  padding-bottom: 20px;
}
.wallet {
  font-size: 20px;
  font-family: Fira Code, Menlo, Monaco, Consolas, Liberation Mono, Courier New,
    monospace;
  padding-bottom: 20px;
  color: gray;
}

@media only screen and (max-width: 768px) {
  .liontext {
    font-size: 3.2rem;
    margin-bottom: 10px;
  }
  .timer {
    font-size: 50px;
    padding-bottom: 10px;
  }
  .logo-img {
    height: 20vh;
  }
  .btn {
    padding: 1.2rem;
    margin: 0.5rem;
  }
  .logo-sub {
    margin-bottom: 1rem;
  }
  .wallet {
    font-size: 15px;
    padding-bottom: 10px;
  }
}
.logo-sub {
  max-width: 600px;
}
</style>