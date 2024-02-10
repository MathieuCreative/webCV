<script lang="ts">
import { defineComponent, ref, onMounted } from 'vue';

interface Skill {
  name: string;
  level: number;
  animatedLevel: number;
}

export default defineComponent({
  name: 'SkillBar',
  setup() {
    const skills = ref<Skill[]>([
      { name: 'HTML', level: 90, animatedLevel: 0 },
      { name: 'CSS', level: 80, animatedLevel: 0 },
      { name: 'JS', level: 75, animatedLevel: 0 },
      { name: 'HTML', level: 90, animatedLevel: 0 },
      { name: 'CSS', level: 80, animatedLevel: 0 },
      { name: 'JS', level: 75, animatedLevel: 0 },
      { name: 'HTML', level: 90, animatedLevel: 0 },
      { name: 'CSS', level: 80, animatedLevel: 0 },
      { name: 'JS', level: 75, animatedLevel: 0 },
      // Autres compétences...
    ]);

    const animateSkill = (skill: Skill) => {
      let start = 0;
      const interval = setInterval(() => {
        if (start >= skill.level) {
          clearInterval(interval);
        }
        skill.animatedLevel = start;
        start++;
      }, 20); // Ajustez cette valeur pour contrôler la vitesse de l'animation
    };

    onMounted(() => {
      skills.value.forEach(animateSkill);
    });

    return { skills };
  },
});
</script>





<template>
  <div class="custom-bg-color flex flex-wrap md:flex-nowrap ">
    <!-- Zone de texte avec padding et marge -->
    <div class="md:flex-1 p-4 bg-white shadow rounded-lg mr-20 ml-20 my-5">
      <h2 class="text-2xl font-bold mb-4">À propos de moi</h2>
      <p>Bonjour👋
        <br>Je suis Mathieu Magnin, un
étudiant en 3ème année de Licence Informatique à l’Université de Bordeaux.
Intrigué par le pouvoir créatif que permet d’acquérir la programmation, je me suis rapidement intéressé à plusieurs technologies ci-contre qui m’ont permis de réaliser quelques projets dont je suis déjà fier !
L’année prochaine, je souhaite rejoindre l’EINSERB MATMECA en alternance. Je cherche donc une entreprise pour réaliser un stage pendant 4 mois (mai-septembre), et peut-être enchaîner sur une alternance ensemble ensuite !
</p>
    </div>

    <div class="md:flex-1 p-4 bg-white shadow rounded-lg mr-20 ml-20 my-5">
  <h2 class="text-2xl font-bold mb-4">Mes compétences</h2>
  <div class="space-y-4">
    <div v-for="skill in skills" :key="skill.name" class="flex items-center">
      <!-- Conteneur pour le nom de la compétence avec une largeur fixe -->
      <div class="w-20 font-bold">{{ skill.name }}</div>
      <!-- Jauge de compétence -->
      <div class="flex-1 bg-gray-200 rounded-full h-4 dark:bg-gray-700">
        <div :style="{ width: skill.animatedLevel + '%' }" class="bg-blue-500 h-4 rounded-full transition-all ease-out duration-1000"></div>
      </div>
    </div>
  </div>
</div>

</div>
</template>

<style scoped>
.custom-bg-color {
  background-color: #000C79;
}
</style>


<!--
<div :style="{ width: skill.level + '%' }" class="bg-blue-500 h-4 rounded-full transition-all ease-out duration-1000"></div>
-->
