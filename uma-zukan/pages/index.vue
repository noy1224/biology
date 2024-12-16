<template>
    <div>
      <h1>未確認生物図鑑</h1>
      <ul>
        <li v-for="creature in creatures" :key="creature.id">
          <NuxtLink :to="`/creature/${creature.id}`">{{ creature.name }}</NuxtLink>
        </li>
      </ul>
    </div>
  </template>
  
  <script setup>
  const creatures = await useFetch('/data/creatures.json')
  </script>
  