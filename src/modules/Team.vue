<template>
  <section id="team" class="section token-info">
    <h2 class="header-2">Team</h2>
    <div class="teammate">
      <div class="teamimage">
        <img src="/assets/stefan.jpg" alt="" srcset="" />
      </div>
      <div class="teamdesc">
        <div class="name">Imie Nazwisko</div>

        Zdjęcie autorstwa Stefan Stefancik z Pexels
      </div>
    </div>
    <div class="teammate">
      <div class="teamimage">
        <img src="/assets/stefan.jpg" alt="" srcset="" />
      </div>
      <div class="teamdesc">
        <div class="name">Imie Nazwisko</div>
        Zdjęcie autorstwa Stefan Stefancik z Pexels
      </div>
    </div>
    <div class="teammate">
      <div class="teamimage">
        <img src="/assets/stefan.jpg" alt="" srcset="" />
      </div>
      <div class="teamdesc">
        <div class="name">Imie Nazwisko</div>
        Zdjęcie autorstwa Stefan Stefancik z Pexels
      </div>
    </div>
    <div class="teammate">
      <div class="teamimage">
        <img src="/assets/stefan.jpg" alt="" srcset="" />
      </div>
      <div class="teamdesc">
        <div class="name">Imie Nazwisko</div>
        Zdjęcie autorstwa Stefan Stefancik z Pexels
      </div>
    </div>
    <div class="teammate">
      <div class="teamimage">
        <img src="/assets/stefan.jpg" alt="" srcset="" />
      </div>
      <div class="teamdesc">
        <div class="name">Imie Nazwisko</div>
        Zdjęcie autorstwa Stefan Stefancik z Pexels
      </div>
    </div>
    <div class="teammate">
      <div class="teamimage">
        <img src="/assets/stefan.jpg" alt="" srcset="" />
      </div>
      <div class="teamdesc">
        <div class="name">Imie Nazwisko</div>
        Zdjęcie autorstwa Stefan Stefancik z Pexels
      </div>
    </div>
    <div class="teammate">
      <div class="teamimage">
        <img src="/assets/stefan.jpg" alt="" srcset="" />
      </div>
      <div class="teamdesc">
        <div class="name">Imie Nazwisko</div>
        Zdjęcie autorstwa Stefan Stefancik z Pexels
      </div>
    </div>
    <div class="teammate">
      <div class="teamimage">
        <img src="/assets/stefan.jpg" alt="" srcset="" />
      </div>
      <div class="teamdesc">
        <div class="name">Imie Nazwisko</div>
        Zdjęcie autorstwa Stefan Stefancik z Pexels
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "TokenInfo",
  components: {},
  data() {
    return {};
  },
});
</script>

<style lang="scss" scoped>
#team {
  align-items: center;
  z-index: 5;
  position: relative;
}
.teammate {
  display: inline-block;
  width: 250px;
  z-index: 5;
  .teamimage {
    z-index: 5;
    border-radius: 50%;
    position: relative;
    top: 100px;
    margin: auto;
    img {
      z-index: 10;
      position: relative;
      height: 100%;
      border-radius: 50%;
      height: 200px;
      width: 200px;
      object-fit: cover;
    }

    height: 220px;
    width: 220px;
    padding: 10px;
    background-color: white;
  }

  .teamdesc {
    margin: auto;
    height: 200px;
    width: 220px;
    position: relative;
    .name {
      padding-top: 110px;
      padding-bottom: 10px;
      font-size: 1.3rem;
    }
  }
  .teamdesc::before {
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
    -webkit-mask: linear-gradient(#fff 0 0) content-box,
      linear-gradient(#fff 0 0);
    -webkit-mask-composite: destination-out;
    mask-composite: exclude;
  }
}
</style>