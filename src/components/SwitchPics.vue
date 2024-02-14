<template>
  <div class="md:flex-1 p-4 shadow rounded-lg mr-10 ml-10 my-5">
    <div class="flex flex-col items-center">
      <div v-if="projects.length > 0" class="mb-4">
        <!-- Conteneur d'image de taille fixe -->
        <div class=" overflow-hidden bg-gray-100 flex justify-center items-center">
          <img :src="projects[currentIndex].photo" alt="Project Image" class="min-w-full min-h-full object-cover w-96 h-96">
        </div>
        <div class="text-center">
  <h2 class="text-2xl font-bold my-2 text-white">{{ projects[currentIndex].title }}</h2>
  <p class="text-white mb-4">{{ projects[currentIndex].text }}</p>
</div>
      </div>
      <div class="flex space-x-2">
        <button v-for="(project, index) in projects" :key="index" @click="setProject(index)"
          :class="['w-4 h-4 rounded-full', currentIndex === index ? 'bg-white' : 'bg-gray-500']">
        </button>
      </div>
    </div>
  </div>
</template>


<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'SwitchPics',
  setup() {
    const currentIndex = ref(0);
    const projects = ref([
      { photo: 'src/assets/teamupnow.png', title: 'teamupnow.io', text: "Mise en relation de gamers par chat audio en s'inspirant du site Omegle. Technologie webRTC pour la connexion audio en temps réel. Implémentation d'un chat textuel avec Firebase." },
      { photo: 'src/assets/pictureslab.png', title: 'Takuzu', text: 'Le jeu Takuzu revisité, réalisé en C avec SDL2 en groupe.' },
      { photo: 'src/assets/pictureslab.png', title: 'Pictures Lab', text: "Projet en cours à l'Université : Une bibliothèque de traitement d'images avec Java, SpringBoot pour le backend et Vuejs et Typescript pour le frontend. Réalisé en groupe." },
      { photo: 'src/assets/train.png', title: 'trAIn', text: "Un gros projet personnel d'application mobile autour du sport en cours de réalisation avec Flutter, Dart, Firebase et un peu d'IA. Je ne peux pas en dire plus pour l'instant😬" },

      // Ajoutez d'autres projets ici
    ]);

    function setProject(index: number) {
      currentIndex.value = index;
    }

    return { currentIndex, projects, setProject };
  },
});
</script>

<style scoped>
</style>
