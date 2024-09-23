<template>
  <div id="app">
    <h1>Recipe Expense Tracker</h1>
    <ExpenseTracker @add-recipe="addRecipe"/>
    <RecipeList :recipes="recipes" @select-recipe="selectRecipe"/>
    <TotalCost :recipe="selectedRecipe"/>
  </div>
</template>

<script>
import RecipeList from './components/RecipeList.vue';
import ExpenseTracker from './components/ExpenseTracker.vue';
import TotalCost from './components/TotalCost.vue';

export default {
  components: { RecipeList, ExpenseTracker, TotalCost },
  data() {
    return {
      recipes: [],
      selectedRecipe: null,
    };
  },
  methods: {
    addRecipe(recipe) {
      this.recipes.push(recipe);
    },
    selectRecipe(recipe) {
      this.selectedRecipe = recipe;
    },
  },
};
</script>
