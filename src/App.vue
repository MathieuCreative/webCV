<script lang="ts">
import { defineComponent} from 'vue';
import AboutMe from './components/AboutMe.vue'
import SkillsList from './components/SkillsList.vue'
import Accueil from './components/Accueil.vue'





export default defineComponent({
  name: 'Main',
  components: {
    AboutMe,
    SkillsList,
    Accueil,
  },
});
</script>




<template>
      <!-- TODO : Accueil -->
      <Accueil/>
      <!-- A propos de moi et Technologies utilisées -->
  <div class="custom-bg-color flex flex-wrap md:flex-nowrap ">
    <AboutMe/>
 <SkillsList/>
</div>
<div class="scroll-test"></div>


</template>

<style scoped>
.custom-bg-color {
  background-color: #000956;
}

/* Styles pour le div de test de défilement */
.scroll-test {
  height: 5000px; /* Ou toute autre hauteur suffisante pour forcer le défilement */
}

</style>


<!--
<div :style="{ width: skill.level + '%' }" class="bg-blue-500 h-4 rounded-full transition-all ease-out duration-1000"></div>
-->
