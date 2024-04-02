<script setup>
import BaseSelect from '@/components/BaseSelect.vue'
import { HOUR_IN_DAY } from '@/constants'

const props = defineProps({
  timelineItem: {
    required: true,
    type: Object,
    validator({ hour }) {
      return typeof hour === 'number' && hour >= 0 && hour < HOUR_IN_DAY
    }
  }
})
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

//

const selectedActivityId = 2
</script>

<template>
  <li class="relative flex flex-col gap-2 px-4 py-10 border-t border-gray-200">
    <a href="#" :class="hourLinkClasses"> {{ timelineItem.hour }} : 00 </a>
    <base-select :selected="selectedActivityId" :options="options" placeholder="Rest" />
  </li>
</template>
