<template>


  <div class="couleur-accueil flex flex-wrap md:flex-nowrap ">

<AccueilProfilePic/>
<AccueilAboutMe class="slide-in"/>
</div>
  </template>
  
  <script lang="ts">
import AccueilAboutMe from './AccueilAboutMe.vue';
import AccueilProfilePic from './AccueilProfilePic.vue';

export default{
  name: 'Accueil',
  components:{
    AccueilAboutMe,
    AccueilProfilePic,
  },

}


</script>




<style scoped>

@keyframes slideInFromRight {
  from {
    transform: translateX(100%); /* Commence à droite de l'écran */
  }
  to {
    transform: translateX(0); /* Termine à sa position normale */
  }
}

.slide-in {
  animation: slideInFromRight 1s ease-out forwards; /* Adaptez la durée et le type d'animation selon vos préférences */
}

.couleur-accueil {
  background-color: #6b6b6b;
}

.custom-bg-color {
  background-color: #000956;
}
</style>

