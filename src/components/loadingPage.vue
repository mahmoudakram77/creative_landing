<template>
  <div class="loading" v-if="false">
    <img src="@/assets/one.gif" alt="" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    };
  },
  methods: {
    loading() {
      this.show = true;
      setTimeout(() => {
        this.show = false;
      }, 6000);
    },
  },
  created() {
    window.addEventListener("load", this.loading);
    this.loading();
  },
};
</script>

<style scoped>
.loading {
  display: flex;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  z-index: 9999;
  align-items: center;
  width: 100%;
  height: 500%;
  background: black;
  justify-content: center;
}
</style>
