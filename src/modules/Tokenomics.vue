<template>
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
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "Tokenomics",
  components: {},
  data() {
    return {};
  },
});
</script>

<style lang="scss" scoped>
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
.redistirbution {
  padding-bottom: 20px;
}
</style>