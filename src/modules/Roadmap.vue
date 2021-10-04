<template>
  <section id="roadmap" class="section token-info">
    <h2 class="header-2">Roadmap</h2>

    <div
      style="opacity: 1; transform-style: preserve-3d"
      class="w-layout-grid timeline-grid"
    >
      <div
        id="w-node-d23b6533-20aa-100c-6817-34ece76dab3f-96fbd0ad"
        class="timeline-wrapper"
      >
        <div class="timeline-dot"></div>
        <div class="timeline-dot">Q3</div>
        <div class="timeline-dot">Q4</div>
        <div class="timeline-dot">Q1</div>

        <div class="timeline-line-wrapper">
          <div id="timeline" class="time-line" style="height: 0%"></div>
        </div>
      </div>
      <div class="text-div">
        <div
          class="dot-text"
          ddata-aos-anchor-placement="bottom-bottom"
          data-aos="fade-up-right"
          data-aos-duration="1000"
        >
          <span> Project launch</span><br />
          - Launching the pre-sale<br />
          - Community building<br />
          - Launch of website and social channels<br />
          - Creating the marketing and production plan<br />
          - Aidrop to the most devoted holders <br />
        </div>
        <div
          class="dot-text"
          data-aos-anchor-placement="bottom-bottom"
          data-aos="fade-up-left"
          data-aos-duration="1000"
        >
          <span>2021</span><br />
          - Establishing marketing cooperations<br />
          - Listing applications on the most popular services<br />
          - Announcement of unique NFT store portal focused on music project
          <br />
          - Consultation of the charity program with the community <br />
        </div>
        <div
          class="dot-text"
          data-aos-anchor-placement="bottom-bottom"
          data-aos="fade-up-right"
          data-aos-duration="1000"
        >
          <span>2021</span><br />
          - Further marketing expansion<br />
          - NFT store release<br />
          - Applying for cex listing (HotBit/KuCoin/Gate.io)<br />
          - Starting work on mobile app project<br />
        </div>
        <div
          class="dot-text"
          data-aos-anchor-placement="bottom-bottom"
          data-aos="fade-up-left"
          data-aos-duration="1000"
        >
          <span>2022</span><br />
          - Mobile app release <br />
          - Rare 3D NFTs release<br />
          - Charity program expanding<br />
          - Expanding artist cooperation to enrich our NFT portfolio<br />
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "Roadmap",
  components: {},
  data() {
    return {
      height: 0,
    };
  },
  methods: {
    timeline() {
      var s = window.scrollY;
      var percent = (s - this.height - 40) / 16;

      if (percent > 100) {
        percent = 100;
      }
      document.getElementById("timeline").style.height = percent + "%";
      var dot = document.getElementsByClassName("timeline-dot");
      var textbox = document.getElementsByClassName("dot-text");
      for (var i = 0; i < dot.length; i++) {
        if (percent >= i * 33) {
          if (dot[i].style.backgroundColor != "#14ffa1") {
            dot[i].style.backgroundColor = "#14ffa1";
          }
        } else {
          if (dot[i].style.backgroundColor != "#e315ff") {
            dot[i].style.backgroundColor = "#e315ff";
          }
        }
      }
    },
  },
  created() {
    window.addEventListener("scroll", this.timeline);
  },
  destroyed() {
    window.removeEventListener("scroll", this.timeline);
  },
  mounted() {
    this.height =
      document.getElementById("timeline").getBoundingClientRect().top -
      (window.innerHeight / 100) * 90 +
      window.scrollY;
    this.timeline();
  },
});
</script>

<style lang="scss" scoped>
.timeline-grid {
  z-index: 5;
  position: relative;
}
.text-div {
  position: absolute;
  margin-left: 50px;
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  top: 0;
  height: 1600px;
  max-height: 1600px;
  max-width: 100%;
  width: 100%;
  margin-top: 0px;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -webkit-flex-direction: column;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-pack: justify;
  -webkit-justify-content: space-between;
  -ms-flex-pack: justify;
  justify-content: space-between;
}
.timeline-line-wrapper {
  position: absolute;
  z-index: -1;
  width: 6px;
  height: 1520px;
  background-color: rgba(var(--c5), 0.8);
}
.time-line {
  width: 100%;
  height: 100%;
  background-color: rgba(var(--c1), 0.8);
}
.timeline-dot {
  font-weight: 500;
  font-size: 20px;
  text-align: center;
  vertical-align: center;

  width: 39px;
  height: 39px;
  min-height: 39px;
  padding-top: 4px;
  border-style: solid;
  border-width: 3px;
  border-color: rgba(var(--c4), 1);
  border-radius: 1000px;
  background-color: rgba(var(--c5), 1);
  box-shadow: 0 2px 9px 0 rgb(112 81 239 / 35%);
}

.timeline-wrapper {
  padding-top: 40px;
  position: relative;
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  height: 1560px;
  max-height: 1560px;
  max-width: 100%;
  margin-top: 0px;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -webkit-flex-direction: column;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-pack: justify;
  -webkit-justify-content: space-between;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  -webkit-align-items: center;
  -ms-flex-align: center;
  align-items: center;
}

.dot-text {
  span {
    font-size: 30px;
    display: block;
    font-family: Fira Code, Menlo, Monaco, Consolas, Liberation Mono,
      Courier New, monospace;
  }
  border-radius: 25px;
  position: relative;
  width: 40%;
  background-color: rgba(114, 72, 221, 0.279);
  padding-top: 20px;
  padding-bottom: 20px;
  padding-left: 20px;
  padding-right: 20px;
}
.dot-text::before {
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
.dot-text:nth-child(2n) {
  margin-left: 52%;
}
@media only screen and (max-width: 768px) {
  .dot-text:nth-child(n) {
    margin-left: 10%;
  }
  .dot-text {
    width: 80%;
  }
  .timeline-wrapper {
    max-width: 20%;
  }
  .text-div {
    width: 80%;
  }
}
</style>