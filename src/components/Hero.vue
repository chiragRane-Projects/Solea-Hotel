<script setup>
import Navbar from './Navbar.vue'
</script>

<template>
  <div class="relative w-full h-[95vh] overflow-hidden">
    <!-- Hero Image -->
    <img
      src="../assets/heroImage.jpg"
      alt="hero"
      class="absolute inset-0 w-full h-full object-cover"
    />

    <!-- Overlay -->
    <div class="absolute inset-0 bg-black/20 z-10"></div>

    <!-- Navbar -->
    <Navbar class="absolute top-0 left-0 w-full z-20" />

    <!-- Centered Content -->
    <div class="relative z-20 flex flex-col items-center justify-center h-full text-white text-center px-4">
      <p class="mb-4 text-sm font-light tracking-widest">Winner of Best Island Retreat 2024</p>
      <h1 class="text-4xl md:text-6xl font-serif italic leading-tight">
        Escape into a World of<br />
        Sophistication
      </h1>
      <p class="mt-6 max-w-2xl text-sm md:text-base font-light">
        Escape the ordinary and indulge in the art of fine living at Solea —
        a sanctuary of timeless elegance.
      </p>
    </div>
  </div>
</template>
