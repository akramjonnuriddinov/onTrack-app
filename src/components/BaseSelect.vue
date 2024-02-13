<script setup>
import BaseButton from '@/components/BaseButton.vue'
import { XMarkIcon } from '@heroicons/vue/24/outline'

defineProps(['selected', 'options', 'placeholder'])
</script>

<template>
  <div class="flex gap-2">
    <base-button>
      <x-mark-icon class="w-8" />
    </base-button>
    <select class="w-full px-2 py-1 text-2xl truncate bg-gray-100 rounded">
      <option selected disabled>{{ placeholder }}</option>
      <option
        v-for="{ value, label } in options"
        :key="value"
        :value="value"
        :selected="value === selected"
      >
        {{ label }}
      </option>
    </select>
  </div>
</template>
