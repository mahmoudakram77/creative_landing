<template>
  <div class="c position-relative">
    <div class="container">
      <div class="overlay"></div>
      <div class="row">
        <div class="col-sm-4">
          <div class="text">
            <h1 class="">THE BEST PRICE</h1>
            <p class="text-center mx-auto">
              Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nam,
              debitis nemo soluta placeat cum ex officiis laborum quia vel vitae
              ad sint animi iste saepe recusandae. Ab ipsa nesciunt eaque?
            </p>
            <button>SALE NOW</button>
          </div>
        </div>
      </div>
    </div>
    <div class="containe">
      <div class="contenerr">
        <h1 class="text-center">OUR BLOG</h1>
        <div class="row">
          <div class="col-lg-4">
            <div class="card">
              <img src="@/assets/blog2.png" alt="" />
              <div class="card-body">
                <h1>Lorem ipsum dolor sit.</h1>
                <p>
                  Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                  Tempora deserunt vero reprehenderit nesciunt excepturi ex
                  beatae commodi incidunt pariatur explicabo?
                </p>
                <a class="text-center" href="">read more</a>
              </div>
            </div>
          </div>
          <div class="col-lg-4">
            <div class="card">
              <img src="@/assets/blog0.png" alt="" />
              <div class="card-body">
                <h1>Lorem ipsum dolor sit.</h1>
                <p>
                  Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                  Tempora deserunt vero reprehenderit nesciunt excepturi ex
                  beatae commodi incidunt pariatur explicabo?
                </p>
                <a class="text-center" href="">read more</a>
              </div>
            </div>
          </div>
          <div class="col-lg-4">
            <div class="card">
              <img src="@/assets/blog0.png" alt="" />
              <div class="card-body">
                <h1>Lorem ipsum dolor sit.</h1>
                <p>
                  Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                  Tempora deserunt vero reprehenderit nesciunt excepturi ex
                  beatae commodi incidunt pariatur explicabo?
                </p>
                <a class="text-center" href="">read more</a>
              </div>
            </div>
          </div>
        </div>
        <div class="car">
          <h1 class="text-center mt-5">PORTFOLIO</h1>
          <carImage></carImage>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import carImage from "./carImage.vue";

export default {
  components: {
    carImage,
  },
};
</script>
<style lang="scss" scoped>
.car {
  // margin-top: 100px;
}

.container {
  background: url("@/assets/cb109c2f7f32551c528064a74cbe--dlya-doma-interera-loft-kuhnya-betonnaya.png");
  background-size: cover;
  height: 600px;
  width: 100%;
  position: absolute;
  top: 500px;
  left: 50%;
  transform: translate(-50%);
}

.container .overlay {
  background: black;
  position: absolute;
  width: 100%;
  height: 600px;
  left: 0;
  opacity: 0.6;
}
.containe {
  position: absolute;
  top: 1300px;
  left: 50%;
  transform: translate(-50%);
  width: 100%;
}

.contenerr {
  position: absolute;
  top: 120px;
  left: 50%;
  transform: translate(-50%);
  width: 100%;
  margin: 0 auto;
  overflow-x: hidden;
}

.card {
  width: 327px;
  margin: 0 auto;
  margin-top: 100px;

  img {
    width: 326px;
  }

  .card-body {
    h1 {
      font-size: 20px;
      text-align: center;
      color: rgb(0, 0, 138);
    }

    p {
      text-align: center;
    }
  }
}

.text {
  text-align: center;
  position: absolute;
  color: white;
  z-index: 2;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  h1 {
    font-size: 80px;
  }

  p {
    font-size: 20px;
  }

  button {
    background: rgb(0, 0, 159);
    border: rgb(0, 0, 159);
    color: white;
    padding: 5px 20px;
    font-size: 30px;
    border-radius: 30px;
    transition: 1s ease all;
    border-bottom: 3px solid #555;

    &:hover {
      letter-spacing: 0.5rem;
      transition: 1s ease all;
      text-shadow: 0 0 10px white;
    }
  }
}

@media screen and (max-width: 768px) {
  .text {
    h1 {
      font-size: 40px;
      text-shadow: 0 0 10px white;
    }

    p {
      width: 330px;
    }

    button {
      font-size: 20px;
    }
  }
}
.card {
  transition: 1s ease all;
}
.card:hover {
  transition: 1s ease all;
}
.card img {
  transition: 1s ease all;
}
.card img:hover {
  transform: scaleY(1.1);
  transition: 1s ease all;
}
.text {
  text-shadow: 0 0 10px black;
}
.card {
}
.col-lg-4 {
}
body,
html {
  overflow-x: hidden;
}
</style>
