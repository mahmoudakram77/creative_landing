<template>
  <div class="bbg">
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
  data() {
    return {
      color: ["red", "blue", "orange", "pink"],
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
    letter-spacing: 1px;
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
  top: 50%;
  transform: translate(-50%, -50%);
}
* {
}
h1 {
  color: rgb(0, 0, 0);
  width: 180px;
}
.oo {
  margin-top: 100px;
  text-align: center;
}

.first {
  background: none;
  animation: moveee 4s infinite alternate;
  font-size: 80px;
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
    letter-spacing: 2px;
  }
}
.last {
  background: none;
  animation: moveeee 4s infinite alternate;
  font-size: 40px;
}
.one {
  background: black;
  padding: 20px;
  width: 400px;
}
h1 {
  color: white;
}
</style>
