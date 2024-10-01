<script lang="ts" setup>
import { ref } from 'vue'
import TickIcon from './icons/TickIcon.vue'

// Mock data for the booking
const booking = ref({
  serviceName: 'Haircut',
  stylistName: 'Jane Doe',
  date: '2024-10-15',
  time: '14:30',
  duration: '2 hours',
  status: 'Confirmed'
})

const formatDate = (dateString: string) => {
  const options: Intl.DateTimeFormatOptions = {
    weekday: 'long',
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  }
  return new Date(dateString).toLocaleDateString('en-US', options)
}
</script>

<template>
  <div
    class="glow-card bg-white shadow-md rounded-2xl p-5 max-w-sm flex items-center flex-col mx-auto"
  >
    <TickIcon class="text-gradientTwo w-8 h-8 mb-2" />
    <h2 class="text-2xl font-bold mb-1 text-secondary">Confirmed</h2>
    <p class="text-center">You are scheduled with Executive barbershop</p>
    <div class="space-y-3">
      <p><span class="font-semibold">Service:</span> {{ booking.serviceName }}</p>
      <p><span class="font-semibold">Stylist:</span> {{ booking.stylistName }}</p>
      <p><span class="font-semibold">Date:</span> {{ formatDate(booking.date) }}</p>
      <p><span class="font-semibold">Time:</span> {{ booking.time }}</p>
      <p><span class="font-semibold">Duration:</span> {{ booking.duration }}</p>
      <p class="flex items-center gap-2">
        <span class="font-semibold">Status:</span>
        <span class="bg-green-100 text-green-800 px-3 py-1 rounded-full text-sm">
          {{ booking.status }}
        </span>
      </p>
    </div>
  </div>
</template>

<style scoped>
.glow-card {
  position: relative;
  animation: subtleGlow 4s ease-in-out infinite alternate;
}

@keyframes subtleGlow {
  0% {
    box-shadow:
      0 0 5px rgba(233, 196, 106, 0.5),
      0 0 10px rgba(233, 196, 106, 0.3),
      0 0 15px rgba(233, 196, 106, 0.1);
  }
  50% {
    box-shadow:
      0 0 5px rgba(233, 196, 106, 0.5),
      0 0 10px rgba(233, 196, 106, 0.3),
      0 0 15px rgba(233, 196, 106, 0.1);
  }
  100% {
    box-shadow:
      0 0 5px rgba(231, 111, 81, 0.5),
      0 0 10px rgba(231, 111, 81, 0.3),
      0 0 15px rgba(231, 111, 81, 0.1);
  }
}
</style>
