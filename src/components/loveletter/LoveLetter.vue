<template>
  <!-- Container -->
  <div class="w-full flex flex-col items-center gap-5 overflow-hidden pt-16">
    <h1 class="flex gap-2 text-2xl items-center font-bold text-pink-700">
      <Letter :size="24" />
      Secret Message
    </h1>

    <!-- Clue how to open the love letter -->
    <div
      v-if="!isOpened"
      class="relative w-[70vw] h-[70vh] border border-pink-800 rounded-xl flex items-center justify-center p-12"
    >
      <p class="absolute top-2 text-sm text-gray-500 text-center">
        Coba tangkap hatinya {{ heartHP }} kali, siapa tau ada sesuatu hehe
      </p>

      <button
        @click="moveHeart"
        class="absolute text-pink-400 hover:text-pink-600 transition duration-300"
        :style="{
          top: heartPosition.top + '%',
          left: heartPosition.left + '%',
        }"
      >
        <Heart :size="48" />
      </button>

      <p v-if="heartHP < 10" class="absolute bottom-2 text-sm text-pink-500 text-center">
        Ayooo dikit lagi, kamu pasti bisaaa
      </p>
    </div>

    <!-- The Love Letter -->
    <div class="w-[70vw] flex items-center justify-center">
      <div
        class="bg-white w-full py-10 rounded-xl shadow-lg flex items-center justify-center transition-all duration-700"
        :class="isOpened ? 'scale-100 opacity-100' : 'scale-0 opacity-0'"
      >
        <div v-if="isOpened" class="flex flex-col gap-6 text-gray-700 capitalize text-center px-4">
          <p class="text-sm">Berapa kilometerpun jarak memisahkan kita</p>

          <p class="text-sm">Berapa kalipun kita bertemu dan kembali berpisah</p>

          <p class="text-sm">Berapa kalipun kita bertengkar</p>

          <p class="text-sm">I always love you</p>

          <p class="text-xl font-bold text-pink-700">and I always love you more</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Heart from '@/assets/icons/Heart.vue'
import Letter from '@/assets/icons/Letter.vue'

const heartPosition = ref({
  top: 50,
  left: 50,
})

const isOpened = ref(false)
let clickCount = 0
let heartHP = 21

function moveHeart() {
  clickCount++
  heartHP--

  heartPosition.value = {
    top: Math.random() * 80,
    left: Math.random() * 80,
  }

  if (clickCount >= 21) {
    isOpened.value = true
  }
}
</script>

<style scoped>
h1 {
  font-family: 'Cardo', serif;
}
</style>
