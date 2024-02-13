<script setup>
const props = defineProps(['timelineItem'])
import { XMarkIcon } from '@heroicons/vue/24/outline'

const hourLinkClasses = [
  'absolute px-2 font-mono text-lg -translate-x-1/2 rounded -top-4 left-1/2',
  props.timelineItem.hour === new Date().getHours()
    ? 'bg-purple-900 font-black text-white'
    : 'bg-gray-100 text-gray-500'
]

const options = [
  { value: 1, label: 'Coding' },
  { value: 2, label: 'Reading' },
  { value: 3, label: 'Training' }
]
</script>

<template>
  <li class="relative flex flex-col gap-2 px-4 py-10 border-t border-gray-200">
    <a href="#" :class="hourLinkClasses"> {{ timelineItem.hour }} : 00 </a>
    <div class="flex gap-2">
      <button
        class="p-3 bg-gray-100 rounded enabled:hover:bg-gray-200 disabled:cursor-not-allowed disabled:opacity-50"
      >
        <XMarkIcon class="w-8" />
      </button>
      <select name="" id="" class="w-full px-2 py-1 text-2xl truncate bg-gray-100 rounded">
        <option selected disabled value="">Rest</option>
        <option v-for="{ value, label } in options" :key="value" :value="value">
          {{ label }}
        </option>
      </select>
    </div>
  </li>
</template>
