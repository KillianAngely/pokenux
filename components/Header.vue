<template>
  <div>
    <NUHeader>
      <div class="navbar">
        <router-link to="/">Accueil</router-link>
        <router-link to="/pokedex">Pokédex</router-link>
        <router-link to="/searchBar">Rechercher</router-link>
        <router-link to="/about">À Propos</router-link>
      </div>
      
      <div class="left-content">
        <span>Pokédex en Nuxt</span>
      </div>
      
    </NUHeader>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const searchQuery = ref('');

const searchPokemon = () => {
  console.log(searchQuery.value);
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 50px;
  background-color: black;
  color: white;
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

.search-input {
  margin-top: 5px;
  margin-right: 30%;
  border-style: double;
  font-size: 1rem;
  color: white;
}

</style>
