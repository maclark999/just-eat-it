<template>
  <div>
    <h1>Meal</h1>
    <ul>
      <li>
        <label>
          <input type="radio" name="meal" />Breakfast
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="meal" />Lunch
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="meal" />Dinner
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="meal" />Drinks
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="meal" checked />Whatever Is Open
        </label>
      </li>
    </ul>
    <button @click="$emit('updateStep')">Next</button>
  </div>
</template>

<script>
export default {
  name: "Meal",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
