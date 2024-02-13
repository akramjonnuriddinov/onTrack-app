<script setup>
import { PAGE_PROGRESS } from '@/constants'
import { CheckCircleIcon } from '@heroicons/vue/24/solid'
</script>

<template>
  <a :href="`#${PAGE_PROGRESS}`">
    <div v-if="false" class="flex items-center gap-1">
      Day complete!
      <check-circle-icon class="text-green-500 h-7" />
    </div>
    <div v-else class="flex items-center gap-1">
      <div>Progress: <span class="font-mono">20%</span></div>
      <div class="w-3 h-3 bg-red-500 rounded-full"></div>
    </div>
  </a>
</template>
