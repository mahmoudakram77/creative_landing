<template>
  <transition name="fade10" appear>
    <div @click="scrolltoTop" v-show="show">
      <i class="fa-regular fa-circle-up"></i>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      scroll: 0,
    };
  },
  methods: {
    scrolltoTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
    onScroll() {
      this.scroll = scrollY;
      if (this.scroll >= 500) {
        this.show = true;
      } else {
        this.show = false;
      }
    },
  },
  created() {
    window.addEventListener("scroll", this.onScroll);
    this.onScroll;
  },
};
</script>

<style lang="scss" scoped>
div {
  position: fixed;
  bottom: 10px;
  right: 10px;
  i {
    font-size: 30px;
    cursor: pointer;
  }
}
.fade10-enter-active {
  transition: 1s ease all;
}
.fade10-leave-active {
  transition: 0.2s ease all;
}
.fade10-enter-from {
  opacity: 0;
}
.fade10-enter-to {
  opacity: 1;
}
.fade10-leave-from {
  opacity: 1;
}

.fade10-leave-to {
  opacity: 0;
}
</style>
