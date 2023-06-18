<template>
  <div class="oo">
    <div class="imagesButton">
      <div class="all">
        <button
          class="button"
          :class="{ active: selectedComponent === 'secOne' }"
          @click="setSelectComponent('secOne')"
        >
          POST OF CONCREATE
        </button>
        <button
          class="button"
          :class="{ active: selectedComponent === 'secTwo' }"
          @click="setSelectComponent('secTwo')"
        >
          3D PANELS
        </button>
        <button
          class="button"
          :class="{ active: selectedComponent === 'secThree' }"
          @click="setSelectComponent('secThree')"
        >
          CONCRETE FURNITURE
        </button>
        <button
          class="button"
          :class="{ active: selectedComponent === 'secFive' }"
          @click="setSelectComponent('secFive')"
        >
          DINNING TABLE
        </button>
      </div>
    </div>
    <div class="content">
      <secOne v-if="selectedComponent === 'secOne'"></secOne>
      <secTwo v-if="selectedComponent === 'secTwo'"></secTwo>
      <secThree v-if="selectedComponent === 'secThree'"></secThree>
      <sec-five v-if="selectedComponent === 'secFive'"></sec-five>
    </div>
  </div>
</template>

<script>
import secOne from "@/components/items/secOne.vue";
import secTwo from "@/components/items/secTwo.vue";
import secThree from "@/components/items/secThree.vue";

import SecFive from "@/components/items/secFive.vue";
export default {
  components: {
    secOne,
    secTwo,
    secThree,
    SecFive,
  },
  data() {
    return {
      selectedComponent: "secOne",
      isActive: false,
    };
  },
  methods: {
    setSelectComponent(cmp) {
      this.selectedComponent = cmp;
      this.isActive = true;
    },
  },
};
</script>

<style lang="scss" scoped>
.imagesButton {
  display: flex;
  justify-content: center;
  position: absolute;
  left: 50%;
  top: 1600px;
  transform: translate(-50%, -50%);
  width: 1000px;
  .all {
    background: rgb(9, 0, 45);
    padding: 10px 20px;
    border-radius: 50px;
  }
}
.button {
  display: inline-block;
  border: none;
  border-radius: 20px;
  color: #000000;
  text-transform: uppercase;
  font-size: 1rem;

  transition: all 0.3s;
  position: relative;
  overflow: hidden;
  z-index: 1;
  &:after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;

    border-radius: 10rem;
    z-index: -2;
  }
  &:before {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0%;
    height: 100%;
    background-color: darken(rgb(1, 1, 130), 0%);
    transition: all 0.3s;
    border-radius: 10rem;
    z-index: -1;
  }
  &:hover {
    color: #fff;
    &:before {
      width: 100%;
    }
  }
}
button {
  margin: 0 20px;
  background: rgb(255, 255, 255);
  color: rgb(0, 0, 0);
  padding: 5px;
  border: 1px solid rgb(4, 4, 206);
  border-radius: 20px;
  transition: 0.3s ease-in-out;

  &:hover {
    transition: 0.3s ease-in-out;
  }

  &:focus {
    background-color: rgb(1, 1, 130);

    border-radius: 20px;
  }
  &:active {
    background-color: rgb(1, 1, 130);

    border-radius: 20px;
  }
}
.active.active {
  background-color: rgb(1, 1, 130);
  border-bottom: 3px solid #555;
  color: white;
}
@media screen and (max-width: 768px) {
  .all {
    text-align: center;
    // z-index: 9999;
    margin-top: -250px;
  }
  .imagesButton {
    max-width: 380px;

    font-size: 3px;
  }
  button {
    display: grid;
    grid-template-columns: 20px 20px 20px;
    font-size: 10px;
    margin: 10px 5px;
    width: 250px;
  }
  .imagesButton {
  }
}
.imagesButton {
  margin-top: -40px;
}

.imagesButton {
  display: flex;
  justify-content: center;
  // overflow-x: auto; /* Enable horizontal scrolling */
  margin-bottom: -10px; /* Adjust as needed to remove any extra space at the bottom */
}

.all {
  background: rgb(9, 0, 45);
  padding: 10px 20px;
  border-radius: 50px;
  // white-space: nowrap; /* Prevent button wrapping */
}

@media screen and (max-width: 768px) {
  .all {
    width: 400px;
    display: grid;
    grid-template-columns: 200px 200px;
    border-radius: 0px;

    justify-content: center;
    margin-top: 0; /* Remove the negative margin */
  }

  .imagesButton {
    margin-top: -40px; /* Adjust as needed */
    margin-bottom: 0; /* Remove the negative margin */
  }

  button {
    width: auto; /* Reset the width */
  }
}
body,
html {
  overflow-x: hidden;
}
</style>
