<template>
  <UContainer class="flex justify-between items-center p-4">
    <NuxtLink to="https://github.com/KillianAngely/pokenux">
      <Icon name="uil:github" class="text-4xl"/>
    </NuxtLink>
    <span>&copy; 2024 Pokédex en Nuxt fait par Thomas, Alexis, Roger et Killian</span>
  </UContainer>
</template>
<script setup lang="ts">
</script>

<style scoped>
.footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  background-color: black;
  color: white;
  padding: 20px; 
}

.left-content {
  font-size: 1rem;
  text-align: center;
}
</style>
