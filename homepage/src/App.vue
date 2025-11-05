<template>
  <div class="relative h-screen w-screen bg-[#412B6B] overflow-hidden">
    <!-- Sanfter Glow-Kreis in Orange, mittig -->
    <div class="absolute inset-0 flex items-center justify-center pointer-events-none">
      <div class="w-[900px] h-[900px] rounded-full bg-gradient-orange-glow" />
    </div>

    <!-- NAVIGATION rechts -->
    <nav class="absolute top-16 right-16 flex flex-col gap-10 z-10">
      <button class="nav-btn" @click="active = 'about'">About me</button>
      <button class="nav-btn" @click="active = 'projects'">Projects</button>
      <button class="nav-btn" @click="active = 'contact'">Contact</button>
    </nav>

    <!-- HEADER oben links -->
    <header class="absolute top-10 left-16 z-10">
      <h1 class="text-white text-3xl font-bold underline">Maischen</h1>
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
.bg-gradient-orange-glow {
  background: radial-gradient(
    circle,
    rgba(242,89,18, 0.28) 0%,
    rgba(65,43,107, 0.07) 60%,
    rgba(65,43,107, 0.0) 100%
  );
}
.nav-btn {
  color: #fff;
  background: none;
  border: 2px solid #fff;
  border-radius: 16px;
  padding: 0.5rem 1.5rem;
  font-size: 1.3rem;
  cursor: pointer;
  transition: background 0.2s, color 0.2s;
}
.nav-btn:hover {
  background: rgba(242,89,18,0.11);
  color: #fff59d;
}
</style>
