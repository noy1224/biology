<template>
    <div>
      <h1>{{ creature.name }}</h1>
      <img :src="creature.image" :alt="creature.name" />
      <p>{{ creature.description }}</p>
      <NuxtLink to="/">戻る</NuxtLink>
    </div>
  </template>
  
  <script setup>
  import { useRoute } from 'vue-router'
  
  const route = useRoute()
  const creatures = await useFetch('/data/creatures.json')
  const creature = creatures.data.value.find(c => c.id === route.params.id)
  </script>
  