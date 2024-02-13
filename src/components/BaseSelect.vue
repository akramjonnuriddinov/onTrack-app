<script setup>
import { XMarkIcon } from '@heroicons/vue/24/outline'

const options = [
  { value: 1, label: 'Coding' },
  { value: 2, label: 'Reading' },
  { value: 3, label: 'Training' }
]
</script>

<template>
  <div class="flex gap-2">
    <button
      class="p-3 bg-gray-100 rounded enabled:hover:bg-gray-200 disabled:cursor-not-allowed disabled:opacity-50"
    >
      <x-mark-icon class="w-8" />
    </button>
    <select name="" id="" class="w-full px-2 py-1 text-2xl truncate bg-gray-100 rounded">
      <option selected disabled value="">Rest</option>
      <option v-for="{ value, label } in options" :key="value" :value="value">
        {{ label }}
      </option>
    </select>
  </div>
</template>
