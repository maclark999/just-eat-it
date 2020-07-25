<template>
  <div id="app">
    <Meal msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import Meal from "./components/Meal.vue";

export default {
  name: "App",
  components: {
    Meal,
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
