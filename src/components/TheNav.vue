<script setup>
import NavItem from '@/components/NavItem.vue'
import { NAV_ITEMS } from '@/constants'

defineProps({
  currentPage: {
    required: true,
    type: String,
    validator(currentPage) {
      return Object.keys(NAV_ITEMS).includes(currentPage)
    }
  }
})
const emit = defineEmits(['navigate'])
</script>

<template>
  <nav class="sticky bottom-0 z-10 bg-white">
    <ul class="flex items-center justify-around border-t">
      <nav-item
        v-for="(icon, page) in NAV_ITEMS"
        :key="page"
        :page="page"
        :class="{ 'bg-gray-200 pointer-events-none': page === currentPage }"
        @click="emit('navigate', page)"
      >
        <component :is="icon" class="w-6 h-6" /> {{ page }}
      </nav-item>
    </ul>
  </nav>
</template>
