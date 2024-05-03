<template>
    <div class="search-container">
      <div class="search-bar">
        <input type="text" v-model="searchTerm" placeholder="Entrez le nom du Pokémon">
      </div>
      <UButton color="black" variant="solid" @click="searchPokemon">Rechercher</UButton>
    </div>

    <div v-if="pokemon" class="pokemon-info">
      <h2>{{ pokemon.name }}</h2>
      <img :src="pokemon.sprites.front_default" alt="Image du Pokémon">
    </div>
</template>
  
<script>
  export default {
    data() {
      return {
        searchTerm: "",
        pokemon: null
      };
    },
    methods: {
      async searchPokemon() {
        try {
          const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${this.searchTerm.toLowerCase()}`);
          if (!response.ok) {
            throw new Error("Pokemon non trouvé");
          }
          this.pokemon = await response.json();
        } catch (error) {
          console.error(error);
          this.$router.push('/error');
        }
      }
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
</style>
  