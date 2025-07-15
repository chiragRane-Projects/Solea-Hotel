<template>
  <nav class="bg-transparent px-8 py-6 w-full fixed top-0 left-0 z-50">
    <div class="w-full mx-auto ">
      <!-- Desktop Navbar -->
      <div
        class="hidden md:flex justify-between items-center border-b border-zinc-800 pb-4 text-white text-sm uppercase tracking-wide font-semibold"
      >
        <!-- Left Section -->
        <div class="flex gap-6">
          <a href="#" class="hover:text-zinc-300 transition">Home</a>
          <a href="#" class="hover:text-zinc-300 transition">Rooms & Suites</a>
          <a href="#" class="hover:text-zinc-300 transition">Dining</a>
        </div>

        <!-- Center Section -->
        <div class="text-lg font-bold tracking-wider text-white italic">
          Solea Hotel
        </div>

        <!-- Right Section -->
        <div class="flex gap-6">
          <a href="#" class="hover:text-zinc-300 transition">Experience</a>
          <a href="#" class="hover:text-zinc-300 transition">Gallery</a>
          <a href="#" class="hover:text-zinc-300 transition">Contact</a>
        </div>
      </div>

      <!-- Mobile Navbar -->
      <div class="flex justify-between items-center md:hidden text-white">
        <h2 class="text-lg font-semibold">Solea Hotel</h2>

        <!-- Hamburger Icon -->
        <button @click="toggleMenu" class="focus:outline-none z-50">
          <svg
            v-if="!isOpen"
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
          <svg
            v-else
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>

      <!-- Mobile Dropdown -->
      <transition name="fade">
        <div
          v-if="isOpen"
          class="md:hidden mt-4 bg-white/10 backdrop-blur-lg rounded-md px-4 py-6 text-white shadow-lg animate-fadeIn"
        >
          <ul class="flex flex-col gap-4 text-sm font-semibold uppercase tracking-wide">
            <li><a href="#" class="hover:text-red-400 transition">Home</a></li>
            <li><a href="#" class="hover:text-red-400 transition">Rooms & Suites</a></li>
            <li><a href="#" class="hover:text-red-400 transition">Dining</a></li>
            <li><a href="#" class="hover:text-red-400 transition">Experience</a></li>
            <li><a href="#" class="hover:text-red-400 transition">Gallery</a></li>
            <li><a href="#" class="hover:text-red-400 transition">Contact</a></li>
          </ul>
        </div>
      </transition>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeIn {
  animation: fadeIn 0.4s ease forwards;
}
</style>
