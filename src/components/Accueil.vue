<template>
        <div class="scroll-test custom-bg-color">

        </div>

  <div class="couleur-accueil flex flex-wrap md:flex-nowrap ">

<!--ICI, créer deux divs pour : 
    - l'un afficher la photo dans ../assets/coolpick2.png avec en dessous Mathieu Magnin en h2 blanc et en dessous "Etudiant en Informatique" en texte classique
    - l'autre pareil mais je voudrais une zone qui affiche plusieurs photo (une à la fois) et plusieurs textes (chaque texte associé à une photo) et toutes les 5 secondes ça change de combinaison image/texte
    avec un v-if. Utiliser toujours la meme photo "../assets/coolpick2.png" pour toutes les photos pour l'instant.
    En dessous de la combinaison photo/texte je souhaite n "boutons" (des ronds gris par ex), chaque bouton correspond à une combinaison photo texte et lorsque la combinaison x est affichée, le bouton en question est blanc.
    Et l'utilisateur peut cliquer sur un bouton et ça affiche la combinaison en question
-->
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
.scroll-test {
  height: 10vh; /* Ou toute autre hauteur suffisante pour forcer le défilement */
}
.custom-bg-color {
  background-color: #000956;
}
</style>

