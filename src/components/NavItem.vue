<script setup>
defineProps(['page'])
</script>

<template>
  <li class="flex-1">
    <a class="flex flex-col items-center p-2 text-xs capitalize" :href="`#${page}`">
      <slot />
    </a>
  </li>
</template>
