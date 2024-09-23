<template>
    <div>
      <h2>Add a New Recipe</h2>
      <input v-model="newRecipe.name" placeholder="Recipe Name"/>
      <input v-model.number="newRecipe.cost" placeholder="Total Cost"/>
      <input v-model.number="newRecipe.calories" placeholder="Total Calories"/>
      <button @click="submitRecipe">Add Recipe</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newRecipe: { name: '', cost: 0, calories: 0 },
      };
    },
    methods: {
      submitRecipe() {
        if (this.newRecipe.name) {
          this.$emit('add-recipe', { ...this.newRecipe });
          this.newRecipe = { name: '', cost: 0, calories: 0 };
        }
      },
    },
  };
  </script>
  