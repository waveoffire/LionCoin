<template>
  <section id="how-to" class="section how-to">
    <h2 class="header-2">How to buy</h2>
    <div class="how-to-step">
      <h3>
        <span>01.</span> Get a TrustWallet, or use any other BSC compatibile
        wallet.
      </h3>
      <span> You can download it from AppStore/Google Play.</span>
    </div>
    <div class="how-to-step">
      <h3>
        <span>02.</span> Go to dApps, or type pancakeswap.finance into adress
        bar.
      </h3>
      <span>
        We'll be firstly listed on PancakeSwap and we recommend to use this one
        to swap BSC to $GLION.</span
      >
    </div>
    <div class="how-to-step">
      <h3><span>03.</span> Connect your wallet to PancakeSwap.</h3>
      <span>
        Click "Connect" at the top right of the screen, and then navigate to
        "Trade" on the left sidebar.</span
      >
    </div>
    <div class="how-to-step">
      <h3><span>04.</span> Select the $GLION token‍</h3>
      <span>
        Click on the "Select a Currency" button, and enter the $GLION token
        contract: (tutej nasz konktrakt który zdeplojujem)</span
      >
    </div>
    <div class="how-to-step">
      <h3><span>05.</span> Adjust your slippage to 11-13%‍</h3>
    </div>
    <div class="how-to-step">
      <h3><span>06.</span> Swap away!‍</h3>
    </div>
  </section>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "How-to",
  components: {},
  data() {
    return {};
  },
});
</script>

<style lang="scss" scoped>
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