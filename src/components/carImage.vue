<template>
  <Splide class="sp" :options="options" aria-label="My Favorite Images">
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 1" />
    </SplideSlide>
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 2" />
    </SplideSlide>
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 2" />
    </SplideSlide>
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 2" />
    </SplideSlide>
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 2" />
    </SplideSlide>
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 2" />
    </SplideSlide>
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 2" />
    </SplideSlide>
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 2" />
    </SplideSlide>
    <SplideSlide>
      <img src="@/assets/1.png" alt="Sample 2" />
    </SplideSlide>
  </Splide>
</template>

<script>
// Default theme
import "@splidejs/vue-splide/css";

// or other themes
import "@splidejs/vue-splide/css/skyblue";
import "@splidejs/vue-splide/css/sea-green";

// or only core styles
import "@splidejs/vue-splide/css/core";

import { Splide, SplideSlide } from "@splidejs/vue-splide";
export default {
  data() {
    return {
      options: {
        drag: false,
        type: "loop",
        perPage: 3,
        autoplay: true,
        interval: 3000,
        perMove: 1,
        gap: 40,
        pagination: true,
        arrow: false,

        breakpoints: {
          1100: {
            perPage: 2,
            gap: 10,
          },
          768: {
            perPage: 1,
          },
        },
      },
    };
  },
  components: {
    Splide,
    SplideSlide,
  },
};
</script>

<style lang="scss" scoped>
img {
  width: 300px;
}
.sp {
  max-width: 1200px;

  margin: 0 auto;
  img {
    margin-left: 20px;
  }
}
@media screen and (max-width: 1100px) {
  .sp {
    max-width: 800px;
    margin: 0 auto;
  }
}
@media screen and (max-width: 768px) {
  .sp {
    max-width: 500px;
  }
  img {
    width: 290px;
    position: relative;
    left: 35px;
  }
}
@media screen and (max-width: 500px) {
  .sp {
    max-width: 500px;
  }
  img {
    width: 290px;
    position: relative;
    left: -15px;
  }
}
.page {
  color: red;
  background: red;
}
.button {
  color: red;
  background: red;
}
body,
html {
  overflow-x: hidden;
}
</style>
