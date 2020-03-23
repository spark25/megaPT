<template>
  <div class="topHeader lightHeader">
    <div class="brand">
      <img src="../assets/mega.png" height="40px" alt srcset />
    </div>
    <nav>
      <ul>
        <router-link
          v-for="(menu, i) in nav"
          :key="i"
          tag="li"
          :to="{ name: menu.route }"
          >{{ menu.name }}</router-link
        >
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  props:["nav"],
  data() {
    return {
      // nav: []
    };
  },
  methods: {},
  // created(){
  //   this.nav =  this.$store.state.nav
  // }
};
</script>

<style lang="scss">
.topHeader {
  height: 64px;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 5px 20px;
  transition: all 0.3s ease-in;

  nav {
    ul {
      display: flex;
      list-style: none;
      li {
        padding: 5px;
        margin: 5px;
        font-weight: 500;
       
        position: relative;
        text-transform: uppercase;
        font-family: "Oswald", sans-serif;
    
        cursor: pointer;
        &::after {
          content: "";
          height: 3px;
          width: 0%;
          position: absolute;
          bottom: 0;
          left: 0;
          transition: all 0.3s ease-in;
          background: $primary;
        }
        &:hover::after {
          width: 100%;
        }
      }
    }
  }
}

.lightHeader {
  // background-color: rgba($color: #000000, $alpha: 0.2);
  // box-shadow: 0px 5px 18px -12px #131313;
    nav {
    ul {
      li {
        color: #eee;
        &:hover {
          color: #fff;
        }
      }
      .router-link-exact-active {
        color: #fff;
      }
    }
  }
  .brand {
    opacity: 0;
    transition: opacity 0.3s ease-in;
  }
}

.solidHeader {
  background-color: #fff;
  box-shadow: 0px 5px 18px -12px #444444;
  nav {
    ul {
      li {
        color: #4e4e4e;
        &:hover {
          color: #141414;
        }
      }
      .router-link-exact-active {
        color: #141414;
      }
    }
  }
  .brand {
    opacity: 1;
  }
}
.showBrand {
  .brand {
    opacity: 1;
  }
}

.router-link-exact-active {
  position: relative;
  // color: #fff;
  &::after {
    content: "";
    width: 100% !important;

  }
}
</style>
