<template>
  <div class="home">
    <section class="showcase">
      <div class="leftSection">
        <div v-rellax="{ speed: 3 }" class="centerBrand">
          <img src="../assets/mega.png" alt="megaPt logo" height="100px" srcset />
        </div>
        <div class="moto">
          <h1 v-rellax="{ speed: 2 }">Design,</h1>
          <h1 v-rellax="{ speed: 1 }">Build</h1>
          <h1 v-rellax="{ speed: -1 }">&amp;</h1>
          <h1 v-rellax="{ speed: -1 }">Sustain</h1>
        </div>

        <blockquote v-rellax="{ speed: -1 }">
          <span></span>
          <p class="oneliner">
            <QuoteIcon :size="28" />We offer solution to your most complex
            construction challenges.Our strength lies in traditional
            construction method and for our creative, fresh approach to cutting
            edge technologies and delivery systems.
          </p>
        </blockquote>
        <v-btn depressed class="primary">Learn More</v-btn>
      </div>
      <div class="rightSection">
        <v-carousel
          cycle
          height="100%"
          delimiter-icon="mdi-minus"
          hide-delimiter-background
          show-arrows-on-hover
        >
          <v-carousel-item>
            <div class="slide slide1">
              <v-card class="infoCard">
                <v-card-title>Unbonded Post-Tensioning System</v-card-title>
                <v-card-text>Post-Tensioning System is a means of complementing the strength of the concrete in compression and overcoming its weakness in resisting tetnsion. Post-Tensioning Systems apply compressive force to the structure through the stressing of high strength steel strand with specialized anchorage assemblies.</v-card-text>
              </v-card>
            </div>
          </v-carousel-item>
          <v-carousel-item>
            <div class="slide slide2">
              <v-card class="infoCard">
                <v-card-title>PT System</v-card-title>
                <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus laudantium repellendus deserunt cupiditate voluptates quam voluptate est ipsum fugit eum.</v-card-text>
              </v-card>
            </div>
          </v-carousel-item>
          <v-carousel-item>
            <div class="slide slide3">
              <v-card class="infoCard">
                <v-card-title>PT System</v-card-title>
                <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus laudantium repellendus deserunt cupiditate voluptates quam voluptate est ipsum fugit eum.</v-card-text>
              </v-card>
            </div>
          </v-carousel-item>
        </v-carousel>
      </div>
    </section>
    <section class="philosophy pa-4 mt-4" >
      <v-row>
        <v-col cols="12" sm="12" md="6" lg="6">
          <v-sheet class="d-flex flex-column align-center varticalCard pa-4">
            <v-img :src="require('../assets/icons/vision.svg')" contain height="60"></v-img>
            <v-card-title class="cardTitle">Vision</v-card-title>
            <v-card-text class="cardText">
              To become the performed supplier for engineering services
              and integrated solutions to our valued customers in the
              diversified market segment.
            </v-card-text>
          </v-sheet>
        </v-col>
        <v-col cols="12" sm="12" md="6" lg="6">
          <v-sheet class="varticalCard d-flex align-center flex-column pa-4">
            <v-img :src="require('../assets/icons/mission.svg')" contain height="60"></v-img>
            <v-card-title class="cardTitle">Mission</v-card-title>
            <v-card-text class="cardText">
              To become leading organization, with providing through
              innovative solution to the construction field. Our pledge is to
              establish lasting relationship with our clients by exceeding
              their expectations and gaining their trust through exceptional
              performance.
            </v-card-text>
          </v-sheet>
        </v-col>
        <!-- <v-col cols="12">
          <v-sheet class="varticalCard d-flex align-center flex-column pa-4">
            <v-img :src="require('../assets/icons/value.svg')" contain height="60"></v-img>
            <v-card-title class="cardTitle">Values</v-card-title>
            <v-card-tex>
              
            </v-card-tex>
          </v-sheet>
        </v-col>-->
      </v-row>
    </section>
    <!-- gallary -->
    <section class="py-4 my-4">
      <v-sheet tile class="varticalCard pa-4">
        <v-img :src="require('../assets/icons/photo.svg')" contain max-height="60"></v-img>
        <v-card-title class="cardTitle text--lighten-2">Gallary</v-card-title>
        <v-card-text class="px-4">
          <v-row>
            <v-col cols="4" v-for="i in 6" :key="i">
              <div class="gallaryImg">
                <img src="https://source.unsplash.com/random" height="200" width="100%" />
                <div class="gallaryImgOverlay">Image Details</div>
              </div>
            </v-col>
          </v-row>
        </v-card-text>
          <v-card-action>
          <v-btn outlined depressed>View More</v-btn>
        </v-card-action>
      </v-sheet>
    </section>
    <!-- clients -->
    <section class="py-4 my-4">
      <v-sheet tile class="varticalCard grey pa-4 lighten-3" min-height="300">
        <v-img :src="require('../assets/icons/trust.svg')" contain max-height="60"></v-img>
        <v-card-title class="cardTitle text--lighten-2">Trusted By</v-card-title>
        <v-card-text class="px-4">
          <v-row>
            <v-col v-for="(client,i) in clients" :key="i">
              <v-btn text class="grey--text">
                <v-icon small>{{client.client}}</v-icon>
              </v-btn>
            </v-col>
          </v-row>
        </v-card-text>
      
      </v-sheet>
    </section>

    <!-- contact -->
    <section class="pa-y my-4">
      <v-row class="py-5 px-0">
        <v-col class="px-0">
          <v-sheet dark tile class="d-flex flex-column align-center success pa-5">
            <div class="display-1 py-4">Ready to connect?</div>
            <v-btn depressed outlined class="my-4">Get Started</v-btn>
          </v-sheet>
        </v-col>
      </v-row>
    </section>
  </div>
</template>

<script>
import QuoteIcon from "vue-material-design-icons/FormatQuoteOpenOutline.vue";
// import { Carousel, Slide } from "vue-carousel";
export default {
  name: "Home",
  components: {
    QuoteIcon
  },
  data() {
    return {
      clients: []
    };
  },
  methods: {
    headObserver() {
      const header = document.querySelector(".topHeader");
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
      const header = document.querySelector(".topHeader");
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
  },
  created() {
    this.clients = this.$store.state.clients;
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
  @include sm {
    flex-direction: column;
  }
  @include md {
    flex-direction: column;
  }

  .leftSection {
    display: flex;
    flex-direction: column;
    // align-items: center;
    justify-content: end;
    justify-content: flex-end;
    box-sizing: border-box;
    padding: 4rem 2rem;
    flex: 2;
    background: linear-gradient(to left, #2c5364, #203a43, #0f2027);
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
    background-size: cover;
    position: relative;
    overflow: hidden;
    .slide {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: end;
      justify-content: flex-end;
      padding: 4rem;
      .infoCard {
        z-index: 99;
        background: linear-gradient(
          to right,
          rgba(0, 0, 0, 0.801),
          rgba(67, 67, 67, 0.801)
        );
      }

      &::after {
        z-index: 1;
        content: "";
        height: 100%;
        width: 100%;
        position: absolute;
        top: 0;
        left: 0;
        background: rgba(0, 0, 0, 0.4);
      }
    }
    .slide1 {
      background: url("~../assets/bg5.jpg");
      background-size: cover;
    }
    .slide2 {
      background: url("~../assets/bg6.jpg");
      background-size: cover;
    }
    .slide3 {
      background: url("~../assets/bg4.jpg");
      background-size: cover;
    }
  }
}

.gallaryImg {
  height: 200px;
  overflow: hidden;
  position: relative;
  img {
    transition: all 0.3s;
    // &:hover{
    //   transform: scale(1.2);
    // }
  }
  .gallaryImgOverlay {
    color: #fff;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.466);
    transform: scale(0);
  }

  &:hover {
    img {
      transform: scale(1.2);
    }
    .gallaryImgOverlay {
      transform-origin: bottom;
      transform: scale(1);
    }
  }
}
</style>
