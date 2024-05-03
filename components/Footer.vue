<template>
  <div>
    <NUFooter class="footer">
      <div class="left-content">
        <span>&copy; 2024 Pokédex en Nuxt fait par Thomas, Alexis, Roger et Killian</span>
      </div>
    </NUFooter>
  </div>
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
