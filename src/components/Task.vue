<script setup>
import { ref } from 'vue'

const status = ref(false)
const title = ref('Сделать домашку')

function changeStatus() {
  status.value = !status.value
}
</script>

<template>
  <div
    class="flex items-center gap-4 p-4 bg-white shadow-md rounded-xl w-full max-w-md border border-gray-200"
  >
    <button
      @click="changeStatus"
      :class="[
        'transition duration-200 ease-in-out px-4 py-2 rounded-lg font-semibold border',
        status
          ? 'bg-gray-400 text-white border-gray-600 line-through'
          : 'bg-green-500 text-white border-green-600 hover:bg-green-600',
      ]"
    >
      {{ status ? 'Готово' : 'Сделать' }}
    </button>

    <h2 :class="['text-lg', status ? 'line-through text-gray-400' : 'text-gray-800']">
      {{ title }}
    </h2>
  </div>
</template>

<style scoped>
h2 {
  transition: all 0.3s ease;
}
</style>
