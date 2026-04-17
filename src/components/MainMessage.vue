<template>
  <transition name="fade">
    <div
      v-if="show"
      class="flex flex-col justify-between items-center text-center gap-6 text-gray-600"
    >
      <span class="text-sm tracking-widest text-pink-700">LIMITLESS LOVE</span>
      <h1 class="text-5xl tracking-wide font-bold ease-in text-center">Happy Anniversary</h1>
      <p class="text-sm">
        Untuk kamu yang <span class="px-4 py-2 bg-white rounded-4xl">{{ gap ?? '...' }}</span> km
        dari aku
      </p>
    </div>
  </transition>
</template>

<script setup>
import { onMounted, ref } from 'vue'

// Transition function
const show = ref(false)
onMounted(() => {
  setTimeout(() => {
    show.value = true
  }, 300)
})

// Gap Calculation function
const gap = ref(null)

const targetLat = -7.259880765709585
const targetLng = 112.6451950094654

function getDistance(lat1, lon1, lat2, lon2) {
  const R = 6371
  const dLat = ((lat2 - lat1) * Math.PI) / 180
  const dLon = ((lon2 - lon1) * Math.PI) / 180

  const a =
    Math.sin(dLat / 2) ** 2 +
    Math.cos((lat1 * Math.PI) / 180) * Math.cos((lat2 * Math.PI) / 180) * Math.sin(dLon / 2) ** 2

  const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a))
  return R * c
}

onMounted(() => {
  navigator.geolocation.getCurrentPosition((pos) => {
    const userLat = pos.coords.latitude
    const userLng = pos.coords.longitude

    gap.value = getDistance(userLat, userLng, targetLat, targetLng).toFixed(1)
  })
})
</script>

<style scoped>
h1 {
  font-family: 'Emilys Candy', serif;
}
.fade-enter-active {
  transition: all 1.5s ease;
}
.fade-enter-from {
  opacity: 0;
  transform: translateY(10px);
}
.fade-enter-to {
  opacity: 1;
  transform: translateY(0);
}
</style>
