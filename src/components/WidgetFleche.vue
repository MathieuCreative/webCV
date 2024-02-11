<template>
  <div class="relative h-32 w-full">
  <!-- Div conteneur avec deux couleurs, maintenant horizontales -->
  <div class="w-full h-1/2 couleur-accueil absolute"></div>
  <div class="w-full h-1/2 custom-bg-color bottom-0 absolute"></div>
  
  <!-- Div de flèche dans un rond superposée -->
  <div class="flex items-center justify-center h-16 w-16 bg-white rounded-full absolute top-1/2 left-1/2" style="transform: translate(-50%, -50%);">
    <!-- Flèche personnalisée -->
    <div class="bg-white rounded-full p-3 flex items-center justify-center">
    <svg class="h-6 w-6 rotate-90" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="#000956" stroke-width="2">
      <path stroke-linecap="round" stroke-linejoin="round" d="M14 5l7 7m0 0l-7 7m7-7H3" />
    </svg>
  </div>
</div>
</div>

</template>

<script lang="ts">

export default{
  name: 'AboutMe'
}


</script>

<style scoped>
.custom-bg-color {
  background-color: #000956;
}
.couleur-accueil {
  background-color: #4D4D4D;
}
</style>