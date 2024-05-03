<template>
  <UContainer class="flex justify-between items-center p-4">
    <ULink to="/">
      <NuxtImg src="/pokelogo.png" />
    </ULink>

    <ULink to="/searchbar"
    active-class="text-primary"
    inactive-class="text-2xl">
      Search
    </ULink>

    <ULink to="/error"
    active-class="text-primary"
      inactive-class="text-2xl">
      About
    </ULink>
  </UContainer>
</template>
<script setup lang="ts">
</script>