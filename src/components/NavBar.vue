<template>
  <header class="lightHeader">
    <div class="brand">
      <img src="../assets/mega.png" height="40px" alt srcset />
    </div>
    <nav>
      <ul>
        <router-link
          v-for="(menu, i) in nav"
          :key="i"
          tag="li"
          :to="{name: menu.route}"
        >{{menu.name}}</router-link>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      nav: [
        {
          name: "Home",
          route: "Home"
        },
        {
          name: "About",
          route: "About"
        },
        {
          name: "Projects",
          route: "About"
        },
        {
          name: "Contact",
          route: "About"
        }
      ]
    };
  },
  methods: {}
};
</script>

<style lang="scss">
header {
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
        color: #eee;
        position: relative;
        text-transform: uppercase;
        &:hover{
             color: #fff;
        }
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
  background-color: rgba($color: #000000, $alpha: 0.2);
  // box-shadow: 0px 5px 18px -12px #131313;
  .brand {
    opacity: 0;
    transition: opacity 0.3s ease-in;
  }
}

.solidHeader {
  background-color: #f5f5f5;
  box-shadow: 0px 5px 18px -12px #444444;
  nav {
    ul {
      li {
        color: #474747;
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
  color: #fff;
  &::after {
    content: "";
    height: 3px;
    width: 100%;
    position: absolute;
    bottom: 0;
    left: 0;
    background: $primary;
  }
}
</style>