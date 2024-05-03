<template>
    <div class="error-container">

      <div class="image-container">
        <img class="error-image" src="/assets/pikachuko.jpeg" alt="Image d'erreur">
      </div>

      <h1 class="error-title">K.O.</h1>
      <p class="error-message">{{ errorMessage }}</p>
  
      <UButton color="black" variant="solid" @click="returnToHome">Retourner à l'accueil</UButton>
    </div>
  </template>
    
  <script>
  export default {
    data() {
      return {
        errorMessage: "Aucun Pokémon trouvé."
      };
    },
    methods: {
      returnToHome() {
        this.$router.push('/');
      }
    }
  };
  </script>
  
  

<style>
  .error-container {
    text-align: center;
    margin-top: 50px;
  }

  .image-container {
    display: flex;
    justify-content: center;
  }

  .error-image {
    max-width: 100%;
    max-height: 300px;
    margin-bottom: 20px;
  }
  .error-title {
    font-size: 32px;
    color: #FF6347;
  }
  
  .error-message {
    font-size: 18px;
    color: #FF6347;
    margin-bottom: 20px;
  }
</style>
  