<template>
  <header
    :class="{ 'nav-hidden': navbarHidden, 'navbar-scrolled': navbarScrolled }"
  >
    <nav>
      <div class="box">
        <div class="logo">LOGO</div>
      </div>
      <div class="f mt-2">
        <i class="fa-brands fa-facebook" style="color: #005eff"></i>
        <i class="fa-brands fa-twitter" style="color: #4081f2"></i>
        <i class="fa-brands fa-youtube" style="color: red"></i>
        <i class="fa-brands fa-linkedin" style="color: white"></i>
      </div>
      <ul class="desk" v-show="!mobile">
        <li v-for="menu in menus" :key="menu.id">
          <router-link :to="menu.url">{{ menu.name }}</router-link>
        </li>
        <translate-google />
      </ul>
      <div class="menu" v-show="mobile" :class="{ 'icon-active': mobileNav }">
        <div class="burger-container-3" @click="toggleBurger">
          <div
            class="burger-3"
            :class="['burger-3', { 'burger-active-3': isActive }]"
          ></div>
        </div>
      </div>
      <div class="bg">
        <transition name="fade">
          <ul class="mt-3 mobile-nav" v-show="mobileNav">
            <li @click="toggleBurger" v-for="menu in menus" :key="menu.id">
              <router-link :to="menu.url">{{ menu.name }}</router-link>
            </li>
          </ul>
        </transition>
      </div>
    </nav>
  </header>
</template>

<script>
import TranslateGoogle from "./translateGoogle.vue";
export default {
  components: { TranslateGoogle },
  data() {
    return {
      menus: [
        { id: 1, name: "HOME", url: "/" },
        { id: 2, name: "SHOP", url: "/shop" },
        { id: 3, name: "PORTFOLIO", url: "/shop" },
        { id: 4, name: "BLOG", url: "/shop" },
        { id: 5, name: "CONTACT", url: "/shop" },
      ],
      isActive: false,
      mobile: null,
      mobileNav: null,
      windowWidth: null,
      navbarHidden: false,
      lastScrollPosition: 0,
      navbarScrolled: false,
    };
  },
  methods: {
    toggleBurger() {
      this.isActive = !this.isActive;
      this.mobileNav = !this.mobileNav;
    },
    checkMobile() {
      this.windowWidth = innerWidth;
      if (this.windowWidth <= 1240) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
    },
    // navbar fixed
    scrollHandler() {
      const currentScrollPosition = window.scrollY;
      if (currentScrollPosition > 100) {
        this.navbarHidden = true;
      } else {
        this.navbarHidden = false;
      }
      if (currentScrollPosition > this.lastScrollPosition) {
        this.navbarScrolled = true;
      } else {
        this.navbarScrolled = false;
      }
      this.lastScrollPosition = currentScrollPosition;
    },
  },
  created() {
    window.addEventListener("resize", this.checkMobile);
    this.checkMobile();
  },
  // navbar fixed
  mounted() {
    window.addEventListener("scroll", this.scrollHandler);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>

<style lang="scss" scoped>
.desk {
  margin-top: 10px;
  margin-right: -460px;
}
.f {
  position: absolute;
  left: 120px;
  top: 12px;
}
.f i {
  font-size: 20px;
  margin: 0 10px;

  padding: 2px;
}
header {
  background: linear-gradient(
    90deg,
    rgba(0, 0, 0, 0.5) 0%,
    rgba(0, 0, 0, 1) 50%,
    rgba(0, 0, 0, 1)
  );

  // margin: -10px;
  nav {
    z-index: 1;
    .logo {
      font-size: 20px;
      color: white;
      margin-top: 5px;
      border: 1px solid white;
      padding: 5px;
    }
    display: flex;
    justify-content: space-between;
    margin: 0 50px;
    padding: 5px;
    ul {
      display: flex;
      list-style: none;
      li {
        text-decoration: none;
        a {
          margin: 0 20px;
          color: white;
          text-decoration: none;
          padding: 5px 10px;
          transition: 0.5s ease all;

          &:hover {
            background: rgb(0, 0, 100);
            border-radius: 20px;
            border-bottom: 1px solid white;
            transition: 0.5s ease all;
          }
        }
      }
    }
  }
}

.router-link-exact-active {
  background: rgb(0, 0, 100);
  padding: 5px 10px;
  border-radius: 20px;

  border-bottom: 1px solid white;
  border-bottom: 1px solid white;
}

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }

// mobile
.menu {
  position: absolute;
  right: 20px;
  top: 16px;
  z-index: 3;
}
.box .logo div {
  z-index: 9999;
}
.f {
  z-index: 9999;
}
header {
  z-index: -1;
}
.mobile-nav {
  flex-direction: column;
  /* background: blue; */
  position: absolute;
  left: 0;
  top: 41px;
  // height: 400px;
  padding: 30px;
  font-size: 20px;
  // margin-top: 20px;
  width: 100%;
  z-index: 1;
  /* background: rgb(0, 95, 255); */
  background: linear-gradient(
    90deg,
    rgba(0, 0, 0, 0.5) 0%,
    rgba(0, 0, 0, 1) 50%,
    rgba(0, 0, 0, 1)
  );
  opacity: 1;
  li {
    margin-top: 20px;
    margin-left: -30px;
  }
}
@media screen and (max-width: 500px) {
  .mobile-nav {
    flex-direction: column;
    /* background: blue; */
    position: absolute;
    left: 0;
    top: 40.3px;
    // height: 400px;
    padding: 30px;
    font-size: 20px;
    // margin-top: 20px;
    width: 100%;
    z-index: 1;
    /* background: rgb(0, 95, 255); */
    background: linear-gradient(
      90deg,
      rgba(0, 0, 0, 0.5) 0%,
      rgba(0, 0, 0, 1) 50%,
      rgba(0, 0, 0, 1)
    );
    opacity: 1;
    li {
      margin-top: 20px;
      margin-left: -30px;
    }
  }
}
// burger setting
.burger-container-3 {
  width: 40px;
  height: 25px;
  cursor: pointer;
  margin: auto;
  -webkit-transition: all 0.3s ease-out;
  -moz-transition: all 0.3s ease-out;
  -ms-transition: all 0.3s ease-out;
  -o-transition: all 0.3s ease-out;
  transition: all 0.3s ease-out;
}
.burger-3 {
  display: block;
  width: 40px;
  height: 5px;
  position: relative;
  top: 10px;
  background-color: #ffffff;
  -webkit-transition: all 0.3s ease-out;
  -moz-transition: all 0.3s ease-out;
  -ms-transition: all 0.3s ease-out;
  -o-transition: all 0.3s ease-out;
  transition: all 0.3s ease-out;
  border-radius: 20px;
}
.burger-3::after {
  position: relative;
  display: block;
  content: " ";
  top: 5px;
  width: 40px;
  height: 5px;
  background-color: #ffffff;
  -webkit-transition-property: transform, top;
  transition-property: transform, top;
  -webkit-transition-duration: 0.2s, 0.2s;
  transition-duration: 0.2s, 0.2s;
  -webkit-transition-delay: 0s, 0.2s;
  transition-delay: 0s, 0.2s;
  border-radius: 20px;
}
.burger-3::before {
  position: relative;
  display: block;
  content: " ";
  bottom: 10px;
  width: 40px;
  height: 5px;
  background-color: #ffffff;
  -webkit-transition-property: transform, bottom;
  transition-property: transform, bottom;
  -webkit-transition-duration: 0.2s, 0.2s;
  transition-duration: 0.2s, 0.2s;
  -webkit-transition-delay: 0s, 0.2s;
  transition-delay: 0s, 0.2s;
  border-radius: 20px;
}
.burger-container-3:hover {
  opacity: 0.8;
}

.burger-active-3 {
  background-color: transparent;
}
.burger-active-3::before {
  bottom: 0;
  transform: rotate(45deg);
  -webkit-transition-property: bottom, transform;
  transition-property: bottom, transform;
  -webkit-transition-duration: 0.2s, 0.2s;
  transition-duration: 0.2s, 0.2s;
  -webkit-transition-delay: 0s, 0.2s;
  transition-delay: 0s, 0.2s;
}
.burger-active-3::after {
  top: -5px;
  transform: rotate(-45deg);
  -webkit-transition-duration: 0.2s, 0.2s;
  transition-duration: 0.2s, 0.2s;
  -webkit-transition-property: top, transform;
  transition-property: top, transform;
  -webkit-transition-delay: 0s, 0.2s;
  transition-delay: 0s, 0.2s;
}
@media screen and (max-width: 768px) {
  .logo {
    margin-left: -30px;
    margin-top: -10px;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: 0.1s ease-in;
}

.fade-enter-from {
  transform: translateX(-400px);
  opacity: 0;
}
.fade-enter-to {
  transform: translateX(0px);
  opacity: 1;
}
.fade-leave-from {
  transform: translateX(0);
  opacity: 1;
}
.fade-leave-to {
  transform: translateX(400px);
  opacity: 0;
}
.link-enter-active,
.link-leave-active {
  transition: 0.3s ease-in;
}
header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;
  transition: top 0.3s;
}

/* Hide the navbar by translating it above the viewport */
.navbar-hidden {
  top: -100px;
}
.navbar-scrolled {
  background-color: white;
}
</style>
