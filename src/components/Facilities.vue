<script setup>
import { Bubbles, Shell, Sunrise, User } from 'lucide-vue-next'
import {
  Card,
  CardHeader,
  CardTitle,
  CardDescription
} from './ui/card'

// Facilities with a color for each card
const facilities = [
  {
    id: 1,
    icon: Sunrise,
    title: 'Infinity Pool with Ocean View',
    desc: 'Swim in serenity with panoramic views of the turquoise sea and sky blending as one.',
    bg: '#FDF6EC' // peach
  },
  {
    id: 2,
    icon: Shell,
    title: 'Fine Dining & Rooftop Lounge',
    desc: 'Savor gourmet dishes curated by award-winning chefs — beachfront dinners or rooftop cocktails.',
    bg: '#F0F9FF' // sky blue
  },
  {
    id: 3,
    icon: Bubbles,
    title: 'Solea Signature Spa',
    desc: 'Tailored treatments, open-air massage rooms, and island essences for deep renewal.',
    bg: '#F3FAF2' // mint
  },
  {
    id: 4,
    icon: User,
    title: '24/7 Personal Concierge',
    desc: 'From private yacht bookings to custom dining — everything, taken care of.',
    bg: '#FFF4F4' // soft pink
  }
]
</script>

<template>
  <main class="relative w-full overflow-hidden">
    <!-- Background Image -->
    <img
      src="../assets/facilities.jpg"
      alt="Beach Image"
      class="absolute inset-0 w-full h-full object-cover blur-sm"
    />
    <div class="absolute inset-0 bg-white/10 z-10"></div>

    <!-- Content -->
    <article class="relative z-20 flex flex-col items-center text-center px-6 py-16 max-w-7xl mx-auto">
      <p class="text-3xl md:text-5xl font-serif mb-12 text-white">
        <span>Exceptional Facilities &</span>
        <span class="block">World-Class Services</span>
      </p>

      <!-- Cards Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 w-full">
        <Card
          v-for="facility in facilities"
          :key="facility.id"
          :style="{ backgroundColor: facility.bg }"
          class="text-left p-6 rounded-xl shadow-md hover:scale-105 transition transform duration-300"
        >
          <CardHeader class="mb-4">
            <component :is="facility.icon" class="w-8 h-8 text-blue-800 mb-2" />
            <CardTitle class="text-base font-semibold text-blue-900">
              {{ facility.title }}
            </CardTitle>
          </CardHeader>
          <CardDescription class="text-sm text-blue-800 leading-relaxed">
            {{ facility.desc }}
          </CardDescription>
        </Card>
      </div>
    </article>
  </main>
</template>
