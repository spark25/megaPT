<template>
  <div class="home">
    <section class="showcase">
      <div class="leftSection">
        <div v-rellax="{speed: 3}" class="centerBrand">
          <img src="../assets/mega.png" alt="megaPt logo" height="100px" srcset />
        </div>
        <div class="moto">
          <h1 v-rellax="{speed: 2}">Design,</h1>
          <h1 v-rellax="{speed: 1}">Build</h1>
          <h1 v-rellax="{speed: -1}">&amp;</h1>
          <h1 v-rellax="{speed: -1}">Sustain</h1>
        </div>

        <blockquote v-rellax="{speed: -1}">
          <span></span>
          <p class="oneliner">
            <QuoteIcon :size="28" />We offer solution to your most complex construction challenges.Our strength lies in traditional construction method and for our creative, fresh approach to cutting edge technologies and delivery systems.
          </p>
        </blockquote>
        <button class="btn primary medium" v-rellax="{speed: -1}">Learn More</button>
      </div>
      <div class="rightSection">

      </div>
    </section>
    <section style="height:700px"></section>
  </div>
</template>

<script>
import QuoteIcon from "vue-material-design-icons/FormatQuoteOpenOutline.vue";
// import { Carousel, Slide } from "vue-carousel";
export default {
  name: "Home",
  components: {
    QuoteIcon,
  },
  data(){
    return{
       slides: [
          '<div class="example-slide">Slide 1</div>',
          '<div class="example-slide">Slide 2</div>',
          '<div class="example-slide">Slide 3</div>',
        ],
    }
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
  // background: url("~../assets/bg5.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  // background-position: center;
  position: relative;
  display: flex;
  // flex-direction: column;
  // align-items: center;
  justify-content: center;
  z-index: 2;
  overflow: hidden;
  @include sm{
    flex-direction: column;
  }
  @include md{
    flex-direction: column;
  }

  .leftSection {
    display: flex;
    flex-direction: column;
    // align-items: center;
    justify-content: end;
    box-sizing: border-box;
    padding: 4rem 2rem;
    flex: 2;
    background-image: linear-gradient(to right, #243949 0%, #517fa4 100%);

    .moto {
      color: #eee;
      display: flex;

      // justify-content: space-around;
      align-items: center;
      position: relative;
      margin-top: 1rem;

      h1 {
        font-size: 2.5rem;
        padding: 5px 10px 0px 0px;
        font-family: "Oswald", sans-serif;
      }
    }
    blockquote {
      border-radius: 4px;
      margin-top: 3rem;
      .material-design-icon {
        color: #fff;
      }
      p {
        color: #f5f5f5;
        font-size: 1rem;
        font-weight: 500;
      }
    }

    button {
      margin-top: 3rem;
    }
  }

  .rightSection {
    flex: 3;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
      background: url("~../assets/bg6.jpg");
      background-size: cover;
    
  }

  
  .sectionContent {
    width: 100%;
    z-index: 4;
    display: flex;
    align-items: center;
    justify-content: space-around;

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
  }
}
</style>
