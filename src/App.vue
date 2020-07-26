<template>
  <div id="app">
    <Meal v-if="currentStep === 0" @updateStep="updateStep" />
    <Location v-if="currentStep === 1" @updateStep="updateStep" />
    <Category v-if="currentStep === 2" @updateStep="updateStep" />
  </div>
</template>

<script>
import Meal from "./components/Meal.vue";
import Location from "./components/Location.vue";
import Category from "./components/Category.vue";

export default {
  name: "App",
  components: {
    Meal,
    Location,
    Category,
  },
  data: () => ({
    currentStep: 0,
  }),
  methods: {
    updateStep: function () {
      this.currentStep += 1;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap");

#app {
  font-family: "Permanent Marker", cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
