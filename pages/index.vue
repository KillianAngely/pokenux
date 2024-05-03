<template>
  <Header></Header>
    <div class="pokemon-list">
      <UCard v-for="pokemon in pokemons" :key="pokemon.name" class="pokemon-card" color="white" shadow>
        <div class="pokemon-content">
          <img :src="pokemon.url_image" alt="pokemon" class="pokemon-image" />
          <p class="pokemon-name">{{ pokemon.name }}</p>
        </div>
      </UCard>
    </div>
  <Footer></Footer>
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
  }
  </script>
  

<style>
  .pokemon-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  
  .pokemon-card {
    width: 200px;
    margin: 10px;
  }
  
  .pokemon-content {
    text-align: center;
  }
  
  .pokemon-image {
    width: 100px; 
    height: 100px;
    display: block;
    margin: 0 auto 10px;
  }
  
  .pokemon-name {
    margin: 0; 
  }
</style>