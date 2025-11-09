<template>
  <div class="relative h-screen w-screen bg-[#FAF3E7] overflow-hidden">

    <!-- NAVIGATION rechts -->
    <div class="fixed w-full flex justify-end p-8 space-x-4 z-10">
      <button 
        class="button-base" 
        @click="active = 'about'"
      >
      About me
      </button>
      <button 
        class="button-base" 
        @click="active = 'projects'"
      >
      Projects
      </button>
      <button 
        class="button-base "
        @click="active = 'contact'"
      >
        Contact
      </button>
    </div>


    <!-- HEADER oben links -->
    <header class="absolute top-10 left-16 z-10">
      <h1 class="text-black text-3xl font-bold underline">Maischen</h1>
    </header>

    <!-- INHALTSBOX links unter Maischen -->
    <section 
      class="absolute top-40 left-14 z-10 rounded-xl px-10 py-8 bg-[#412B6B] bg-opacity-60 border-4 border-white min-w-[250px] min-h-[220px] flex items-center"
      v-if="active"
    >
      <div v-if="active === 'about'">
        <p class="text-white text-lg">Nach dem Klick wird hier mein Text angezeigt<br/>About me Inhalt...</p>
      </div>
      <div v-else-if="active === 'projects'">
        <p class="text-white text-lg">Nach dem Klick wird hier mein Text angezeigt<br/> Projects...</p>
      </div>
      <div v-else-if="active === 'contact'">
        <p class="text-white text-lg">Nach dem Klick wird hier mein Text angezeigt<br/>Kontakt Inhalt...</p>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const active = ref('about')
</script>

<style scoped>

.button-base {
  padding: 0.75rem 1.5rem;
  border-radius: 0.9rem;
  background: orange;
  box-shadow: 0 8px 24px red;
  font-size: 0.9rem;
  font-weight: 500;
  transition: all 0.3s;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: black;
}

.button-base:hover {
  box-shadow: 0 16px 32px orange;
  transform: scale(1.25);
}
</style>
