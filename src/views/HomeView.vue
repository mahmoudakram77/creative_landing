<template>
  <div class="row">
    <div class="col-lg-6">
      <img class="img1 img-fluid" src="@/assets/1.png" alt="" />
    </div>
    <div class="col text2 mt-5 text-center">
      <img class="img2" src="@/assets/2.png" alt="" />
      <transition name="fade" mode="in-out" appear>
        <div class="text">
          <h1 class="h1">{{ text }}</h1>
          <p>{{ para }}</p>
          <button class="b">{{ btn }}</button>
        </div>
      </transition>
    </div>
  </div>

  <!-- the second sec -->
  <div class="container-fluid con">
    <div class="row">
      <div class="col-lg-5 col-md-10 col-sm-10">
        <h1>{{ made }}</h1>
        <p>{{ para }}</p>
        <a
          href=""
          class="text-black-50 link mb-5"
          style="text-decoration: none"
          >{{ learn }}</a
        >
      </div>
      <div class="buble position-absolute">
        <img src="@/assets/40.png" alt="" />
        <img class="buble2" src="@/assets/20.png" alt="" />
        <img src="@/assets/30.png" alt="" />
      </div>

      <div class="col-lg-5 col-md-10 col-sm-10">
        <div class="image position-relative">
          <div class="image-wrapper">
            <img class="img-fluid image-up" src="@/assets/up.png" alt="Up" />
            <img
              class="img-fluid image-under"
              src="@/assets/under.png"
              alt="Under"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="showing">
    <showing-image />
  </div>
  <bg-sec class="bg"></bg-sec>

  <div class="conn position-relative">
    <contact-v class="contact"></contact-v>
  </div>
</template>

<script>
// @ is an alias to /src
import showingImage from "@/components/items/showingImage.vue";
import BgSec from "@/components/bgSec.vue";
import contactV from "@/components/contactV.vue";
export default {
  name: "HomeView",
  data() {
    return {
      text: "lorem lorem",
      btn: "SHOP NOW",
      made: "MADE WITH A SOUL",
      learn: "Learn About Us",
      para: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Expedita nam neque modi veritatis velit recusandae dolorum laborum ut optio voluptate.",
    };
  },
  components: { showingImage, BgSec, contactV },
};
</script>

<style lang="scss" scoped>
.image-wrapper {
  position: relative;
}

.image-under {
  position: relative;
  z-index: 1;
}

.image-up {
  position: absolute;
  top: 20%;
  left: 80%;
  transform: translate(-50%, -50%);
  z-index: 2;
  max-width: 100%;
  height: auto;
}
@media screen and (max-width: 900px) {
  .image-up {
  }
}

.img1 {
  z-index: -1;
  position: absolute;
  left: 0;
  top: 0;
}
.img2 {
  position: absolute;
  right: 0;
  top: 0;
  z-index: -2;
}
.text {
  color: white;
  margin-right: 100px;
  h1 {
    font-size: 100px;
  }
}
button {
  background: rgb(0, 0, 83);
  padding: 10px;
  border: 1px solid rgb(0, 0, 83);
  border-radius: 20px;
  color: white;
  transition: 0.5s ease all;
  &:hover {
    border-bottom: 4px solid #555;
    transition: 0.8s ease all;
  }
}
.row {
  width: 100%;
}
.text {
  margin-top: 100px;
  text-shadow: 3px 3px 1px rgb(0, 0, 0);

  font-family: sans;
  color: rgb(255, 255, 255);
  p {
    font-size: 20px;
    font-weight: bold;
    text-shadow: 0px 0px 10px rgb(0, 0, 0);
  }
  button {
    font-weight: bold;
  }
}
@media screen and (max-width: 1268px) {
  .text {
    position: absolute;
    left: 50%;
    top: 20%;
    transform: translate(-50%, -20%);
    width: 300px;
    padding: 10px;
  }
}
h1 {
  -webkit-text-stroke: 1px black;
}
.container {
  position: absolute;
  top: 900px;
  margin: 0px 100px;
  overflow-x: hidden;
}
.row {
  justify-content: center;
}
@media screen and (max-width: 768px) {
  .con {
  }
  .image-up {
    width: 150px;
  }
  .image-under {
    margin-left: -40px;
  }
  .image {
    position: absolute;
    left: 65%;
    top: 150px;
    transform: translate(-50%, -50%);
  }
}
.link {
  display: inline-block;
  position: relative;
  &::after {
    content: "";
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 0px;
    height: 2px;
    background: #555;
    transition: 1s ease-in-out;
  }
  &:hover::after {
    width: 100%;
  }
}
.con {
  position: absolute;
  top: 800px;
  padding: 20px 40px;
  .row {
    align-items: center;
  }
  .image-wrapper {
    margin-left: -30px;
  }
}
.showing {
  margin-top: 1000px;
}
.fade-enter-active,
.fade-leave-active {
  transition: 1s ease-in;
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-to {
  opacity: 1;
}
.fade-leave-from {
  opacity: 1;
}
.fade-leave-to {
  opacity: 0;
}
.b:hover {
  letter-spacing: 6px;
}
.buble {
  bottom: 450px;
  animation: move infinite;
  display: flex;
  justify-content: space-between;
  img {
    width: 85px;
  }
}
.buble img:nth-child(1) {
  width: 110px;
  height: 110px;
  animation: move 10s infinite;
}
.buble img:nth-child(2) {
  width: 120px;
  height: 120px;
  animation: move 8s infinite;
}

.buble img:nth-child(3) {
  width: 100px;
  height: 100px;
  animation: move 9s infinite;
}

.buble img:nth-child(4) {
  width: 200px;

  animation: move 12s infinite;
}

.buble img:nth-child(5) {
  width: 80px;
  height: 80px;
  animation: move 17s infinite;
}
.buble img:nth-child(6) {
  width: 100px;
  height: 100px;

  animation: move 13s infinite;
}
.buble img:nth-child(7) {
  width: 120px;
  height: 88px;
  animation: move 30s infinite;
}

@keyframes move {
  0% {
    transform: translateY(0) rotate(0deg);
    opacity: 0;
  }
  100% {
    transform: translateY(-1000px) rotate(360deg);
    opacity: 1;
  }
}
.buble2 {
}
.conn {
}
.contact {
  position: absolute;
  top: 2600px;
  overflow-x: hidden;
  left: 50%;
  transform: translate(-50%);
}
body,
html {
  overflow-x: hidden;
}
@media screen and (max-width: 1900px) {
  .contact {
    position: absolute;
    top: 2700px;
    overflow-x: hidden;
    left: 43%;
    transform: translate(-50%);
  }
}
@media screen and (max-width: 1400px) {
  .contact {
    position: absolute;
    top: 2700px;
    overflow-x: hidden;
    left: 41%;
    transform: translate(-50%);
  }
}
@media screen and (max-width: 991px) {
  .contact {
    position: absolute;
    top: 3800px;
    overflow-x: hidden;
    left: 40%;
    transform: translate(-50%);
  }
}
@media screen and (max-width: 768px) {
  .contact {
    position: absolute;
    top: 3600px;
    overflow-x: hidden;
    left: 36%;
    transform: translate(-50%);
  }
}
@media screen and (max-width: 620px) {
  .contact {
    position: absolute;
    top: 3600px;
    overflow-x: hidden;
    left: 34%;
    transform: translate(-50%);
  }
}
@media screen and (max-width: 575px) {
  .contact {
    position: absolute;
    top: 3600px;
    overflow-x: hidden;

    transform: translate(-50%);
  }
}
@media screen and (max-width: 450px) {
  .contact {
    position: absolute;
    top: 3600px;
    left: 26%;
    overflow-x: hidden;

    transform: translate(-50%);
  }
}
@media screen and (max-width: 413px) {
  .contact {
    position: absolute;
    top: 3600px;
    left: 24%;
    overflow-x: hidden;

    transform: translate(-50%);
  }
}
</style>
