<template>
  <div class="search">
    <keep-alive>
      <input type="text" v-if="showing" class="transition-input" />
    </keep-alive>

    <i @click="showInput" class="fas fa-search"> </i>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showing: false,
    };
  },
  methods: {
    showInput() {
      this.showing = !this.showing;
    },
  },
};
</script>

<style lang="scss" scoped>
.search {
  position: relative;
  input {
    width: 120px;
    height: 30px;
    border-radius: 20px;
    padding: 5px 5px;
    position: absolute;
    top: 0;
    border: none;
    width: 100px;
    transition: 1s ease;
    margin-left: -20px;
    color: red;
    border:none &:hover {
      width: 100px;
      transition: 1s ease;
    }
  }
  i {
    position: absolute;
    top: 35%;
    right: -75px;
    cursor: pointer;
  }
}
.transition-input {
  transition: width 1s ease;
  animation: move 1s;

  &:hover {
    width: 100px;
  }
}

@keyframes move {
  0% {
    transform: translateY(-100px);
  }
  100% {
    transform: translateY(0px);
  }
}

i {
  position: absolute;
  top: 35%;
  right: -23px;
  cursor: pointer;
  font-size: 20px;
  color: rgb(127, 0, 2);
}
</style>
