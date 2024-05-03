<template>
    <div>
        <ul>
            <li v-for="pokemon in pokemons" :key="pokemon.name">
                <img :src="pokemon.url_image" alt="pokemon" />
                <p>{{ pokemon.name }}</p>
            </li>
        </ul>
    </div>
  </template>
  
  <script setup lang="ts">
  
  const pokemons = ref([]);
  const { data : pokelist  } = await useFetch('https://pokeapi.co/api/v2/pokemon?limit=30');
  for (const pokemonData of pokelist.value.results) {
    const url = pokemonData.url as string;
    
    var pokemonInfo = await useFetch(url);
    pokemonInfo = pokemonInfo.data.value;

    const name : string= pokemonInfo.name ;
    const url_image : string = pokemonInfo.sprites.front_default ;
    pokemons.value.push({ name, url_image});
    console.log(pokemons.value);
  }
  </script>
  