<template>
  <div>
    <h1>Location</h1>
    <div>
      <input
        class="w-9/12"
        type="range"
        value="0.25"
        min="0.25"
        max="25"
        step="0.25"
        @input="updateValue($event)"
      />
    </div>
    <div>{{ sliderValue }} miles</div>
    <button @click="$emit('updateStep')">Next</button>
  </div>
</template>

<script>
export default {
  name: "Location",
  data: () => ({
    sliderValue: 0,
  }),
  methods: {
    updateValue: function (event) {
      this.sliderValue = event.target.value;
    },
  },
};
</script>

<style>
/* https://codepen.io/seanstopnik/pen/CeLqA */
/* https://css-tricks.com/sliding-nightmare-understanding-range-input/ */
</style>
