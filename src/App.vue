<template>
  <div id="app">
    <main class="app">
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
              <li><a class="nav-item" href="#token-info">Token Info</a></li>
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
              <a @click="menuToggle()" class="nav-item" href="#token-info"
                >Token Info</a
              >
            </li>
            <li>
              <a @click="menuToggle()" class="nav-item" href="#team">Team</a>
            </li>
            <li>
              <a @click="menuToggle()" class="nav-item" href="#contact"
                >Contact</a
              >
            </li>
          </ul>
        </transition>
      </header>

      <div class="hero">
        <div id="particles-js"></div>
        <div class="overlay"></div>
        <section id="hero" class="hero-content section flex column center">
          <img
            class="logo-img"
            src="/assets/svg/lion.svg"
            alt="Lion Space logo"
          />
          <h1 class="logo-title liontext">Lion Space</h1>
          <span class="logo-sub"
            >Galactic Lion is a fair-launched, community driven project with
            high expectations and charity intentions. Our mission is to deliver
            high quality token ecosystem full of utility, changing and inputting
            a bit extra into the world of meme cryptocurrencies.</span
          >
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
      <div class="desc">
        <div id="particles-js2"></div>
        <section id="tokenomics" class="section tokenomics">
          <h2 class="header-2">Tokenomics</h2>
          <div class="tokenomics-div">
            <i class="fa fa-fw fa-money fa-5x" aria-hidden="true"></i>
            <h3>Total Supply</h3>
            <span> 1,000,000,000,000 </span>
          </div>
          <div class="tokenomics-div">
            <i class="fa fa-fw fa-fire fa-5x" aria-hidden="true"></i>
            <h3>Token redistribution</h3>

            <span class="redistirbution"> 4% Burn to liquidity</span>

            <span class="redistirbution"> 4% Distribution to the holders </span>
            <span class="redistirbution"> 2% To the marketing wallet </span>
          </div>
        </section>
        <section id="how-to" class="section how-to">
          <h2 class="header-2">How to buy</h2>
          <div class="how-to-step">
            <h3>
              <span>01.</span> Get a TrustWallet, or use any other BSC
              compatibile wallet.
            </h3>
            <span> You can download it from AppStore/Google Play.</span>
          </div>
          <div class="how-to-step">
            <h3>
              <span>02.</span> Go to dApps, or type pancakeswap.finance into
              adress bar.
            </h3>
            <span>
              We'll be firstly listed on PancakeSwap and we recommend to use
              this one to swap BSC to $GLION.</span
            >
          </div>
          <div class="how-to-step">
            <h3><span>03.</span> Connect your wallet to PancakeSwap.</h3>
            <span>
              Click "Connect" at the top right of the screen, and then navigate
              to "Trade" on the left sidebar.</span
            >
          </div>
          <div class="how-to-step">
            <h3><span>04.</span> Select the $GLION token‍</h3>
            <span>
              Click on the "Select a Currency" button, and enter the $GLION
              token contract: (tutej nasz konktrakt który zdeplojujem)</span
            >
          </div>
          <div class="how-to-step">
            <h3><span>05.</span> Adjust your slippage to 11-13%‍</h3>
          </div>
          <div class="how-to-step">
            <h3><span>06.</span> Swap away!‍</h3>
          </div>
        </section>
        <section id="token-info" class="section token-info">
          <h2 class="header-2">Token Info</h2>
        </section>
        <section id="team" class="section team">
          <h2 class="header-2">Team</h2>
        </section>
      </div>
    </main>
    <footer id="contact" class="section">
      <section>
        <div class="socials">
          <i class="fa fa-facebook fa-fw fa-3x" aria-hidden="true"></i>
          <i class="fa fa-twitter fa-fw fa-3x" aria-hidden="true"></i>
          <i class="fa fa-github fa-fw fa-3x" aria-hidden="true"></i>
          <i class="fa fa-telegram fa-fw fa-3x" aria-hidden="true"></i>
          <i class="fab fa-3x fa-fw fa-discord"></i>
        </div>
        <div class="copyright">COPYRIGHT 2021 - Lion Space</div>
      </section>
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
#particles-js {
  position: absolute;
  z-index: 10;
  opacity: 0.7;
  width: 120%;
  height: 120%;
  background-color: transparent;
  background-image: url("");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 60% 60%;
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
  --c1: 20, 255, 161;
  --c2: 0, 151, 191;
  --c3: 68, 112, 210;
  --c4: 146, 67, 232;
  --c5: 227, 21, 255;
}

.liontext {
  font-size: 3.2rem;
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
.header-2 {
  font-size: 2rem;
  font-weight: 400;
}
.tokenomics {
  padding-top: 3rem;
}

.tokenomics-div {
  position: relative;
  display: inline-table;

  width: 48%;
  height: 300px;
  i {
    margin-top: 15px;
    color: rgba(rgb(235, 222, 41), 1);
  }

  margin: 10px 5px;

  border-radius: 25px;
  background-color: rgba(114, 72, 221, 0.279);
  // border: 1px solid rgba(114, 72, 221, 0.694);
  padding-bottom: 20px;
  padding-left: 0;
  h3 {
    font-size: 1.3rem;
  }
  span {
    display: block;
  }
}
@media only screen and (max-width: 768px) {
  .tokenomics-div {
    display: block;
    width: 100%;
  }
}
.tokenomics-div::before {
  content: "";
  animation: 10s rotate linear infinite;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border-radius: 25px;
  padding: 4px;
  background: linear-gradient(
    var(--angle),
    rgba(var(--c1), 1),
    rgba(var(--c2), 1),
    rgba(var(--c3), 1),
    rgba(var(--c4), 1),
    rgba(var(--c5), 1)
  );
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: destination-out;
  mask-composite: exclude;
}

.desc {
  position: relative;
  background: linear-gradient(
    to bottom,
    #1b2137,
    #1b2137 25%,
    #1b2137 50%,
    #1b2137 75%
  );
}
.socials {
  padding: 20px 0;
}
.copyright {
  font-size: 0.7rem;
  color: rgba(255, 255, 255, 0.605);
}
.redistirbution {
  padding-bottom: 20px;
}
.how-to-step {
  border-radius: 25px;
  position: relative;
  text-align: left;
  margin: 10px 0;

  background-color: rgba(114, 72, 221, 0.279);
  padding-top: 1px;
  padding-bottom: 20px;
  padding-left: 20px;
  h3 {
    font-weight: 300;

    span {
      color: rgba(20, 255, 161, 1);
    }
  }
  span {
    color: rgba(255, 255, 255, 0.435);
  }
}
.how-to-step::before {
  content: "";
  animation: 10s rotate linear infinite;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border-radius: 25px;
  padding: 4px;
  background: linear-gradient(
    var(--angle),
    rgba(var(--c1), 1),
    rgba(var(--c2), 1),
    rgba(var(--c3), 1),
    rgba(var(--c4), 1),
    rgba(var(--c5), 1)
  );
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: destination-out;
  mask-composite: exclude;
}
.how-to {
  padding-top: 3rem;
}
</style>