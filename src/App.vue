<script lang="ts">
import { defineComponent} from 'vue';
import SwitchPics from './components/SwitchPics.vue'
import SkillsList from './components/SkillsList.vue'
import Accueil from './components/Accueil.vue'
import WidgetFleche from './components/WidgetFleche.vue'
import Timeline from './components/Timeline.vue'
import WidgetFlecheReversed from './components/WidgetFlecheReversed.vue'
import Contact from './components/Contact.vue'







export default defineComponent({
  name: 'Main',
  components: {
    SwitchPics,
    SkillsList,
    Accueil,
    WidgetFleche,
    WidgetFlecheReversed,
    Timeline,
    Contact,
  },
});
</script>




<template>
  <div class = "custom-bg-color">

  <Accueil/>

  <!-- ICI -->
<WidgetFleche/>

  <!--FIN TRUC CHELOU-->

  <div class="custom-bg-color flex flex-wrap md:flex-nowrap ">
    <SwitchPics/>
    <SkillsList/>
  </div>
  <div class="custom-bg-color">
    <Timeline/>
  </div>
  <WidgetFlecheReversed/>

<Contact/>

</div>
<div class="espace"></div>

</template>





<style scoped>
.custom-bg-color {
  background-color: #000956;
}

/* Styles pour le div de test de défilement */
.espace {
  height: 5000px; /* Ou toute autre hauteur suffisante pour forcer le défilement */
  background-color: #6b6b6b;
}


</style>


<!--
<div :style="{ width: skill.level + '%' }" class="bg-blue-500 h-4 rounded-full transition-all ease-out duration-1000"></div>
-->
