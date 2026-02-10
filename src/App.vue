<script setup lang="ts">
import GoldCard from './components/GoldCard.vue'
import StatsPanel from './components/StatsPanel.vue'

// Placeholder or real image paths
const candidates = [
  {
    name: 'Anies Baswedan',
    image: '/hero/anies.png',
    number: 1,
    rotation: '-14deg',
    delay: '0.1s'
  },
  {
    name: 'Prabowo Subianto',
    image: '/hero/prabowo.png',
    number: 2,
    rotation: '0deg',
    delay: '0.2s'
  },
  {
    name: 'Ganjar Pranowo',
    image: '/hero/ganjar.png',
    number: 3,
    rotation: '14deg',
    delay: '0.3s'
  }
]
</script>

<template>
  <main class="relative w-full h-dvh flex items-center justify-center overflow-hidden selection:bg-gold-500/30">
    <!-- Main Content Container: h-dvh ensures it fits dynamic viewports -->
    <div class="relative z-10 w-full max-w-[1600px] h-dvh flex flex-col justify-between py-4 px-6 md:py-8 overflow-hidden">
      <!-- Header: Compact -->
      <header class="text-center shrink-0 z-10">
        <h1
          class="text-2xl md:text-4xl font-black font-[Metal_Mania] uppercase tracking-[0.2em]"
          style="
          background: linear-gradient(180deg, #FBC02D 0%, #F9A825 50%, #e4b01f 100%);
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
          background-clip: text;
          filter: drop-shadow(0 0 15px rgba(129, 97, 15, 0.57)) 
                  drop-shadow(0 0 30px rgba(251, 192, 45, 0.6)) 
                  drop-shadow(0 0 45px rgba(255, 183, 0, 0.688))
                  drop-shadow(0 4px 8px rgba(0, 0, 0, 0.8));
        "
        >
          Sistem Pemilu Konoha<br />Smart Contract
        </h1>
      </header>

      <!-- Cards Container: Flex-1 to take available space, centered -->
      <div class="flex-1 flex items-center justify-center relative perspective-[1500px] w-full min-h-0 py-2">
        <!-- Left Shadow Label -->
        <div class="absolute left-4 top-1/2 -translate-y-1/2 hidden 2xl:block pointer-events-none">
          <span class="font-display text-[10px] text-white/10 tracking-[0.5em] -rotate-90 block">OFFICIAL CANDIDATES</span>
        </div>

        <!-- Card Wrapper -->
        <div class="flex items-center justify-center mt-16 gap-2 md:gap-6 relative z-10 origin-center transition-transform duration-500">
          <GoldCard v-for="candidate in candidates" :key="candidate.number" v-bind="candidate" />
        </div>

        <!-- Right Shadow Label -->
        <div class="absolute right-4 top-1/2 -translate-y-1/2 hidden 2xl:block pointer-events-none">
          <span class="font-display text-[10px] text-white/10 tracking-[0.5em] rotate-90 block">SECURE VOTING</span>
        </div>
      </div>
    </div>

    <!-- Mountain Effects Overlay -->
    <div class="fixed inset-0 z-10 pointer-events-none bg-[url('/mountain-effects.png')] bg-cover bg-top bg-no-repeat bg-fixed brightness-[0.8] contrast-100"></div>

    <!-- Copyright Footer -->
    <div class="fixed bottom-3 left-3 z-10 text-[10px] text-slate-500 font-body max-w-xs hidden md:block leading-tight">
      <p>© 2026 Kohona Election Commission.</p>
      <p class="opacity-50">Authorized by the National Committee.</p>
    </div>

    <!-- Stats Panel -->
    <div class="origin-bottom-right fixed bottom-3 right-3 z-10">
      <StatsPanel />
    </div>
  </main>
</template>

<style scoped></style>
