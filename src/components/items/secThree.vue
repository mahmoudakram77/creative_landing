<template>
  <div class="oo">
    <div class="one">
      <div class="container">
        <div class="row">
          <div
            class="col-lg-4 col-sm-12 coll"
            v-for="image in images"
            :key="image.id"
          >
            <transition name="fade" appear>
              <div class="i">
                <div class="overlay">
                  <h1>{{ image.text }}</h1>
                  <h2>{{ image.price }}</h2>
                  <a
                    class="link"
                    style="color: white; text-decoration: none"
                    href=""
                    >SEE MORE</a
                  >
                </div>
                <img class="img-item" :src="image.url" alt="" />
              </div>
            </transition>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        {
          id: 1,
          url: require("@/assets/3.png"),
          text: "lorem lorem",
          price: 1200,
        },
        {
          id: 2,
          url: require("@/assets/4.png"),
          text: "lorem lorem",
          price: 1200,
        },
        {
          id: 3,
          url: require("@/assets/5.png"),
          text: "lorem lorem",
          price: 1200,
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.container {
  text-align: center;
}

.row {
  display: flex;
  justify-content: center;
}

.coll {
  margin-top: 180px;
}

@media screen and (max-width: 1268px) {
  .coll {
    position: relative;
    top: 440px;
  }
}

.i {
  position: relative;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 0;
  background-color: rgba(72, 0, 255, 0.5);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;
  overflow: hidden;
  transition: height 0.5s;
}

.i:hover .overlay {
  height: 100%;
}

.img-item {
  width: 100%;
  height: auto;
  box-shadow: 0 0 20px rgb(193, 192, 192);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}
.link {
  position: relative;

  &::after {
    content: "";
    display: block;
    width: 0;
    height: 2px;
    background-color: rgb(255, 255, 255); /* Specify the color you want */
    position: absolute;
    bottom: -5px;
    transition: width 1s ease;
  }

  &:hover::after {
    width: 100%;
  }
}
@media screen and (max-width: 768px) {
  .coll {
    margin-top: 100px; /* Adjust the margin value as needed */
  }
}
.coll {
  margin-top: 250px; /* Adjust the margin value as needed */
}
</style>
