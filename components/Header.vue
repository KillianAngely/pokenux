<template>
  <div>
    <NUHeader>
      <!-- Barre de navigation -->
      <div class="navbar">
        <router-link to="/">Accueil</router-link>
        <router-link to="/pokedex">Pokédex</router-link>
        <router-link to="/search">Rechercher</router-link>
        <router-link to="/about">À Propos</router-link>
      </div>
      
      <!-- Contenu à gauche du header -->
      <div class="left-content">
        <span>Pokédex en Nuxt</span>
      </div>
      
      <!-- Barre de recherche -->
      <div class="search-container">
        <input type="text" v-model="searchQuery" placeholder="Rechercher un Pokémon..." class="search-input" @input="searchPokemon" />
      </div>
    </NUHeader>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const searchQuery = ref('');

// Fonction de recherche de Pokémon
const searchPokemon = () => {
  console.log(searchQuery.value);
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 50px; /* Hauteur de la barre de navigation */
  background-color: black; /* Couleur de fond */
  color: white; /* Couleur du texte */
}

.navbar a {
  text-decoration: none;
  color: white;
}

.navbar a:hover {
  text-decoration: underline;
}

.left-content {
  margin-left: 5%;
  margin-top: 15px;
  font-size: 1.5rem;
  color: white;
}

.search-container {
  text-align: right;
  color: white;
}

.search-input {
  margin-top: 5px;
  margin-right: 30%;
  border-style: double;
  font-size: 1rem;
  color: white;
}

</style>
