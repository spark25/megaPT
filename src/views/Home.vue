<template>
  <div class="home">
    <section class="showcase">
      <div class="sectionContent">
        <div class="leftSection">
          <div v-rellax="{speed: 3}"  class="centerBrand">
            <img src="../assets/mega.png" alt="megaPt logo" height="100px" srcset />
          </div>
          <div class="moto" v-rellax="{speed: -1}">
            <h1 class="animated fadeInUp faster">Design,</h1>
            <h1 class="animated fadeInUp fast">Build</h1>
            <h1 class="animated fadeInUp slow">&</h1>
            <h1 class="animated fadeInUp slow">Sustain</h1>
          </div>
          <button class="btn primary medium">Learn More</button>
        </div>

        <blockquote v-rellax="{speed: 2}">
          <span>
            <QuoteIcon :size="54" />
          </span>
          <p class="oneliner">We offer solution to your most complex construction challenges.</p>
          <p>Our strength lies in traditional construction method and for our creative, fresh approach to cutting edge technologies and delivery systems.</p>
        </blockquote>
      </div>
    </section>
    <section style="height:700px"></section>
  </div>
</template>

<script>
import QuoteIcon from "vue-material-design-icons/FormatQuoteOpenOutline.vue";
export default {
  name: "Home",
  components: {
    QuoteIcon
  },
  methods: {
    headObserver() {
      const header = document.querySelector("header");
      const showcase = document.querySelector(".showcase");
      const options = {
        rootMargin: "-100px 0px 0px 0px"
      };
      const showcaseObserver = new IntersectionObserver(entries => {
        entries.forEach(entry => {
          if (!entry.isIntersecting) {
            header.classList.add("solidHeader");
          } else {
            header.classList.remove("solidHeader");
          }
        });
      }, options);
      showcaseObserver.observe(showcase);
    },
    brandObserver() {
      const header = document.querySelector("header");
      const brand = document.querySelector(".centerBrand");
      const options = {
        rootMargin: "-30px 0px 0px 0px"
      };
      const brandObserver = new IntersectionObserver(entries => {
        entries.forEach(entry => {
          if (!entry.isIntersecting) {
            header.classList.add("showBrand");
          } else {
            header.classList.remove("showBrand");
          }
        });
      }, options);
      brandObserver.observe(brand);
    }
  },
  mounted() {
    this.headObserver();
    this.brandObserver();
  }
};
</script>
<style lang="scss">
.showcase {
  height: 100vh;
  width: 100%;
  background: url("~../assets/bg5.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  // background-position: center;
  position: relative;
  display: flex;
  // flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 2;
  overflow: hidden;

  &::before {
    content: "";
    height: 100%;
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
   background-image: linear-gradient(to right, rgba(0, 0, 0, 0.747) 0%, rgba(34, 43, 162, 0.24) 100%);
  }
  .sectionContent {
    width: 100%;
    z-index: 4;
    display: flex;
    // flex-direction: column;
    align-items: center;
    justify-content: space-around;
    .leftSection {
      display: flex;
      flex-direction: column;
      // align-items: center;
      justify-content: space-evenly;

      button{
        margin-top: 4rem;
      }
    }
    .moto {
      color: #eee;
      display: flex;
      justify-content: space-around;
      align-items: center;
      position: relative;
      padding-top: 1rem;

      h1 {
        font-size: 2.5rem;
        padding: 5px 5px;
      }

      // &::after {
      //   content: "";
      //   height: 5px;
      //   width: 100%;
      //   position: absolute;
      //   bottom: 0;
      //   border-radius: 20px;
      //   background-color: #a22522;
      // }
    }
    blockquote {
      width: 400px;
      padding: 2rem 4rem;
      margin-top: 4rem;
      border-radius: 4px;
      background: rgba($color: $primary, $alpha: 0.3);
      text-align: center;
      .material-design-icon {
        color: #fff;
      }
      p {
        color: #f5f5f5;
        text-align: right;
        // font-family: 'Montserrat', sans-serif;
        font-size: 1rem;
        font-weight: 500;
      }
    }
  }
}
</style>
