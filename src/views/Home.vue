<template>
  <div class="flex flex-col p-8">
    <input
      type="text"
      class="rounded border-2 border-gray-200 w-full"
      placeholder="search meals"
    />

    <div class="flex gap-2 mt-2 justify-center">
      <RouterLink
        v-for="letter of letters"
        :key="letter"
        :to="{ name: 'byLetter', params: { letter } }"
        >{{ letter }}</RouterLink
      >
    </div>
  </div>
</template>
<script setup>
import { computed, onMounted, ref } from "vue";
import store from "../store";
import axiosClient from "../axiosClient";
const ingredients = ref([]);
const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
onMounted(async () => {
  const response = await axiosClient.get("list.php?i=list");
  ingredients.value = response.data.meals;
  console.log(response);
});
</script>
