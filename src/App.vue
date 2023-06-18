<template>
  <nav-bar></nav-bar>

  <router-view />

  <footer-footer class="footer"></footer-footer>
  <scroll-up></scroll-up>
  <loading-page></loading-page>
</template>

<script>
import navBar from "./components/navBar.vue";
import footerFooter from "./components/footerFooter.vue";
import ScrollUp from "./components/scrollUp.vue";
import LoadingPage from "./components/loadingPage.vue";
export default {
  components: {
    navBar,
    footerFooter,
    ScrollUp,
    LoadingPage,
  },
};
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  overflow-x: hidden;
}
.footer {
  position: absolute;
  bottom: -800px;
}
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
// }

// nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }
.fade6-enter-active {
  transition: opacity 0.5s;
}
.fade6-enter-from {
  opacity: 0;
}
.fade6-enter-to {
  opacity: 1;
}

/* Define the leaving state */
.fade6-leave-active {
  transition: opacity 0.1s;
}
.fade6-leave-from {
  opacity: 1;
}
.fade6-leave-to {
  opacity: 0;
}
</style>
