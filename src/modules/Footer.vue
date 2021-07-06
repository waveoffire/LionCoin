<template>
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
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "Footer",
  components: {},
  data() {
    return {};
  },
});
</script>

<style lang="scss" scoped>
.socials {
  padding: 20px 0;
}
.copyright {
  font-size: 0.7rem;
  color: rgba(255, 255, 255, 0.605);
}
</style>