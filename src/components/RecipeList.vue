<template>
    <div>
      <h2>Recipes</h2>
      <ul>
        <li v-for="recipe in recipes" :key="recipe.name" @click="selectRecipe(recipe)">
          {{ recipe.name }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: ['recipes'],
    methods: {
      selectRecipe(recipe) {
        this.$emit('select-recipe', recipe);
      },
    },
  };
  </script>
  