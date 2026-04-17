<template>
  <!-- Container -->
  <div class="w-screen h-screen flex flex-col items-center justify-center">
    <!-- Clue how to open the love letter -->
    <div
      v-if="!isOpened"
      class="relative w-[70vw] h-[70vh] border rounded-xl flex items-center justify-center p-12"
    >
      <p class="absolute top-2 text-sm text-gray-500 text-center">
        Coba klik hati ini {{ heartHP }} kali, siapa tau ada sesuatu hehe
      </p>

      <button
        @click="moveHeart"
        class="absolute text-pink-400 hover:text-pink-600 transition duration-300"
        :style="{
          top: heartPosition.top + '%',
          left: heartPosition.left + '%',
        }"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="currentColor"
          viewBox="0 0 24 24"
          width="48"
          height="48"
        >
          <path
            d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 
      2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 
      4.5 2.09C13.09 3.81 14.76 3 
      16.5 3 19.58 3 22 5.42 
      22 8.5c0 3.78-3.4 6.86-8.55 
      11.54L12 21.35z"
          />
        </svg>
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
        <p v-if="isOpened" class="text-gray-700 capitalize text-center px-4">
          <span class="text-sm">Berapa kilometerpun jarak memisahkan kita </span> <br />
          <br />
          <span class="text-sm">Berapa kalipun kita bertemu dan kembali berpisah </span> <br />
          <br />
          <span class="text-sm">Berapa kalipun kita bertengkar </span> <br />
          <br />
          <span class="text-sm">I always love you </span> <br />
          <br />
          <span class="text-xl text-pink-700">and I always love you more</span>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

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

<style scoped></style>
