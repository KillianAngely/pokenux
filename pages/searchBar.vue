<template>
    <div class="search-container">
    <UContainer >
      <div class="search-bar">
        <UInput type="text" v-model="searchTerm" placeholder="Entrez le nom du Pokémon"></UInput>
      </div>
      <UButton color="black" variant="solid" @click="searchPokemon">Rechercher</UButton>
    </UContainer>

    <UCard v-if="pokemon != null ">
        <h2>{{ pokemon.name}}</h2>
        <img :src="pokemon.image" alt="pokemon" class="pokemon-image" />
        <ul>
          <li>weight : {{ pokemon.weight }}</li>
          <li>types : {{ pokemon.types.join(', ') }}</li>
          <li>stats : {{ pokemon.stats.join(', ') }}</li>
          <li>abilities : {{ pokemon.abilities.join(', ') }}</li>
        </ul>
    </UCard>
      <div v-else>
        <p>Entrez le nom d'un Pokémon pour commencer</p>
      </div>
    </div>

</template>
  
<script setup lang="ts">

const searchTerm = ref('');
const pokemon = ref(null);

const searchPokemon = async () => {
  try {
    const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${searchTerm.value.toLowerCase()}`);
    if (response.ok) {
      const data = await response.json();
      const name = data.name;
      const image = data.sprites.front_default;
      const weight = data.weight;
      const types = data.types.map((type: any) => type.type.name);
      const stats = data.stats.map((stat: any) => stat.base_stat);
      const abilities = data.abilities.map((ability: any) => ability.ability.name);

      pokemon.value = { name, image , weight, types , stats , abilities};

    } else {
      throw new Error('Pokemon not found');
    }
  } catch (error) {
    console.error(error);
    window.location.href = '/error';
  }
};
</script>

  
<style scoped>
  .search-container {
    margin-top: 25%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .search-bar {
    margin-bottom: 30px;
  }

  .pokemon-image {
    width: 100px; 
    height: 100px;
    display: block;
    margin: 0 auto 10px;
  }
</style>
  