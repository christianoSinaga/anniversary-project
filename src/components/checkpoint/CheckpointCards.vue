<template>
  <button
    @click="hideDesc"
    class="flex flex-col justify-start bg-white p-5 rounded-lg shadow-lg gap-3 w-[70vw] shadow-gray-400"
  >
    <h1 class="font-bold text-gray-500">
      {{ props.checkpoint.title }}
    </h1>

    <transition name="accordion">
      <div v-if="showDesc" class="overflow-hidden">
        <p class="text-sm text-gray-600">
          {{ props.checkpoint.desc }}
        </p>
      </div>
    </transition>
    <span class="text-pink-700 text-xs">{{ props.checkpoint.date }}</span>
  </button>
</template>

<script setup>
import { ref } from 'vue'
const showDesc = ref(false)

const props = defineProps({
  checkpoint: {
    type: Object,
    required: true,
  },
})

const hideDesc = () => {
  showDesc.value = !showDesc.value
}
</script>

<style scoped>
h1 {
  font-family: 'Cardo', serif;
}
.accordion-enter-active,
.accordion-leave-active {
  transition: all 0.3s ease;
  overflow: hidden;
}

.accordion-enter-from,
.accordion-leave-to {
  max-height: 0;
  opacity: 0;
}

.accordion-enter-to,
.accordion-leave-from {
  max-height: 300px;
  opacity: 1;
}
</style>
