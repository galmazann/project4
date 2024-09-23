<template>
    <div v-if="recipe">
      <h2>Total Cost for {{ recipe.name }}</h2>
      <p>Cost: {{ totalCost }} USD</p>
      <p>Calories: {{ totalCalories }} kcal</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['recipe'],
    computed: {
      totalCost() {
        return this.recipe ? this.recipe.cost : 0;
      },
      totalCalories() {
        return this.recipe ? this.recipe.calories : 0;
      },
    },
  };
  </script>
  