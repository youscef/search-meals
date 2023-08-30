<script setup>
import { RouterView, RouterLink } from "vue-router";
</script>

<template>
  <div class="bg-gray-100 h-full">
    <header class="bg-white shadow h-16 flex justify-between item-stretch">
      <RouterLink :to="{ name: 'home' }" class="inline-flex items-center px-5 h-full ">Home</RouterLink>
      <div class="flex items-center gap-1">
        <RouterLink :to="{ name: 'byName' }" class=" inline-flex items-center transition-colors  px-2 h-full hover:bg-purple-100">Search Meals</RouterLink>
        <RouterLink :to="{ name: 'byLetter' }" class="inline-flex items-center transition-colors px-2 h-full hover:bg-purple-100">Meals By Letter</RouterLink>
        <RouterLink :to="{ name: 'byIngredient' }" class="inline-flex items-center transition-colors px-2 h-full hover:bg-purple-100">Meals By Ingredients</RouterLink>
      </div>
    </header>
    <main><RouterView></RouterView></main>
  </div>
</template>

<style scoped></style>
