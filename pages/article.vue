<script setup lang="ts">
const { data: Pokeinfo } = await useFetch('https://pokeapi.co/api/v2/pokemon/bulbasaur')
console.log(Pokeinfo)
</script>

<template>
  <p>Page visits: {{ Pokeinfo }}</p>
</template>
