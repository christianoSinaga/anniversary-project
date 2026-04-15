<script setup>
import CheckpointWindow from './components/checkpoint/CheckpointWindow.vue'
import GalleryWindow from './components/gallery/GalleryWindow.vue'
import MainMessage from './components/MainMessage.vue'
import { ref, onMounted } from 'vue'

const audioRef = ref(null)
const isPlaying = ref(false)

const playAudio = () => {
  if (!audioRef.value) return

  audioRef.value.volume = 0.2

  audioRef.value.play().then(() => {
    isPlaying.value = true
  })
}

const toggleAudio = () => {
  if (!audioRef.value) return

  if (isPlaying.value) {
    audioRef.value.pause()
    isPlaying.value = false
  } else {
    playAudio()
  }
}

onMounted(() => {
  playAudio()
})
</script>

<template>
  <!-- Audio Player -->
  <!-- Floating Music Button -->
  <button
    @click="toggleAudio"
    class="fixed bottom-5 right-5 z-50 bg-black/70 text-white p-3 rounded-full shadow-lg backdrop-blur-md hover:scale-110 transition"
  >
    {{ isPlaying ? '⏸️' : '▶️' }}
  </button>
  <audio ref="audioRef" loop>
    <source src="/src/assets/song/shittin-me.mp3" type="audio/mpeg" />
  </audio>
  <!-- Main Container -->
  <div
    class="h-screen overflow-y-scroll snap-y snap-mandatory bg-linear-to-br from-red-100 to-purple-300"
  >
    <section class="h-dvh pb-20 flex items-center justify-center snap-start">
      <MainMessage />
    </section>

    <section class="h-full flex items-center justify-center snap-start">
      <div
        class="h-full overflow-y-scroll flex justify-center items-start py-6 pbe-40 no-scrollbar"
      >
        <CheckpointWindow />
      </div>
    </section>

    <section class="h-full pb-20 flex items-center justify-center snap-start">
      <GalleryWindow />
    </section>
  </div>
</template>

<style scoped>
.no-scrollbar::-webkit-scrollbar {
  display: none;
}
.no-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>
