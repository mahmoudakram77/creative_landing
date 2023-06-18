<template>
  <div class="bbg">
    <div
      class="oo"
      style="font-size: 100px; text-transform: uppercase; color: white"
    >
      <div class="first">
        <span>H</span>
        <span>E</span>
        <span>L</span>
        <span>L</span>
        <span>o</span>
      </div>
      <div class="last">
        <span>W</span>
        <span>o</span>
        <span>r</span>
        <span>L</span>
        <span>D</span>
      </div>
    </div>

    <div class="shop text-center mx-auto d-flex">
      <div class="one">
        <h1>WE ARE</h1>
        <div class="bg">
          <transition name="fade" appear>
            <p :style="{ color: currentColor }">{{ currentWord }}</p>
          </transition>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    getTransitionName() {
      const index = this.currentIndex;
      switch (index) {
        case 0:
          return "fade-enter-one";
        case 1:
          return "fade-enter-two";
        case 2:
          return "fade-enter-three";
        case 3:
          return "fade-enter-four";
        default:
          return "fade-enter";
      }
    },
  },
  data() {
    return {
      color: ["red", "blue", "white", "pink"],
      words: ["creative", "DESIGNER", "CODER", "DEVELOPER"],
      currentIndex: 0,
      currentWord: "",
      currentColor: "",
      intervalId: null,
    };
  },
  mounted() {
    this.startWordInterval();
  },
  methods: {
    startWordInterval() {
      this.currentWord = this.words[this.currentIndex].toUpperCase();
      this.currentColor = this.color[this.currentIndex];
      this.intervalId = setInterval(() => {
        this.currentIndex = (this.currentIndex + 1) % this.words.length;
        this.currentWord = this.words[this.currentIndex].toUpperCase();
        this.currentColor = this.color[this.currentIndex];
      }, 3000);
    },
    stopWordInterval() {
      clearInterval(this.intervalId);
    },
  },
  beforeUnmount() {
    this.stopWordInterval();
  },
};
</script>

<style scoped>
.shop {
  margin-top: 100px;
}
h1 {
  padding: 10px;
}
.bg {
  background: black;
  display: inline-block;
  padding: 10px 30px;
  width: 330px;
}
p {
  color: white;
  font-size: 30px;

  text-align: center;
  animation: movee 10s alternate infinite;
}
@keyframes movee {
  0% {
    transform: scale(1);
    letter-spacing: 0px;
  }

  100% {
    transform: scale(1.2);
    letter-spacing: 10px;
  }
}

.one {
  display: flex;
}

.fade-enter-active,
.fade-leave-active {
  transition: 10s ease all;
}
.fade-enter-from {
  opacity: 0;
  transform: scale(1);
}
.fade-enter-to {
  opacity: 1;
  transform: scale(1.1);
}
.fade-leave-from {
  opacity: 1;
  transform: scale(1.1);
}
.fade-leave-to {
  opacity: 0;
  transform: scale(1);
}
.shop {
  position: absolute;
  left: 50%;
  top: 60%;
  transform: translate(-50%, -50%);
}
* {
  background: black;
}
h1 {
  color: white;
}
.oo {
  margin-top: 100px;
  text-align: center;
}

.first {
  background: none;
  animation: moveee 4s infinite alternate;
}

@keyframes moveee {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(1.1);
  }
}
@keyframes moveeee {
  0% {
    letter-spacing: 0px;
  }
  100% {
    letter-spacing: 50px;
  }
}
.last {
  background: none;
  animation: moveeee 4s infinite alternate;
}
</style>
