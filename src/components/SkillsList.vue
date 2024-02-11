<template>
<div class="md:flex-1 p-4 bg-white shadow rounded-lg mr-20 ml-20 my-5 skills-container">
    <h2 class="text-2xl font-bold mb-4">Technologies rencontrées</h2>
    <p class="text-gray-400 text-sm mb-4">Attention : 100% = Technologie sur laquelle j'ai passé le plus de temps, et non technologie que je maîtrise à 100% !</p>
    <div class="space-y-4">
      <div v-for="skill in skills" :key="skill.name" class="flex items-center">
        <!-- Conteneur pour le nom de la compétence avec une largeur fixe -->
        <div class="w-20 font-bold">{{ skill.name }}</div>
        <!-- Jauge de compétence -->
        <div class="flex-1 bg-gray-200 rounded-full h-4 dark:bg-gray-700">
          <div :style="{ width: skill.animatedLevel + '%' }" class="custom-bg-color h-4 rounded-full transition-all ease-out duration-1000"></div>
        </div>
      </div>
    </div>
  </div>
</template>



<script lang="ts">
import { defineComponent, ref, onMounted, onUnmounted } from 'vue';
interface Skill {
  name: string;
  level: number;
  animatedLevel: number;
}
interface Skill {
  name: string;
  level: number;
  animatedLevel: number;
}

export default defineComponent({
    name:'SkillsList',
    setup() {
    const skills = ref<Skill[]>([
      { name: 'Java', level: 100, animatedLevel: 0 },
      { name: 'Flutter', level: 100, animatedLevel: 0 },
      { name: 'C', level: 80, animatedLevel: 0 },
      { name: 'Vue.js', level: 75, animatedLevel: 0 },
      { name: 'Spring Boot', level: 75, animatedLevel: 0 },
      { name: 'y86', level: 70, animatedLevel: 0 },
      { name: 'Ocaml', level: 65, animatedLevel: 0 },
      { name: 'Tailwind', level: 40, animatedLevel: 0 },
      { name: 'JS CSS HTML', level: 80, animatedLevel: 0 },
      { name: 'Python', level: 35, animatedLevel: 0 },
    ]);
    const observer = ref<IntersectionObserver | null>(null);

    const animateSkill = (skill: Skill) => {
      let start = 0;
      const interval = setInterval(() => {
        if (start >= skill.level) {
          clearInterval(interval);
        } else {
          skill.animatedLevel = start;
          start++;
        }
      }, 20);
    };

    const resetAnimation = (skill: Skill) => {
      skill.animatedLevel = 0; // Réinitialiser immédiatement pour les besoins de l'exemple
    };

    const observeElement = (el: Element) => {
      if (observer.value) {
        observer.value.observe(el);
      }
    };

    onMounted(() => {
      observer.value = new IntersectionObserver((entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            skills.value.forEach(animateSkill);
          } else {
            skills.value.forEach(resetAnimation); // Réinitialiser quand hors du viewport
          }
        });
      }, {
        rootMargin: '0px',
        threshold: 0.1
      });

      const skillsContainer = document.querySelector('.skills-container');
      if (skillsContainer) {
        observeElement(skillsContainer);
      }
    });

    onUnmounted(() => {
      if (observer.value) {
        observer.value.disconnect();
      }
    });

    return { skills };
  },
});
</script>



<style scoped>
.custom-bg-color {
  background-color: #000C79;
}

</style>