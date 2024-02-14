<template>
  <div class = "accueil-couleur">
    <h1 class="accueil-couleur text-center text-5xl text-white">Contact</h1>
    <div class="accueil-couleur flex justify-center items-center pt-10">
      <div class="flex space-x-4">
        <!-- LinkedIn -->
        <a href="https://www.linkedin.com/in/mathieu-magnin-0a7570204/" target="_blank">
          <img src="../assets/linkedIn.png" alt="LinkedIn" class="w-16 h-16 rounded-lg"/>
        </a>
        <!-- Gmail -->
        <a href="mailto:mathieu.magnin07@gmail.com">
          <img src="../assets/gmail.png" alt="Gmail" class="bg-white w-16 h-16 rounded-lg"/>
        </a>
        <!-- GitHub -->
        <a href="https://github.com/MathieuCreative" target="_blank">
          <img src="../assets/github.png" alt="GitHub" class="bg-white w-16 h-16 rounded-lg"/>
        </a>
      </div>
    </div>
    <div class = "espace"></div>
      <div class="w-16 h-1 bg-white mx-auto mt-4"></div>
      <div class = "espace"></div>
      <h2 class = "text-custom-bg-color txt-2xl text-center">Ce site web est mis à disposition selon les termes de la Licence Creative Commons Attribution - Pas d'utilisation Commerciale - Pas de Modification. </h2>
      <div class = "espace"></div>
      <div class = "espace"></div>

    </div>
  </template>
  
  <script lang="ts">
  export default {
    name: 'Contact',
  }
  </script>
  
  <style scoped>
  .accueil-couleur {
  background-color: #6b6b6b;
}
.espace {
  height: 30px; /* Ou toute autre hauteur suffisante pour forcer le défilement */
  background-color: #6b6b6b;
}
.custom-bg-color {
  background-color: #000956;
}

  </style>
  