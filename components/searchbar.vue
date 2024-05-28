<template>
    <UContainer >
      <div class="search-bar">
        <UInput type="text" v-model="searchTerm" placeholder="Entrez le nom du Pokémon"></UInput>
      </div>
      <UButton color="black" variant="solid" @click="searchPokemon">Rechercher</UButton>
    </UContainer>
</template>


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